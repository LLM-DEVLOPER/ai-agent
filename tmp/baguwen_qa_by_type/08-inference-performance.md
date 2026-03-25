# 推理与性能优化

---

## 1. Prefill、Decode 与延迟指标

**面试官可能会问：** Prefill 和 Decode 有什么区别？首 token 延迟和总完成时延分别受哪个阶段影响？

**回答要点：**

Prefill 和 Decode 是大模型自回归推理的两个阶段，性能瓶颈完全不同。Prefill 阶段把整个输入 prompt 一次性并行处理，计算所有 token 的 KV 值并写入 KV Cache，是计算密集型（compute-bound），GPU 利用率高，但它决定了首 token 延迟（TTFT，Time To First Token）。Prompt 越长，Prefill 越慢，用户等第一个字出现的时间就越长。

Decode 阶段是逐 token 自回归生成，每次只生成一个 token，需要读取全量 KV Cache，是内存带宽密集型（memory-bound），GPU 计算利用率反而不高，瓶颈在显存带宽。Decode 阶段决定了总完成时延（E2E latency）和 token 间延迟（ITL，Inter-Token Latency）。一句话总结：首 token 慢看 Prefill，生成慢看 Decode。

Batch size 对两个阶段的影响也不同：Prefill 阶段 batch 越大 GPU 利用率越高，吞吐越好；Decode 阶段 batch 越大，每个请求的 ITL 越高，因为显存带宽被多个请求共享。

**深入追问：** 连续批处理（Continuous Batching）和静态批处理有什么区别？

**回答要点：**

静态批处理要等一批请求都到齐才开始推理，GPU 空闲等待时间长，且不同请求长度差异大时有严重的 padding 浪费。连续批处理（也叫 iteration-level scheduling）的核心思想是：每个 decode step 结束后，调度器立刻检查是否有新请求可以插入当前 batch，不需要等整批完成。这样 GPU 几乎不空转，吞吐大幅提升。vLLM 的调度器就是基于这个思想实现的，代价是调度逻辑更复杂，需要管理动态 batch 的 KV Cache 分配。

---

## 2. vLLM 与 PagedAttention

**面试官可能会问：** vLLM 解决了什么问题？PagedAttention 的核心思想是什么？

**回答要点：**

在 vLLM 出现之前，推理服务的 KV Cache 管理是静态预分配的：每个请求在开始时就要预留最大序列长度的显存，导致大量显存碎片和浪费，高并发下显存利用率极低，系统吞吐上不去。

vLLM 的核心创新是 PagedAttention，借鉴操作系统虚拟内存分页的思想，把 KV Cache 切成固定大小的 block（类似内存页），用一张逻辑-物理 block 映射表管理。每个请求的 KV Cache 不再需要连续物理显存，按需分配 block，用完释放，显存碎片率极低。这带来两个直接收益：一是显存利用率大幅提升，同等显存下可以跑更多并发请求；二是支持 prefix sharing，多个请求如果有相同的 prompt 前缀（比如 system prompt），可以共享同一批物理 block，不需要重复计算和存储。vLLM 还内置了连续批处理调度器，整体吞吐比 naive 实现高出数倍，是目前高并发推理场景的事实标准之一。

**深入追问：** vLLM 有什么局限，什么情况下不一定适合用？

**回答要点：**

vLLM 的局限主要有几点：对单请求低延迟场景不一定最优，因为调度开销和 block 管理有额外成本；对于超长上下文（128K+），block 数量膨胀，调度压力也会上升。如果场景是单用户、低并发、对首 token 延迟极度敏感，直接用 transformers 或 llama.cpp 可能更简单直接。

---

## 3. KV Cache 与 Prefix Cache

**面试官可能会问：** KV Cache 在优化什么？Prefix Cache 又是什么？

**回答要点：**

KV Cache 的本质是用空间换时间。Transformer 的 attention 计算中，每个 token 都需要和之前所有 token 的 Key、Value 做计算。如果没有 KV Cache，每次 decode 步骤都要重新计算所有历史 token 的 K/V，计算量随序列长度线性增长。KV Cache 把已经计算过的 K/V 矩阵缓存在显存里，decode 阶段只需要计算新 token 的 K/V 并追加，大幅降低计算量。代价是显存占用随序列长度线性增长，一个 7B 模型 batch size 32、序列长度 2048，KV Cache 可以轻松占掉十几 GB 显存。

Prefix Cache（也叫 prompt cache）是 KV Cache 的进一步延伸：如果多个请求共享相同的 prompt 前缀（比如固定的 system prompt、few-shot 示例），可以把这段前缀的 KV Cache 预计算并缓存，后续请求直接复用，跳过 prefill 阶段的重复计算。vLLM 的 prefix caching 和 Anthropic 的 prompt caching 都是这个思路。在 system prompt 很长的场景（比如 RAG 把大量文档塞进 prompt），prefix cache 可以把首 token 延迟降低 50% 以上。

**深入追问：** 长上下文场景下 KV Cache 的显存压力怎么缓解？

**回答要点：**

几个方向：一是 KV Cache 量化，把 K/V 从 fp16 压缩到 int8 甚至 int4，显存减半但精度有损；二是 KV Cache offload，把不活跃的 KV 换出到 CPU 内存或 NVMe，代价是 PCIe 带宽成为新瓶颈；三是 sliding window attention（如 Mistral），只保留最近 N 个 token 的 KV，牺牲超长距离依赖；四是 MQA/GQA/MLA，减少 KV head 数量，从模型结构层面降低 KV Cache 体积。

---

## 3.5 MHA → MQA → GQA → MLA：Attention 的 KV Cache 压缩演化

**面试官可能会问：** MHA、MQA、GQA、MLA 分别是什么？为什么要从 MHA 演化到后面这些变体？

**回答要点：**

这条演化线的核心驱动力是：**KV Cache 是大模型推理的显存杀手**，减少 KV head 数量是从模型结构层面釜底抽薪。

### MHA（Multi-Head Attention）—— 标准基线

原始 Transformer 的标准设计，$h$ 个注意力头，每个头都有独立的 $Q, K, V$ 投影矩阵：

$$\text{head}_i = \text{Attention}(QW_i^Q, KW_i^K, VW_i^V)$$

KV Cache 大小 = `2 × num_layers × num_heads × head_dim × seq_len × batch_size`

对于 GPT-3（96 层，96 头，head_dim=128），batch=32，seq=2048，KV Cache 约 **192 GB**——远超单卡显存。

### MQA（Multi-Query Attention）—— 激进压缩

Shazeer（2019）提出：**Q 保留多头，但 K 和 V 只保留 1 个头**，所有 Q head 共享同一组 K、V：

$$\text{head}_i = \text{Attention}(QW_i^Q, KW^K, VW^V)$$

KV Cache 压缩比 = `num_heads`（如 32 头就缩小 32 倍）。

**代价**：表达能力下降，不同 Q head 无法关注不同的 K/V 子空间。实验发现质量损失明显，尤其在复杂推理任务上。PaLM、Falcon 系列使用了 MQA。

### GQA（Grouped-Query Attention）—— 质量与效率的平衡

Ainslie et al.（2023）提出折中方案：把 $h$ 个 Q head 分成 $g$ 组，每组共享一组 K、V：

$$g \text{ 组 KV heads}，每组对应 \frac{h}{g} \text{ 个 Q heads}$$

- $g = h$：退化为 MHA（无压缩）
- $g = 1$：退化为 MQA（最激进压缩）
- $g = h/8$（如 8 个 KV head 对应 64 个 Q head）：**Llama 3 的配置**

KV Cache 压缩比 = `h/g`，质量介于 MHA 和 MQA 之间，实践中接近 MHA 质量，KV Cache 缩小 4~8 倍。

**Llama 3 70B**：`num_heads=64`，`num_kv_heads=8`，GQA 压缩比 8 倍。Mistral、Gemma、Qwen 系列均使用 GQA。

### MLA（Multi-head Latent Attention）—— DeepSeek 的创新

DeepSeek-V2/V3 提出的新方案，思路完全不同：**不是减少 KV head 数量，而是对 K、V 做低秩压缩（Low-Rank KV Compression）**。

核心思路：把 K、V 先投影到一个低维的潜变量（latent）$c^{KV}$，推理时只缓存这个低维表示，需要时再还原：

$$c_t^{KV} = W^{DKV} h_t \quad (d^c \ll d_h \cdot n_h)$$

$$K_t = W^{UK} c_t^{KV}, \quad V_t = W^{UV} c_t^{KV}$$

KV Cache 只存低维 $c^{KV}$，而不是完整的 K 和 V，压缩比约为 **5.7 倍**（比 GQA 更激进），且**表达能力损失极小**（因为是可学习的低秩投影，而非简单 head 共享）。

DeepSeek-V2 使用 MLA，在 KV Cache 大幅减小的同时，性能接近甚至超过 MHA。

**对比总结**：

| 方案 | KV Cache 大小 | 表达能力 | 代表模型 |
|------|-------------|---------|---------|
| **MHA** | 基准（最大） | 最强 | GPT-3、早期 LLaMA |
| **MQA** | ÷ num_heads | 明显下降 | PaLM、Falcon |
| **GQA** | ÷ (num_heads/num_kv_heads) | 接近 MHA | Llama 3、Mistral、Qwen |
| **MLA** | ÷ ~5.7（低秩压缩） | 接近 MHA | DeepSeek-V2/V3 |

> **面试一句话总结**：MQA 激进但损质量，GQA 折中成工业主流，MLA 用低秩投影另辟蹊径，在压缩比和质量上同时做到更好，是 DeepSeek 系列的核心架构创新之一。

---

## 4. FlashAttention

**面试官可能会问：** FlashAttention 解决的是什么问题，它为什么能加速 attention 计算？

**回答要点：**

FlashAttention 解决的核心问题不是计算量（FLOPs），而是显存带宽瓶颈。标准 attention 的实现需要把 Q、K、V 矩阵以及中间的 attention score 矩阵（大小 N×N）反复在 HBM（高带宽显存）和 SRAM（片上缓存）之间搬运。对于长序列，这个 N×N 矩阵非常大，IO 开销远超实际计算开销，GPU 大部分时间在等数据搬运，而不是在算。

FlashAttention 的核心思想是 tiling + kernel fusion：把 Q、K、V 切成小块，在 SRAM 里完成整个 attention 计算（包括 softmax），不把中间结果写回 HBM，大幅减少 HBM 读写次数。计算量没变，但 IO 次数从 O(N²) 降到接近 O(N)，实际速度提升 2-4 倍，显存占用也从 O(N²) 降到 O(N)。FlashAttention 2 进一步优化了并行策略，FlashAttention 3 针对 Hopper 架构（H100）做了专项优化，现在是几乎所有主流推理框架的标配。

**深入追问：** FlashAttention 和 KV Cache 是什么关系，两者能同时用吗？

**回答要点：**

两者解决的是不同层面的问题，可以同时用。KV Cache 是在 decode 阶段避免重复计算历史 token 的 K/V；FlashAttention 是在 attention 计算本身（无论 prefill 还是 decode）优化显存 IO 效率。vLLM 就是同时使用了 PagedAttention（KV Cache 管理）和 FlashAttention（attention 计算加速）。

---

## 5. Speculative Decoding 与量化

**面试官可能会问：** Speculative Decoding 是什么，适合什么场景？

**回答要点：**

Speculative Decoding 的核心思想是用一个小的 draft model 快速生成多个候选 token，再用大的 target model 并行验证，接受正确的 token，拒绝错误的。为什么这样能加速？因为 decode 阶段是 memory-bound 的，target model 每次只生成一个 token，GPU 利用率很低。如果 draft model 猜对了 K 个 token，target model 一次 forward 就能验证并接受这 K 个 token，相当于用一次 forward 的时间完成了 K 个 token 的生成。

适合的场景是输出内容可预测性高的任务，比如代码补全、翻译、格式化输出，draft model 命中率高，收益才明显。不适合创意写作、开放式问答，draft model 命中率低，验证开销反而拖慢速度。另外高并发场景下，batch 本身已经能让 GPU 利用率上去，Speculative Decoding 的收益会被稀释，这是它最大的局限。

**深入追问：** 量化（INT8/INT4）的 trade-off 是什么，什么场景值得激进量化？

**回答要点：**

量化把模型权重从 fp16/bf16 压缩到 int8 或 int4，显存减半或减到四分之一，推理速度也有提升（尤其是 weight-only 量化在 decode 阶段收益明显，因为瓶颈就是显存带宽）。代价是精度损失。INT8 量化（如 bitsandbytes、GPTQ）通常精度损失可接受，适合大多数场景。INT4 量化精度损失更大，需要仔细评估。AWQ（Activation-aware Weight Quantization）通过保护重要权重，在 INT4 下精度损失比 GPTQ 更小。

值得激进量化的场景：成本敏感、对精度容忍度高（摘要、分类）、模型本身参数量大（70B 量化到 INT4 才能在单卡跑）。不值得激进量化的场景：精度敏感（代码生成、数学推理）、模型本身已经很小（7B INT4 可能精度掉得很明显）。

---

## 6. Streaming 与首 Token 延迟优化

**面试官可能会问：** Streaming 为什么不只是交互问题，它对系统有什么影响？

**回答要点：**

Streaming（流式输出）的本质是把 decode 阶段每生成一个 token 就立刻推送给客户端，而不是等全部生成完再返回。从用户体验角度，Streaming 把"等待感"从总完成时延降到首 token 延迟，用户感知到的响应速度大幅提升。对于生成 500 token 的回复，总完成时延可能 10 秒，但首 token 延迟可能只有 0.5 秒，用户体验完全不同。

但 Streaming 也会放大系统压力：每个请求都要维持一个长连接（SSE 或 WebSocket），并发连接数上升，服务端需要管理大量 in-flight 请求的状态。不适合 Streaming 的场景包括：需要对完整输出做结构化解析（JSON 提取、函数调用）、需要先审核再展示、批量离线任务。

**深入追问：** 首 token 延迟高，通常应该从哪几个方向排查？

**回答要点：**

首先看 Prefill 阶段：prompt 是不是太长，有没有开启 prefix cache，prefix cache 命中率如何。其次看排队延迟：请求是不是在队列里等了很久才开始 prefill，这说明并发太高或调度器有问题。再看网络和序列化开销：请求从客户端到推理服务的网络延迟以及 tokenization 时间。最后看是否有冷启动问题：模型是否刚加载，KV Cache 是否是冷的。

---

## 7. 限流、熔断与稳定性

**面试官可能会问：** AI 服务为什么比普通接口更容易被并发打爆，限流和熔断应该怎么设计？

**回答要点：**

AI 服务的特殊性在于：单个请求的资源消耗极高（GPU 显存、计算时间），且请求时长不固定，生成 10 token 和生成 1000 token 的资源消耗差 100 倍。普通接口的 QPS 限流在这里不够用，因为 QPS 相同但 token 数差异大时，资源消耗可以差几十倍。

限流策略应该多层叠加：请求级限流基于 QPS 或并发连接数，防止瞬时流量冲击；Token 级限流按 input/output token 数限流，更准确反映资源消耗，OpenAI 的 TPM（tokens per minute）就是这个思路；用户级限流对单个用户或租户做配额控制，防止单用户打爆整个服务。

熔断设计：当推理服务的错误率或延迟超过阈值，熔断器打开，直接返回降级响应，而不是让请求继续排队堆积，避免雪崩。降级策略可以是切换到更小的模型、返回缓存结果、拒绝非核心请求。重试要谨慎，模型调用失败重试会放大负载，应该加指数退避和 jitter，并且区分可重试错误（超时、限流）和不可重试错误（输入违规、模型错误）。

**深入追问：** 线上推理服务通常要监控哪些核心指标？

**回答要点：**

分三层来看。延迟层：TTFT（首 token 延迟）、ITL（token 间延迟）、E2E latency，看 P50/P95/P99，P99 抖动往往是排队或 GC 问题。吞吐层：tokens/s（生成吞吐）、QPS、并发请求数、队列长度，队列长度持续增长是过载的早期信号。资源层：GPU 利用率、显存占用、KV Cache 使用率，GPU 利用率低说明 batch 太小或调度有问题，显存占用接近上限说明快 OOM 了。

---

## 8. 推理性能项目深挖

**面试官可能会问：** 讲一个你做过的推理性能优化项目，链路是怎么设计的，遇到了什么 bad case，如果重做会优先改哪层？

**回答要点：**

链路设计层面，一个典型的推理服务链路是：客户端请求 → 网关（限流、鉴权、路由）→ 编排层（prompt 构建、工具调用编排）→ 推理服务（vLLM 或 TGI）→ 后处理（结构化解析、审核）→ 流式返回。关键设计决策包括：是否开启 prefix cache（system prompt 长时必开）、batch size 策略（低延迟场景用小 batch，高吞吐场景用大 batch）、是否做模型路由（简单请求走小模型，复杂请求走大模型）。

Bad case 层面，最常见的几类：KV Cache OOM，并发上来后显存被 KV Cache 打满，根因通常是没有做 KV Cache 上限控制或 max_new_tokens 设置过大，解法是限制单请求最大 token 数并配置 vLLM 的 gpu_memory_utilization 参数留出余量；首 token 延迟抖动，排查发现是 prefix cache 命中率下降（system prompt 被频繁修改），解法是固定 system prompt，把动态内容放到 user message；量化后精度下降，INT4 量化后代码生成任务通过率明显下降，解法是换用 AWQ 量化，并对精度敏感任务单独保留 fp16 模型做路由。

如果重做，优先改的层是 KV Cache 管理和 prefix cache 策略，这是性价比最高的优化，不需要改模型，只需要正确配置和固定 prompt 结构，收益立竿见影。其次是限流和熔断，这是稳定性的底线。最后才考虑量化和 Speculative Decoding，这些需要仔细评估精度和场景匹配度，不是所有场景都值得上。

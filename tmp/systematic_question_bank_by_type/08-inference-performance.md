# 推理部署与性能优化

重要性：

- 高频程度：高
- 对应原始题库：[08-inference-performance.md](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/raw_question_source_by_type/08-inference-performance.md)

## 这一类在考什么

考的是你是否真正理解上线系统的性能瓶颈，而不是只会说几个优化名词。

## 这一类的核心主线

1. `先拆链路`
2. `再定瓶颈`
3. `再说优化`
4. `最后讲观测`

## 必会主问题

1. 端到端延迟由哪些环节组成？
2. `vLLM`、`KV Cache`、`Batching`、`Streaming` 各解决什么问题？
3. 显存不足时有哪些优化手段？
4. 量化、缓存、模型路由、Prompt 裁剪各适合什么问题？
5. 为什么线上必须做限流、超时、重试、熔断？
6. 模型路由如何平衡效果、成本、时延？
7. Prompt 裁剪为什么也是性能优化？

## 高频追问

1. `FlashAttention`、`PagedAttention` 大概解决什么瓶颈？
2. 延迟高时如何判断是检索慢、工具慢还是推理慢？
3. 什么时候值得做异步化和任务队列化？

## 标准回答抓手

- 先按链路拆：`检索 -> 工具 -> 模型推理 -> 后处理`
- 优化不要只盯模型
- 一定讲 `观测、告警、灰度、回滚`

## 常见失分点

- 把性能优化都归因于模型
- 说不清端到端 latency 拆解
- 不讲成本和效果 tradeoff

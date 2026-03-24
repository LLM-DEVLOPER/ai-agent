# CSDN 采集稿

采集时间：2026-03-24

## 来源列表

1. 100 道大模型应用开发面试题精选
   https://blog.csdn.net/teddyandwolf/article/details/148159001
   日期：2025-05-23
2. AI 大模型 Agent 面试精选：15 道高频题助你轻松通关
   https://blog.csdn.net/lvaolan168/article/details/156113926
   日期：2026-03-06
3. AI 大模型 Agent 面试精选：高频面试题+详解
   https://blog.csdn.net/Z4400840/article/details/155563244
   日期：2025-12-04
4. 一次性捋清楚吧，吃透大模型 RAG 面试题
   https://blog.csdn.net/m0_59235245/article/details/138229314
   日期：2024-04-26
5. 2025 年 AI 大模型面试必看：RAG 核心问题深度解析
   https://blog.csdn.net/ytt0523_com/article/details/150588279
6. 2025 年最全汇总：国内 24 家大模型面试经验分享
   https://blog.csdn.net/a2875254060/article/details/147589721
7. 大模型应用开发面试宝典：22 家公司真实面试经验与技术考点总结
   https://blog.csdn.net/2401_85390073/article/details/151832648
   日期：2025-09-18

## 题目整理

### 1. Agent 架构

- 什么是 AI Agent？一个完整 Agent 的核心组件有哪些？
- Agent 和传统 LLM 应用有什么差别？
- 生产级 Agent 系统应该怎么设计？
- 为什么要手搓 Agent，而不是直接套现成框架？
- 什么时候应该从单 Agent 升级到多 Agent？

### 2. Prompt / Function Calling / 安全

- Function Calling 和 Tool Use 的差别是什么？
- Function Call 的能力在模型层面通常怎么训练出来？
- 如何控制模型输出为稳定的 JSON / schema 格式？
- 什么是 Prompt Injection，典型攻击路径有哪些？
- 如果用户输入刻意诱导 Agent 泄露系统提示词，你怎么防？

### 3. RAG

- RAG 是什么？相比纯生成链路最大的收益是什么？
- RAG 标准工作流有哪些步骤？
- Chunking 常见策略有哪些，分块大小怎么选？
- 如何提升 RAG 的召回率和最终正确率？
- 当 RAG 回答不准时，应该怎么排障？
- 什么时候要加 query rewrite、rerank、metadata filter？
- RAG 与微调各自适合解决什么问题？

### 4. 记忆、规划、ReAct

- Agent 的记忆管理通常怎么分层？
- ReAct 的核心思想是什么？
- Agent 的任务规划一般怎么做？
- 规划失败、工具失败、上下文过长时分别如何恢复？

### 5. 多 Agent

- 多 Agent 系统的主要优势是什么？
- 多 Agent 之间如何通信与协作？
- 多 Agent 场景中如何避免循环调度和状态失控？

### 6. 评测

- Agent 性能一般怎么评估？
- 模型评估有哪些常见方法？
- RAG 系统整体应该用哪些指标评估？
- 用户体验差，到底是检索差、生成差还是交互差，怎么拆分？

### 7. 部署与监控

- 大模型服务的扩展性挑战有哪些？
- 性能监控应该关注哪些关键指标？
- 如何处理 API 限流与速率限制？
- 端到端延迟一般从哪些环节优化？
- Agent 服务的高可用和稳健性如何保证？

### 8. 模型基础

- 当前主流开源 LLM 体系有哪些？
- Prefix LM 和 Causal LM 的差异是什么？
- Attention 和 Self-Attention 的区别是什么？
- 多头注意力为什么有效？
- 位置编码的作用是什么？

### 9. 训练与微调

- LLM 的训练目标通常是什么？
- 指令微调和标准微调的差异是什么？
- 微调数据集怎么选？常见挑战有哪些？
- RLHF 在训练链路里起什么作用？
- LoRA 的原理是什么，适用边界在哪里？

### 10. 应用设计

- 如何评估和优化大模型应用的用户体验？
- 业务接入大模型后，如何平衡效果、成本和时延？
- 如果线上 bad case 很多，你先改 Prompt、改检索、还是加后处理？

## 观察

- CSDN 的内容题库化明显，覆盖广，适合补基础面与结构化答题骨架。
- 高频主题已经收敛到 `RAG + Agent + Prompt/函数调用 + 评测 + 部署监控`。
- 真正容易拉开差距的不是基础定义题，而是“排障题、上线题、指标题、成本题”。

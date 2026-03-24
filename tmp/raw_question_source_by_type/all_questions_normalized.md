# 归一化问题候选池

整理时间：2026-03-24

说明：

- 数据来源：`all_questions_flattened.md`
- 这是第一轮规则归一化，不是语义模型归一化
- 目标：为后续筛 `top100` 提供标准题候选池
- 原始问题总数：`647`
- 当前归一化后候选数：`255`

| ID | 归一化题目 | 归并次数 | 来源面经数 | 分类倾向 | 典型原题示例 |
| --- | --- | ---: | ---: | --- | --- |
| 1 | 项目介绍与项目深挖 | 62 | 43 | 系统设计与项目深挖 | 项目追问 |
| 2 | 推理部署与性能优化 | 50 | 29 | 推理部署与性能优化 | `PagedAttention` |
| 3 | 工具调用与 Function Calling | 32 | 26 | 工具调用、Function Calling 与 MCP | 工具调用和流程编排 |
| 4 | 上下文工程与多轮对话 | 29 | 26 | 记忆、上下文工程与多轮对话 | 上下文接口怎么修改 |
| 5 | Agent 记忆设计 | 25 | 20 | 记忆、上下文工程与多轮对话 | CUDA memory model |
| 6 | 检索与召回优化 | 25 | 19 | 检索、召回与向量库 | 介绍 GraphRAG，难点是什么，增量场景怎么做 |
| 7 | 评测体系 | 22 | 19 | 评测、幻觉治理与 bad case | RAG 评测怎么做 |
| 8 | 工程化与并发治理 | 19 | 18 | 工程化、后端服务与并发治理 | Spring AI 怎么用 |
| 9 | Transformer 与注意力机制 | 15 | 11 | 模型基础、Transformer、LoRA 与 RLHF | Transformer 架构有哪些关键机制 |
| 10 | LoRA 与微调 | 15 | 9 | 模型基础、Transformer、LoRA 与 RLHF | 金融场景里 RAG 和微调怎么选 |
| 11 | 向量库与索引选型 | 14 | 11 | 检索、召回与向量库 | pgvector 的使用 |
| 12 | 意图识别与任务规划 | 12 | 12 | Prompt、意图识别、规划与 ReAct | 意图识别 |
| 13 | Agent 定义与架构 | 12 | 11 | Agent 基础与系统架构 | 多智能体怎么设计 |
| 14 | 编码题与手撕题 | 12 | 9 | 编码题与手撕题 | LRU 机制 |
| 15 | RLHF / DPO / PPO / 强化学习 | 12 | 7 | 模型基础、Transformer、LoRA 与 RLHF | DeepResearch 和强化学习怎么结合应用 |
| 16 | 多模态与截图理解 | 10 | 6 | 多模态 | Playwright 截图时报错或渲染失败怎么办 |
| 17 | MCP | 9 | 9 | 工具调用、Function Calling 与 MCP | MCP 是什么 |
| 18 | Prompt 设计与优化 | 9 | 7 | Prompt、意图识别、规划与 ReAct | Prompt 模板怎么设计 |
| 19 | 多 Agent 协作 | 8 | 6 | 多 Agent 协作 | 如何让多个 Agent 协同工作，举一个具体机制 |
| 20 | 幻觉治理与 bad case | 7 | 7 | 评测、幻觉治理与 bad case | 幻觉治理怎么做 |
| 21 | RAG 链路设计 | 5 | 5 | RAG 全链路 | RAG 链路怎么搭 |
| 22 | RAG 分块策略 | 4 | 4 | 检索、召回与向量库 | RAG 分块怎么做 |
| 23 | Qwen 与开源模型理解 | 3 | 2 | 模型基础、Transformer、LoRA 与 RLHF | Qwen 各代的重要突破 |
| 24 | 未完全归一化::LangGraph 怎么用 | 2 | 2 | 其他未稳定归类问题 | LangGraph 怎么用 |
| 25 | 未完全归一化::RAG | 2 | 2 | RAG 全链路 | RAG |
| 26 | 未完全归一化::`MLA` | 2 | 2 | 其他未稳定归类问题 | `MLA` |
| 27 | 未完全归一化::`PD` 分离 | 2 | 2 | 其他未稳定归类问题 | `PD` 分离 |
| 28 | 未完全归一化::AF / PD 分离是什么 | 1 | 1 | 其他未稳定归类问题 | AF / PD 分离是什么 |
| 29 | 未完全归一化::AI Agent 前端架构怎么设计 | 1 | 1 | Agent 基础与系统架构 | AI Agent 前端架构怎么设计 |
| 30 | 未完全归一化::AI Chat 组件设计 | 1 | 1 | 其他未稳定归类问题 | AI Chat 组件设计 |
| 31 | 未完全归一化::AI 应用适合哪些业务场景 | 1 | 1 | 系统设计与项目深挖 | AI 应用适合哪些业务场景 |
| 32 | 未完全归一化::AI 时代下，前端工程师的角色发生了哪些变化 | 1 | 1 | 其他未稳定归类问题 | AI 时代下，前端工程师的角色发生了哪些变化 |
| 33 | 未完全归一化::AI 流式输出如何实现 | 1 | 1 | 其他未稳定归类问题 | AI 流式输出如何实现 |
| 34 | 未完全归一化::AI 聊天产品的前端 UI 应该关注哪些关键点 | 1 | 1 | 其他未稳定归类问题 | AI 聊天产品的前端 UI 应该关注哪些关键点 |
| 35 | 未完全归一化::API 网关怎么做 | 1 | 1 | 其他未稳定归类问题 | API 网关怎么做 |
| 36 | 未完全归一化::Agent workflow 怎么设计 | 1 | 1 | Agent 基础与系统架构 | Agent workflow 怎么设计 |
| 37 | 未完全归一化::Agent 全链路怎么设计 | 1 | 1 | Agent 基础与系统架构 | Agent 全链路怎么设计 |
| 38 | 未完全归一化::Agent 和 RAG 的关系与边界 | 1 | 1 | RAG 全链路 | Agent 和 RAG 的关系与边界 |
| 39 | 未完全归一化::Agent 哪些模块最容易在线上出问题，如何监控与定位 | 1 | 1 | Agent 基础与系统架构 | Agent 哪些模块最容易在线上出问题，如何监控与定位 |
| 40 | 未完全归一化::Agent 在 RAG 链路中的位置 | 1 | 1 | RAG 全链路 | Agent 在 RAG 链路中的位置 |
| 41 | 未完全归一化::Agent 在实际业务里如何组织流程 | 1 | 1 | 系统设计与项目深挖 | Agent 在实际业务里如何组织流程 |
| 42 | 未完全归一化::Agent 在金融问答或投研辅助里适不适合，边界在哪里 | 1 | 1 | Agent 基础与系统架构 | Agent 在金融问答或投研辅助里适不适合，边界在哪里 |
| 43 | 未完全归一化::Agent 工作流如何组织 | 1 | 1 | Agent 基础与系统架构 | Agent 工作流如何组织 |
| 44 | 未完全归一化::Agent 工程实现细节 | 1 | 1 | Agent 基础与系统架构 | Agent 工程实现细节 |
| 45 | 未完全归一化::Agent 常见模式有哪些，适合什么任务 | 1 | 1 | Agent 基础与系统架构 | Agent 常见模式有哪些，适合什么任务 |
| 46 | 未完全归一化::Agent 开发相关问题 | 1 | 1 | Agent 基础与系统架构 | Agent 开发相关问题 |
| 47 | 未完全归一化::Agent 的改进方向是什么 | 1 | 1 | Agent 基础与系统架构 | Agent 的改进方向是什么 |
| 48 | 未完全归一化::Agent 的编排怎么做，用了什么模式，如何调度 | 1 | 1 | Agent 基础与系统架构 | Agent 的编排怎么做，用了什么模式，如何调度 |
| 49 | 未完全归一化::Agent 算法在业务落地中的挑战 | 1 | 1 | 系统设计与项目深挖 | Agent 算法在业务落地中的挑战 |
| 50 | 未完全归一化::CAP 理解 | 1 | 1 | 其他未稳定归类问题 | CAP 理解 |
| 51 | 未完全归一化::CUDA GEMM 基础 | 1 | 1 | 其他未稳定归类问题 | CUDA GEMM 基础 |
| 52 | 未完全归一化::CUDA `GEMM` | 1 | 1 | 其他未稳定归类问题 | CUDA `GEMM` |
| 53 | 未完全归一化::CUDA `prefix-sum` | 1 | 1 | 其他未稳定归类问题 | CUDA `prefix-sum` |
| 54 | 未完全归一化::Chat UI 如何设计滚动与流式体验 | 1 | 1 | 其他未稳定归类问题 | Chat UI 如何设计滚动与流式体验 |
| 55 | 未完全归一化::ConcurrentHashMap 与 HashMap 区别 | 1 | 1 | 其他未稳定归类问题 | ConcurrentHashMap 与 HashMap 区别 |
| 56 | 未完全归一化::Context Window 限制如何处理 | 1 | 1 | 其他未稳定归类问题 | Context Window 限制如何处理 |
| 57 | 未完全归一化::Coze Agent 的目的是什么 | 1 | 1 | Agent 基础与系统架构 | Coze Agent 的目的是什么 |
| 58 | 未完全归一化::DIN 模型相比传统推荐模型有什么改进 | 1 | 1 | 其他未稳定归类问题 | DIN 模型相比传统推荐模型有什么改进 |
| 59 | 未完全归一化::GPU / CUDA 基础 | 1 | 1 | 其他未稳定归类问题 | GPU / CUDA 基础 |
| 60 | 未完全归一化::HTTP 长连接和短连接的区别 | 1 | 1 | 其他未稳定归类问题 | HTTP 长连接和短连接的区别 |
| 61 | 未完全归一化::HTTPS 基础 | 1 | 1 | 其他未稳定归类问题 | HTTPS 基础 |
| 62 | 未完全归一化::HashMap 底层实现、扩容、冲突处理 | 1 | 1 | 其他未稳定归类问题 | HashMap 底层实现、扩容、冲突处理 |
| 63 | 未完全归一化::Java / Go 多态相关问题 | 1 | 1 | 其他未稳定归类问题 | Java / Go 多态相关问题 |
| 64 | 未完全归一化::K8S 如何使用 | 1 | 1 | 其他未稳定归类问题 | K8S 如何使用 |
| 65 | 未完全归一化::Kafka 的使用场景 | 1 | 1 | 系统设计与项目深挖 | Kafka 的使用场景 |
| 66 | 未完全归一化::L1 正则和 L2 正则的区别是什么，为什么 L1 能产生稀疏性 | 1 | 1 | 其他未稳定归类问题 | L1 正则和 L2 正则的区别是什么，为什么 L1 能产生稀疏性 |
| 67 | 未完全归一化::LangGraph 和 Agent 编排怎么做 | 1 | 1 | Agent 基础与系统架构 | LangGraph 和 Agent 编排怎么做 |
| 68 | 未完全归一化::LangGraph 的使用场景 | 1 | 1 | 系统设计与项目深挖 | LangGraph 的使用场景 |
| 69 | 未完全归一化::LangGraph 的应用 | 1 | 1 | 其他未稳定归类问题 | LangGraph 的应用 |
| 70 | 未完全归一化::LangGraph 的核心思想是什么 | 1 | 1 | 其他未稳定归类问题 | LangGraph 的核心思想是什么 |
| 71 | 未完全归一化::LangGraph 适用于什么场景，构建 Agent 有哪几种方式 | 1 | 1 | 系统设计与项目深挖 | LangGraph 适用于什么场景，构建 Agent 有哪几种方式 |
| 72 | 未完全归一化::MVCC 细节 | 1 | 1 | 其他未稳定归类问题 | MVCC 细节 |
| 73 | 未完全归一化::Multi-Agent 和 Coze 的理解 | 1 | 1 | Agent 基础与系统架构 | Multi-Agent 和 Coze 的理解 |
| 74 | 未完全归一化::Multi-agent 中 plan 的设计思路是什么 | 1 | 1 | Agent 基础与系统架构 | Multi-agent 中 plan 的设计思路是什么 |
| 75 | 未完全归一化::Multi-agent 如何设计 | 1 | 1 | Agent 基础与系统架构 | Multi-agent 如何设计 |
| 76 | 未完全归一化::MySQL / PostgreSQL 对比与使用 | 1 | 1 | 其他未稳定归类问题 | MySQL / PostgreSQL 对比与使用 |
| 77 | 未完全归一化::MySQL ACID | 1 | 1 | 其他未稳定归类问题 | MySQL ACID |
| 78 | 未完全归一化::MySQL binlog 原理 | 1 | 1 | 其他未稳定归类问题 | MySQL binlog 原理 |
| 79 | 未完全归一化::MySQL 为什么使用 B+ 树 | 1 | 1 | 其他未稳定归类问题 | MySQL 为什么使用 B+ 树 |
| 80 | 未完全归一化::MySQL 事务隔离与一致性 | 1 | 1 | 其他未稳定归类问题 | MySQL 事务隔离与一致性 |
| 81 | 未完全归一化::MySQL 相关基础 | 1 | 1 | 其他未稳定归类问题 | MySQL 相关基础 |
| 82 | 未完全归一化::MySQL 相关问题 | 1 | 1 | 其他未稳定归类问题 | MySQL 相关问题 |
| 83 | 未完全归一化::MySQL 锁 | 1 | 1 | 其他未稳定归类问题 | MySQL 锁 |
| 84 | 未完全归一化::OpenClaw 怎么看 | 1 | 1 | 其他未稳定归类问题 | OpenClaw 怎么看 |
| 85 | 未完全归一化::PAI、igraph、GraphScope、图数据库的区别 | 1 | 1 | 检索、召回与向量库 | PAI、igraph、GraphScope、图数据库的区别 |
| 86 | 未完全归一化::PD 分离是什么 | 1 | 1 | 其他未稳定归类问题 | PD 分离是什么 |
| 87 | 未完全归一化::Query 改写策略 | 1 | 1 | 其他未稳定归类问题 | Query 改写策略 |
| 88 | 未完全归一化::RAG 优化 | 1 | 1 | RAG 全链路 | RAG 优化 |
| 89 | 未完全归一化::RAG 优化怎么做 | 1 | 1 | RAG 全链路 | RAG 优化怎么做 |
| 90 | 未完全归一化::RAG 优化有哪些思路 | 1 | 1 | RAG 全链路 | RAG 优化有哪些思路 |
| 91 | 未完全归一化::RAG 全流程怎么设计 | 1 | 1 | RAG 全链路 | RAG 全流程怎么设计 |
| 92 | 未完全归一化::RAG 切片策略如何选择 | 1 | 1 | RAG 全链路 | RAG 切片策略如何选择 |
| 93 | 未完全归一化::RAG 切片策略怎么选 | 1 | 1 | RAG 全链路 | RAG 切片策略怎么选 |
| 94 | 未完全归一化::RAG 在大模型应用中的作用和局限 | 1 | 1 | RAG 全链路 | RAG 在大模型应用中的作用和局限 |
| 95 | 未完全归一化::RAG 怎么做 | 1 | 1 | RAG 全链路 | RAG 怎么做 |
| 96 | 未完全归一化::RAG 怎么接 | 1 | 1 | RAG 全链路 | RAG 怎么接 |
| 97 | 未完全归一化::RAG 怎么设计 | 1 | 1 | RAG 全链路 | RAG 怎么设计 |
| 98 | 未完全归一化::RAG 数据库存什么 | 1 | 1 | RAG 全链路 | RAG 数据库存什么 |
| 99 | 未完全归一化::RAG 整体链路 | 1 | 1 | RAG 全链路 | RAG 整体链路 |
| 100 | 未完全归一化::RAG 是否还有必要 | 1 | 1 | RAG 全链路 | RAG 是否还有必要 |
| 101 | 未完全归一化::RAG 有哪些分类 | 1 | 1 | RAG 全链路 | RAG 有哪些分类 |
| 102 | 未完全归一化::RAG 的基本链路 | 1 | 1 | RAG 全链路 | RAG 的基本链路 |
| 103 | 未完全归一化::RAG 的整体链路如何设计 | 1 | 1 | RAG 全链路 | RAG 的整体链路如何设计 |
| 104 | 未完全归一化::RAG 知识库系统全链路设计 | 1 | 1 | RAG 全链路 | RAG 知识库系统全链路设计 |
| 105 | 未完全归一化::RAG 遇到模型缺失电商知识时怎么补 | 1 | 1 | RAG 全链路 | RAG 遇到模型缺失电商知识时怎么补 |
| 106 | 未完全归一化::RAG 链路怎么设计 | 1 | 1 | RAG 全链路 | RAG 链路怎么设计 |
| 107 | 未完全归一化::RL 或偏好优化怎么理解 | 1 | 1 | 其他未稳定归类问题 | RL 或偏好优化怎么理解 |
| 108 | 未完全归一化::RL 相关训练方法 | 1 | 1 | 模型基础、Transformer、LoRA 与 RLHF | RL 相关训练方法 |
| 109 | 未完全归一化::Redis / MQ 在 AI 应用里的作用 | 1 | 1 | 其他未稳定归类问题 | Redis / MQ 在 AI 应用里的作用 |
| 110 | 未完全归一化::Redis ZSET、AOF、RDB、AOF 重写 | 1 | 1 | 其他未稳定归类问题 | Redis ZSET、AOF、RDB、AOF 重写 |
| 111 | 未完全归一化::Redis 三剑客 | 1 | 1 | 其他未稳定归类问题 | Redis 三剑客 |
| 112 | 未完全归一化::Redis 出现大 key、大 value 会带来哪些问题 | 1 | 1 | 其他未稳定归类问题 | Redis 出现大 key、大 value 会带来哪些问题 |
| 113 | 未完全归一化::Redis 在增量更新环节如何使用，是否存在大 key、大 value 问题 | 1 | 1 | 其他未稳定归类问题 | Redis 在增量更新环节如何使用，是否存在大 key、大 value 问题 |
| 114 | 未完全归一化::Redis 基础与使用 | 1 | 1 | 其他未稳定归类问题 | Redis 基础与使用 |
| 115 | 未完全归一化::ReentrantLock、公平非公平锁、AQS、CLH、自愈 | 1 | 1 | 其他未稳定归类问题 | ReentrantLock、公平非公平锁、AQS、CLH、自愈 |
| 116 | 未完全归一化::SQL：统计每个商家的评论数并去重 | 1 | 1 | 其他未稳定归类问题 | SQL：统计每个商家的评论数并去重 |
| 117 | 未完全归一化::SSE 中断续传如何设计 | 1 | 1 | 其他未稳定归类问题 | SSE 中断续传如何设计 |
| 118 | 未完全归一化::SSE 和 WebSocket 的区别 | 1 | 1 | 其他未稳定归类问题 | SSE 和 WebSocket 的区别 |
| 119 | 未完全归一化::Sequence Packing 的原理和收益 | 1 | 1 | 其他未稳定归类问题 | Sequence Packing 的原理和收益 |
| 120 | 未完全归一化::TP 并行如何做 | 1 | 1 | 其他未稳定归类问题 | TP 并行如何做 |
| 121 | 未完全归一化::TaskRunner / 任务编排怎么设计 | 1 | 1 | 其他未稳定归类问题 | TaskRunner / 任务编排怎么设计 |
| 122 | 未完全归一化::TensorRT 怎么优化 | 1 | 1 | 其他未稳定归类问题 | TensorRT 怎么优化 |
| 123 | 未完全归一化::Tool 调用链路怎么设计 | 1 | 1 | 其他未稳定归类问题 | Tool 调用链路怎么设计 |
| 124 | 未完全归一化::Top-k、Top-p 的实现原理 | 1 | 1 | 模型基础、Transformer、LoRA 与 RLHF | Top-k、Top-p 的实现原理 |
| 125 | 未完全归一化::Triton / CUDA | 1 | 1 | 其他未稳定归类问题 | Triton / CUDA |
| 126 | 未完全归一化::WebWorker 在前端 AI 应用里怎么用 | 1 | 1 | 其他未稳定归类问题 | WebWorker 在前端 AI 应用里怎么用 |
| 127 | 未完全归一化::Wide&Deep 模型原理是什么，Wide 和 Deep 分别解决什么问题 | 1 | 1 | 其他未稳定归类问题 | Wide&Deep 模型原理是什么，Wide 和 Deep 分别解决什么问题 |
| 128 | 未完全归一化::XSS 风险怎么处理 | 1 | 1 | 其他未稳定归类问题 | XSS 风险怎么处理 |
| 129 | 未完全归一化::`GEMM` | 1 | 1 | 其他未稳定归类问题 | `GEMM` |
| 130 | 未完全归一化::`IPC` | 1 | 1 | 其他未稳定归类问题 | `IPC` |
| 131 | 未完全归一化::`SmoothQuant` | 1 | 1 | 其他未稳定归类问题 | `SmoothQuant` |
| 132 | 未完全归一化::`all-reduce` 通信 | 1 | 1 | 其他未稳定归类问题 | `all-reduce` 通信 |
| 133 | 未完全归一化::`graph fusion` | 1 | 1 | 其他未稳定归类问题 | `graph fusion` |
| 134 | 未完全归一化::`prefix cache` | 1 | 1 | 其他未稳定归类问题 | `prefix cache` |
| 135 | 未完全归一化::`prefix caching` | 1 | 1 | 其他未稳定归类问题 | `prefix caching` |
| 136 | 未完全归一化::`sglang` | 1 | 1 | 其他未稳定归类问题 | `sglang` |
| 137 | 未完全归一化::`speculative decoding` | 1 | 1 | 其他未稳定归类问题 | `speculative decoding` |
| 138 | 未完全归一化::`static_cast`、`dynamic_cast`、`const_cast`、`reinterpret_cast` 的区别与底层含义 | 1 | 1 | 其他未稳定归类问题 | `static_cast`、`dynamic_cast`、`const_cast`、`reinterpret_cast` 的区别与底层含义 |
| 139 | 未完全归一化::agent 模块设计 | 1 | 1 | Agent 基础与系统架构 | agent 模块设计 |
| 140 | 未完全归一化::emoji 表情包存储时涉及哪些 MySQL 存储相关知识 | 1 | 1 | 其他未稳定归类问题 | emoji 表情包存储时涉及哪些 MySQL 存储相关知识 |
| 141 | 未完全归一化::fallback 机制如何设计 | 1 | 1 | 其他未稳定归类问题 | fallback 机制如何设计 |
| 142 | 未完全归一化::k8s 在 Agent 系统里的使用场景 | 1 | 1 | 系统设计与项目深挖 | k8s 在 Agent 系统里的使用场景 |
| 143 | 未完全归一化::kernel 优化 | 1 | 1 | 其他未稳定归类问题 | kernel 优化 |
| 144 | 未完全归一化::like 查询是否会失效 | 1 | 1 | 其他未稳定归类问题 | like 查询是否会失效 |
| 145 | 未完全归一化::reduce 优化 | 1 | 1 | 其他未稳定归类问题 | reduce 优化 |
| 146 | 未完全归一化::token 相关基础 | 1 | 1 | 其他未稳定归类问题 | token 相关基础 |
| 147 | 未完全归一化::tool 参数治理怎么做 | 1 | 1 | 其他未稳定归类问题 | tool 参数治理怎么做 |
| 148 | 未完全归一化::topk 截断怎么选 | 1 | 1 | 其他未稳定归类问题 | topk 截断怎么选 |
| 149 | 未完全归一化::workflow 是什么 | 1 | 1 | Agent 基础与系统架构 | workflow 是什么 |
| 150 | 未完全归一化::不同设备字段特征不一致时，怎么做统一化训练 | 1 | 1 | 模型基础、Transformer、LoRA 与 RLHF | 不同设备字段特征不一致时，怎么做统一化训练 |
| 151 | 未完全归一化::业务编排怎么做 | 1 | 1 | 系统设计与项目深挖 | 业务编排怎么做 |
| 152 | 未完全归一化::个人基本情况，有无实习经历 | 1 | 1 | 其他未稳定归类问题 | 个人基本情况，有无实习经历 |
| 153 | 未完全归一化::为什么想做金融大模型 | 1 | 1 | 其他未稳定归类问题 | 为什么想做金融大模型 |
| 154 | 未完全归一化::为什么选择这些数据策略 | 1 | 1 | 其他未稳定归类问题 | 为什么选择这些数据策略 |
| 155 | 未完全归一化::为什么需要 RAG | 1 | 1 | RAG 全链路 | 为什么需要 RAG |
| 156 | 未完全归一化::人类反馈如何被 Agent 消化，是否用 RL 更新策略 | 1 | 1 | Agent 基础与系统架构 | 人类反馈如何被 Agent 消化，是否用 RL 更新策略 |
| 157 | 未完全归一化::什么是 Modular Agent | 1 | 1 | Agent 基础与系统架构 | 什么是 Modular Agent |
| 158 | 未完全归一化::介绍实习公司中负责的关键词命中系统、文档提取系统的特色功能 | 1 | 1 | 其他未稳定归类问题 | 介绍实习公司中负责的关键词命中系统、文档提取系统的特色功能 |
| 159 | 未完全归一化::从前端转 Agent 岗位的理解 | 1 | 1 | Agent 基础与系统架构 | 从前端转 Agent 岗位的理解 |
| 160 | 未完全归一化::从大模型侧要做什么来适配 Agent | 1 | 1 | Agent 基础与系统架构 | 从大模型侧要做什么来适配 Agent |
| 161 | 未完全归一化::传统 RAG 的痛点有哪些 | 1 | 1 | RAG 全链路 | 传统 RAG 的痛点有哪些 |
| 162 | 未完全归一化::做 MySQL 治理时有哪些具体优化收获 | 1 | 1 | 其他未稳定归类问题 | 做 MySQL 治理时有哪些具体优化收获 |
| 163 | 未完全归一化::做一个应用型 LLM 系统时，如何权衡效果、时延和成本 | 1 | 1 | 其他未稳定归类问题 | 做一个应用型 LLM 系统时，如何权衡效果、时延和成本 |
| 164 | 未完全归一化::关键词命中系统优化的核心目标是什么，具体如何优化 | 1 | 1 | 其他未稳定归类问题 | 关键词命中系统优化的核心目标是什么，具体如何优化 |
| 165 | 未完全归一化::分库分表 | 1 | 1 | 其他未稳定归类问题 | 分库分表 |
| 166 | 未完全归一化::前端如何做 AI 质量监控 | 1 | 1 | 其他未稳定归类问题 | 前端如何做 AI 质量监控 |
| 167 | 未完全归一化::动态链接库依赖顺序 | 1 | 1 | 其他未稳定归类问题 | 动态链接库依赖顺序 |
| 168 | 未完全归一化::协程基础 | 1 | 1 | 其他未稳定归类问题 | 协程基础 |
| 169 | 未完全归一化::单体还是微服务怎么选 | 1 | 1 | 其他未稳定归类问题 | 单体还是微服务怎么选 |
| 170 | 未完全归一化::可用性设计 | 1 | 1 | 其他未稳定归类问题 | 可用性设计 |
| 171 | 未完全归一化::各步骤原理 | 1 | 1 | 其他未稳定归类问题 | 各步骤原理 |
| 172 | 未完全归一化::后端基础 | 1 | 1 | 其他未稳定归类问题 | 后端基础 |
| 173 | 未完全归一化::后端基础追问 | 1 | 1 | 其他未稳定归类问题 | 后端基础追问 |
| 174 | 未完全归一化::后端基础问题 | 1 | 1 | 其他未稳定归类问题 | 后端基础问题 |
| 175 | 未完全归一化::向量嵌入怎么做 | 1 | 1 | 其他未稳定归类问题 | 向量嵌入怎么做 |
| 176 | 未完全归一化::图数据库引入解决了什么问题 | 1 | 1 | 检索、召回与向量库 | 图数据库引入解决了什么问题 |
| 177 | 未完全归一化::在 AI 产品迭代中，如何平衡自研组件和成熟 AI UI 库 | 1 | 1 | 其他未稳定归类问题 | 在 AI 产品迭代中，如何平衡自研组件和成熟 AI UI 库 |
| 178 | 未完全归一化::在 RAG 系统中，前端如何优化长文档展示与引用来源跳转 | 1 | 1 | RAG 全链路 | 在 RAG 系统中，前端如何优化长文档展示与引用来源跳转 |
| 179 | 未完全归一化::在处理 AI 响应的长列表消息时，如何实现自动滚动到底部，同时保证用户手动向上滚动时不被干扰 | 1 | 1 | 其他未稳定归类问题 | 在处理 AI 响应的长列表消息时，如何实现自动滚动到底部，同时保证用户手动向上滚动时不被干扰 |
| 180 | 未完全归一化::在工程上如何处理 Agent 任务的状态管理与容错 | 1 | 1 | Agent 基础与系统架构 | 在工程上如何处理 Agent 任务的状态管理与容错 |
| 181 | 未完全归一化::基于 AC 自动机构建违禁词匹配查询结构，在实际场景中如何实现 | 1 | 1 | 系统设计与项目深挖 | 基于 AC 自动机构建违禁词匹配查询结构，在实际场景中如何实现 |
| 182 | 未完全归一化::多 key 场景下 Redis 订阅发布的轮询和监听如何处理 | 1 | 1 | 系统设计与项目深挖 | 多 key 场景下 Redis 订阅发布的轮询和监听如何处理 |
| 183 | 未完全归一化::多租户场景下知识库和会话如何隔离 | 1 | 1 | RAG 全链路 | 多租户场景下知识库和会话如何隔离 |
| 184 | 未完全归一化::大批量数据场景下，为什么 emoji 匹配要用 AC 自动机 | 1 | 1 | 系统设计与项目深挖 | 大批量数据场景下，为什么 emoji 匹配要用 AC 自动机 |
| 185 | 未完全归一化::大模型后训练有哪些方式 | 1 | 1 | 模型基础、Transformer、LoRA 与 RLHF | 大模型后训练有哪些方式 |
| 186 | 未完全归一化::大模型应用开发中 RAG 的基本链路 | 1 | 1 | RAG 全链路 | 大模型应用开发中 RAG 的基本链路 |
| 187 | 未完全归一化::如何优化 Agent，让它更智能 | 1 | 1 | Agent 基础与系统架构 | 如何优化 Agent，让它更智能 |
| 188 | 未完全归一化::如何做 AI 应用的错误态和降级态设计 | 1 | 1 | 其他未稳定归类问题 | 如何做 AI 应用的错误态和降级态设计 |
| 189 | 未完全归一化::如何处理生成结果不稳定带来的产品体验问题 | 1 | 1 | 其他未稳定归类问题 | 如何处理生成结果不稳定带来的产品体验问题 |
| 190 | 未完全归一化::如何实现一个简单的 Markdown 实时渲染引擎，并处理代码高亮 | 1 | 1 | 其他未稳定归类问题 | 如何实现一个简单的 Markdown 实时渲染引擎，并处理代码高亮 |
| 191 | 未完全归一化::如何对 MySQL 进行优化 | 1 | 1 | 其他未稳定归类问题 | 如何对 MySQL 进行优化 |
| 192 | 未完全归一化::如何设计 AI Agent 工作流编辑器 | 1 | 1 | Agent 基础与系统架构 | 如何设计 AI Agent 工作流编辑器 |
| 193 | 未完全归一化::如何设计一个 AI 歌词生成系统 | 1 | 1 | 其他未稳定归类问题 | 如何设计一个 AI 歌词生成系统 |
| 194 | 未完全归一化::如何设计一套可观测的 AI 应用前端埋点 | 1 | 1 | 其他未稳定归类问题 | 如何设计一套可观测的 AI 应用前端埋点 |
| 195 | 未完全归一化::如果 AI Agent 给出的排障建议与实际不符，怎么办 | 1 | 1 | Agent 基础与系统架构 | 如果 AI Agent 给出的排障建议与实际不符，怎么办 |
| 196 | 未完全归一化::如果做滴滴场景的 Agent，核心价值是什么 | 1 | 1 | 系统设计与项目深挖 | 如果做滴滴场景的 Agent，核心价值是什么 |
| 197 | 未完全归一化::如果回答流式输出中断，前端如何处理体验 | 1 | 1 | 其他未稳定归类问题 | 如果回答流式输出中断，前端如何处理体验 |
| 198 | 未完全归一化::如果某个 Agent 误判导致策略冲突，怎么处理 | 1 | 1 | Agent 基础与系统架构 | 如果某个 Agent 误判导致策略冲突，怎么处理 |
| 199 | 未完全归一化::如果系统出现网络抖动，而不是真故障，Agent 该如何判断 | 1 | 1 | Agent 基础与系统架构 | 如果系统出现网络抖动，而不是真故障，Agent 该如何判断 |
| 200 | 未完全归一化::如果线上回答不稳定，怎么排查 | 1 | 1 | 其他未稳定归类问题 | 如果线上回答不稳定，怎么排查 |
| 201 | 未完全归一化::如果要优化相关度和回答效果，有什么思路，如何体系化建设 | 1 | 1 | 其他未稳定归类问题 | 如果要优化相关度和回答效果，有什么思路，如何体系化建设 |
| 202 | 未完全归一化::如果让你设计一个 AI Agent 的工作流编排画布，类似 LangFlow，你会选什么技术栈，核心难点在哪 | 1 | 1 | Agent 基础与系统架构 | 如果让你设计一个 AI Agent 的工作流编排画布，类似 LangFlow，你会选什么技术栈，核心难点在哪 |
| 203 | 未完全归一化::如果让大模型实现类似 Cloud Code、Cursor 的编程工具，该如何实现 | 1 | 1 | 其他未稳定归类问题 | 如果让大模型实现类似 Cloud Code、Cursor 的编程工具，该如何实现 |
| 204 | 未完全归一化::如果设计一个数据处理场景，例如一千条数据求和，如何处理 | 1 | 1 | 系统设计与项目深挖 | 如果设计一个数据处理场景，例如一千条数据求和，如何处理 |
| 205 | 未完全归一化::实际应用问题有哪些 | 1 | 1 | 其他未稳定归类问题 | 实际应用问题有哪些 |
| 206 | 未完全归一化::对 AI 大语言模型有什么了解 | 1 | 1 | 其他未稳定归类问题 | 对 AI 大语言模型有什么了解 |
| 207 | 未完全归一化::对当前 Agent 能力的预期和现实差距怎么看 | 1 | 1 | Agent 基础与系统架构 | 对当前 Agent 能力的预期和现实差距怎么看 |
| 208 | 未完全归一化::对目标业务的理解 | 1 | 1 | 系统设计与项目深挖 | 对目标业务的理解 |
| 209 | 未完全归一化::工作流怎么搭建 | 1 | 1 | 其他未稳定归类问题 | 工作流怎么搭建 |
| 210 | 未完全归一化::布隆过滤器 | 1 | 1 | 其他未稳定归类问题 | 布隆过滤器 |
| 211 | 未完全归一化::常见 Agent 框架有什么区别 | 1 | 1 | Agent 基础与系统架构 | 常见 Agent 框架有什么区别 |
| 212 | 未完全归一化::平常用什么大模型 | 1 | 1 | 系统设计与项目深挖 | 平常用什么大模型 |
| 213 | 未完全归一化::平时通过什么渠道跟进最新技术 | 1 | 1 | 系统设计与项目深挖 | 平时通过什么渠道跟进最新技术 |
| 214 | 未完全归一化::开发 agent 使用的框架和语言分别是什么 | 1 | 1 | Agent 基础与系统架构 | 开发 agent 使用的框架和语言分别是什么 |
| 215 | 未完全归一化::异构文档如何处理 | 1 | 1 | 其他未稳定归类问题 | 异构文档如何处理 |
| 216 | 未完全归一化::张量并行 | 1 | 1 | 其他未稳定归类问题 | 张量并行 |
| 217 | 未完全归一化::技术栈里是否考虑过 Hive、Spark 这类大数据链路 | 1 | 1 | 其他未稳定归类问题 | 技术栈里是否考虑过 Hive、Spark 这类大数据链路 |
| 218 | 未完全归一化::数据处理场景怎么设计 | 1 | 1 | 系统设计与项目深挖 | 数据处理场景怎么设计 |
| 219 | 未完全归一化::数据库存储和 RAG 是怎么做的 | 1 | 1 | RAG 全链路 | 数据库存储和 RAG 是怎么做的 |
| 220 | 未完全归一化::数据构建怎么做 | 1 | 1 | 其他未稳定归类问题 | 数据构建怎么做 |
| 221 | 未完全归一化::数据质量和筛选策略怎么做 | 1 | 1 | 其他未稳定归类问题 | 数据质量和筛选策略怎么做 |
| 222 | 未完全归一化::数据集包括什么 | 1 | 1 | 其他未稳定归类问题 | 数据集包括什么 |
| 223 | 未完全归一化::日常干活会用哪些 AI 工具 | 1 | 1 | 系统设计与项目深挖 | 日常干活会用哪些 AI 工具 |
| 224 | 未完全归一化::最左前缀原则 | 1 | 1 | 其他未稳定归类问题 | 最左前缀原则 |
| 225 | 未完全归一化::有没有从 0 训练大模型的经历 | 1 | 1 | 模型基础、Transformer、LoRA 与 RLHF | 有没有从 0 训练大模型的经历 |
| 226 | 未完全归一化::构建 Agent 时遇到过哪些瓶颈 | 1 | 1 | Agent 基础与系统架构 | 构建 Agent 时遇到过哪些瓶颈 |
| 227 | 未完全归一化::消息可靠性如何保证 | 1 | 1 | 其他未稳定归类问题 | 消息可靠性如何保证 |
| 228 | 未完全归一化::游戏公司目前在关注的 AI 漫剧 / 自动化内容方向，你会怎么做方案设计 | 1 | 1 | 其他未稳定归类问题 | 游戏公司目前在关注的 AI 漫剧 / 自动化内容方向，你会怎么做方案设计 |
| 229 | 未完全归一化::热点问题如何处理 | 1 | 1 | 其他未稳定归类问题 | 热点问题如何处理 |
| 230 | 未完全归一化::用两三句话介绍 Agent 以及当前挑战 | 1 | 1 | Agent 基础与系统架构 | 用两三句话介绍 Agent 以及当前挑战 |
| 231 | 未完全归一化::画出典型的 RAG 结构 | 1 | 1 | RAG 全链路 | 画出典型的 RAG 结构 |
| 232 | 未完全归一化::知识图谱底层用什么数据结构存 | 1 | 1 | 检索、召回与向量库 | 知识图谱底层用什么数据结构存 |
| 233 | 未完全归一化::稀疏多目标场景下，loss 怎么设计，既保证主目标收敛，又不让稀疏目标失效 | 1 | 1 | 模型基础、Transformer、LoRA 与 RLHF | 稀疏多目标场景下，loss 怎么设计，既保证主目标收敛，又不让稀疏目标失效 |
| 234 | 未完全归一化::算法题：K 个一组反转链表 | 1 | 1 | 其他未稳定归类问题 | 算法题：K 个一组反转链表 |
| 235 | 未完全归一化::算法题：`2n+1` 个数两两成对，找出单独那个数 | 1 | 1 | 其他未稳定归类问题 | 算法题：`2n+1` 个数两两成对，找出单独那个数 |
| 236 | 未完全归一化::系统稳定性怎么保障 | 1 | 1 | 其他未稳定归类问题 | 系统稳定性怎么保障 |
| 237 | 未完全归一化::线上大模型应用架构怎么设计 | 1 | 1 | 其他未稳定归类问题 | 线上大模型应用架构怎么设计 |
| 238 | 未完全归一化::线上问题定位 | 1 | 1 | 推理部署与性能优化 | 线上问题定位 |
| 239 | 未完全归一化::结构化输出怎么做 | 1 | 1 | 其他未稳定归类问题 | 结构化输出怎么做 |
| 240 | 未完全归一化::给出 CUDA Kernel 代码，识别其功能 | 1 | 1 | 其他未稳定归类问题 | 给出 CUDA Kernel 代码，识别其功能 |
| 241 | 未完全归一化::缓存一致性怎么做 | 1 | 1 | 其他未稳定归类问题 | 缓存一致性怎么做 |
| 242 | 未完全归一化::解释 JS 事件循环，并说明宏任务与微任务在处理 AI 消息推送时的先后顺序 | 1 | 1 | 其他未稳定归类问题 | 解释 JS 事件循环，并说明宏任务与微任务在处理 AI 消息推送时的先后顺序 |
| 243 | 未完全归一化::训练与 `RL` 工程优化 | 1 | 1 | 模型基础、Transformer、LoRA 与 RLHF | 训练与 `RL` 工程优化 |
| 244 | 未完全归一化::训练样本质量问题会如何影响模型行为 | 1 | 1 | 模型基础、Transformer、LoRA 与 RLHF | 训练样本质量问题会如何影响模型行为 |
| 245 | 未完全归一化::论文经历介绍 | 1 | 1 | 其他未稳定归类问题 | 论文经历介绍 |
| 246 | 未完全归一化::请求抢占怎么做 | 1 | 1 | 其他未稳定归类问题 | 请求抢占怎么做 |
| 247 | 未完全归一化::请简述 SSE 和 WebSocket 的区别，在 AI 流式输出场景下如何选择 | 1 | 1 | 系统设计与项目深挖 | 请简述 SSE 和 WebSocket 的区别，在 AI 流式输出场景下如何选择 |
| 248 | 未完全归一化::调度队列怎么设计 | 1 | 1 | 其他未稳定归类问题 | 调度队列怎么设计 |
| 249 | 未完全归一化::谈谈对 CSS 容器查询的理解，它在 AI 侧边栏组件中有什么作用 | 1 | 1 | 其他未稳定归类问题 | 谈谈对 CSS 容器查询的理解，它在 AI 侧边栏组件中有什么作用 |
| 250 | 未完全归一化::过去一年如何利用 AI 工具提升前端开发效率 | 1 | 1 | 其他未稳定归类问题 | 过去一年如何利用 AI 工具提升前端开发效率 |
| 251 | 未完全归一化::还有算法题追问 | 1 | 1 | 其他未稳定归类问题 | 还有算法题追问 |
| 252 | 未完全归一化::重试机制怎么做 | 1 | 1 | 其他未稳定归类问题 | 重试机制怎么做 |
| 253 | 未完全归一化::错误态和降级怎么做 | 1 | 1 | 其他未稳定归类问题 | 错误态和降级怎么做 |
| 254 | 未完全归一化::面对快速迭代的 AI 技术，如何保证团队技术栈稳定性与前瞻性 | 1 | 1 | 其他未稳定归类问题 | 面对快速迭代的 AI 技术，如何保证团队技术栈稳定性与前瞻性 |
| 255 | 系统设计题 | 1 | 1 | 系统设计与项目深挖 | 系统设计或中间件基础 |

---

## 1. 项目介绍与项目深挖

- 归并次数：`62`
- 来源面经数：`43`
- 分类倾向：`系统设计与项目深挖`

典型原题：

- 项目追问
- 反问
- 自我介绍
- 项目深挖
- RAG 项目深挖
- 全是 Agent、RAG 和项目相关问题，不涉及后端八股

来源样例：

- [蚂蚁三面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-10-21-ant-ai-agent-app-round3.md)
- [美团后端一面 Agent 开发](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-27-meituan-backend-agent-dev-round1.md)
- [字节后端一面（含 RAG）](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-10-byte-backend-round1-with-rag.md)
- [AI 应用开发实习面经 快手](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-20-kuaishou-ai-app-dev-intern.md)
- [快手前端 AI 应用开发一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-20-kuaishou-frontend-ai-app-dev-round1.md)
- [阿里 AI Agent 开发一面 40min](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-22-ali-ai-agent-dev-round1.md)

## 2. 推理部署与性能优化

- 归并次数：`50`
- 来源面经数：`29`
- 分类倾向：`推理部署与性能优化`

典型原题：

- `PagedAttention`
- `KV cache`
- 是否做过模型压缩，车载端或低端设备如何推理加速
- `FlashAttention`
- `vLLM` 优化点
- 推理效果和资源消耗如何平衡

来源样例：

- [百融云创 AI Infra 面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-02-26-bright-ai-infra-offer.md)
- [AI Infra 推理方向日常实习面经总结](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-ai-infra-inference-summary.md)
- [快手实习 AI Infra 一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-04-kuaishou-ai-infra-round1-alt.md)
- [字节校招 AI Infra 后端面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-byte-ai-infra-backend-campus.md)
- [字节大模型 Agent 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-30-byte-agent-algo-round2.md)
- [百度 智能体算法工程师一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-08-05-baidu-agent-algo-round1.md)

## 3. 工具调用与 Function Calling

- 归并次数：`32`
- 来源面经数：`26`
- 分类倾向：`工具调用、Function Calling 与 MCP`

典型原题：

- 工具调用和流程编排
- 外部工具调用链条如何做故障容错和超时机制
- 工具调用失败后的 feedback 策略如何设计
- `function call`
- 联网搜索
- 工具调用怎么做

来源样例：

- [高德 Agent 研发秋招面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-10-12-gaode-agent-rd-autumn.md)
- [蚂蚁大模型 Agent 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-30-ant-agent-algo-round2.md)
- [京东科技后端一面 35min](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-10-jd-backend-ai-round1.md)
- [腾讯微信支付一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-25-tencent-wechatpay-backend-ai-round1.md)
- [大模型应用面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-26-llm-app-dev-general.md)
- [字节大模型算法实习-AI 搜索一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-27-byte-llm-algo-ai-search-round1.md)

## 4. 上下文工程与多轮对话

- 归并次数：`29`
- 来源面经数：`26`
- 分类倾向：`记忆、上下文工程与多轮对话`

典型原题：

- 上下文接口怎么修改
- 较长较多的上下文怎么解决
- 多轮 `mask`
- 多轮对话状态如何管理，高并发下如何保证一致性
- 怎么防止客服 LLM 串台问题
- 上下文裁剪怎么做

来源样例：

- [得物大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-05-dewu-llm-algo-interview.md)
- [滴滴校招大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-14-didi-llm-algo-interview.md)
- [蚂蚁大模型 Agent 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-30-ant-agent-algo-round2.md)
- [小红书 NLP 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-09-xiaohongshu-nlp-algo-round2.md)
- [腾讯微信支付一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-25-tencent-wechatpay-backend-ai-round1.md)
- [快手 AI Agent 开发实习生一二面面筋](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-01-15-kuaishou-ai-agent-intern-round12.md)

## 5. Agent 记忆设计

- 归并次数：`25`
- 来源面经数：`20`
- 分类倾向：`记忆、上下文工程与多轮对话`

典型原题：

- CUDA memory model
- 怎么加强大模型记忆机制
- Agent 的记忆系统怎么设计
- LangChain 的 memory 在多用户并发下如何做隔离，如何保证线程安全
- 是否做过记忆衰退，避免旧数据干扰新任务
- 长期记忆如何存储，历史数据很大时如何优化查询效率

来源样例：

- [百融云创 AI Infra 面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-02-26-bright-ai-infra-offer.md)
- [得物大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-05-dewu-llm-algo-interview.md)
- [字节大模型 Agent 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-30-byte-agent-algo-round2.md)
- [蚂蚁大模型 Agent 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-30-ant-agent-algo-round2.md)
- [淘天 Agent 开发实习一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-17-taotian-agent-dev-intern-round1.md)
- [腾讯微信支付一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-25-tencent-wechatpay-backend-ai-round1.md)

## 6. 检索与召回优化

- 归并次数：`25`
- 来源面经数：`19`
- 分类倾向：`检索、召回与向量库`

典型原题：

- 介绍 GraphRAG，难点是什么，增量场景怎么做
- RAG 或知识检索相关问题
- 若要做实时重排，如何在大规模数据下做架构 tradeoff 并压低 latency
- 检索方式有哪些
- 检索与召回优化
- RAG 常用的检索方式

来源样例：

- [美团 AI Agent 算法一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-16-meituan-ai-agent-algo-round1.md)
- [高德 Agent 研发秋招面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-10-12-gaode-agent-rd-autumn.md)
- [快手大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-02-kuaishou-llm-algo-interview.md)
- [滴滴校招大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-14-didi-llm-algo-interview.md)
- [贝壳找房 RAG 面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-20-ke-rag-interview.md)
- [小红书 NLP 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-09-xiaohongshu-nlp-algo-round2.md)

## 7. 评测体系

- 归并次数：`22`
- 来源面经数：`19`
- 分类倾向：`评测、幻觉治理与 bad case`

典型原题：

- RAG 评测怎么做
- 训练数据和评测数据如何构建
- 多维度自动化评估里，关键词匹配和问答对流程怎么构建
- 自动化评估体系怎么评，维度有哪些
- 如何评测
- AIGC 文本评估怎么做

来源样例：

- [京东大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-01-30-jd-llm-algo-interview.md)
- [AI Agent 开发二面 快手面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-21-kuaishou-ai-agent-dev-round2.md)
- [百度 智能体算法工程师一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-08-05-baidu-agent-algo-round1.md)
- [快手大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-02-kuaishou-llm-algo-interview.md)
- [滴滴校招大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-14-didi-llm-algo-interview.md)
- [百度大模型应用面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-16-baidu-llm-app-interview.md)

## 8. 工程化与并发治理

- 归并次数：`19`
- 来源面经数：`18`
- 分类倾向：`工程化、后端服务与并发治理`

典型原题：

- Spring AI 怎么用
- 是否用过 AutoGen 或 LangChain，为什么选这个框架
- `Langchain4j`
- LangChain 怎么用
- FastAPI 是否自己开发
- LangChain 在项目中的作用

来源样例：

- [腾讯微信支付一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-25-tencent-wechatpay-backend-ai-round1.md)
- [腾讯后台开发一面（含 AI 应用）](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-10-tencent-backend-ai-app-round1.md)
- [字节大模型 Agent 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-30-byte-agent-algo-round2.md)
- [京东科技后端一面 35min](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-10-jd-backend-ai-round1.md)
- [大模型应用面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-26-llm-app-dev-general.md)
- [零氪科技 NLP / RAG 面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-01-13-linkdoc-nlp-rag-rounds.md)

## 9. Transformer 与注意力机制

- 归并次数：`15`
- 来源面经数：`11`
- 分类倾向：`模型基础、Transformer、LoRA 与 RLHF`

典型原题：

- Transformer 架构有哪些关键机制
- 解释交叉注意力机制
- 为什么要用 multi-head attention
- 介绍 self-attention，并分析时间复杂度
- 介绍 MoE（混合专家）架构的核心优势
- Transformer 的基本结构

来源样例：

- [美团 Agent 算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-09-27-meituan-agent-algo-interview.md)
- [字节大模型 Agent 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-30-byte-agent-algo-round2.md)
- [腾讯大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-01-29-tencent-llm-algo-round1.md)
- [360 AI 应用一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-11-360-ai-app-round1.md)
- [阿里淘天AI agent开发一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-12-taotian-ai-agent-dev-round1.md)
- [阿里实习 AI Infra 面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-28-ali-ai-infra-intern.md)

## 10. LoRA 与微调

- 归并次数：`15`
- 来源面经数：`9`
- 分类倾向：`模型基础、Transformer、LoRA 与 RLHF`

典型原题：

- 金融场景里 RAG 和微调怎么选
- `embedding` 微调
- LoRA 效果不好怎么办
- LoRA 的关键超参数和影响
- LoRA 的原理
- LoRA 的缺点和改进方向

来源样例：

- [同花顺金融大模型算法一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-04-ths-finance-llm-algo-round1.md)
- [夸克大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-05-quark-llm-algo-interview.md)
- [得物大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-05-dewu-llm-algo-interview.md)
- [蚂蚁大模型 Agent 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-30-ant-agent-algo-round2.md)
- [美团 AI Agent 算法一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-16-meituan-ai-agent-algo-round1.md)
- [Agent 开发 字节面试被问麻了](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-09-byte-agent-dev-multi-round.md)

## 11. 向量库与索引选型

- 归并次数：`14`
- 来源面经数：`11`
- 分类倾向：`检索、召回与向量库`

典型原题：

- pgvector 的使用
- RAG 索引优化
- 知道哪些 Embedding 模型
- 向量库怎么设计
- 用的什么向量数据库
- 向量库的作用和选型

来源样例：

- [蚂蚁三面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-10-21-ant-ai-agent-app-round3.md)
- [百度大模型应用面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-16-baidu-llm-app-interview.md)
- [小红书 NLP 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-09-xiaohongshu-nlp-algo-round2.md)
- [零氪科技 NLP / RAG 面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-01-13-linkdoc-nlp-rag-rounds.md)
- [有赞 Agent 开发实习一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-01-23-youzan-agent-dev-intern-round1.md)
- [京东大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-01-30-jd-llm-algo-interview.md)

## 12. 意图识别与任务规划

- 归并次数：`12`
- 来源面经数：`12`
- 分类倾向：`Prompt、意图识别、规划与 ReAct`

典型原题：

- 意图识别
- ReAct 是什么
- Agent 规划与执行能力如何评估
- 反思机制是什么
- 用户请求不完整时，如何补全用户意图
- 职业发展规划是什么

来源样例：

- [京东科技后端一面 35min](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-10-jd-backend-ai-round1.md)
- [腾讯微信支付一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-25-tencent-wechatpay-backend-ai-round1.md)
- [字节大模型算法实习-AI 搜索一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-27-byte-llm-algo-ai-search-round1.md)
- [字节 后端开发（Agent 中台）一面凉](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-09-byte-agent-platform-backend-round1.md)
- [百度 智能体算法工程师一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-08-05-baidu-agent-algo-round1.md)
- [百度大模型应用面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-16-baidu-llm-app-interview.md)

## 13. Agent 定义与架构

- 归并次数：`12`
- 来源面经数：`11`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- 多智能体怎么设计
- Agent 和 Workflow 的区别，为什么需要 Agent
- AI Agent 是什么
- Agent 中台和普通后端平台有什么区别
- 国内几个 Agent 平台对比
- Agent 和 workflow 的区别

来源样例：

- [LLM 算法实习 百度二面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-07-baidu-llm-algo-intern-round2.md)
- [百度 LLM 算法校招二面 强度拉满了](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-baidu-llm-algo-round2.md)
- [得物大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-05-dewu-llm-algo-interview.md)
- [腾讯微信支付一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-25-tencent-wechatpay-backend-ai-round1.md)
- [字节 后端开发（Agent 中台）一面凉](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-09-byte-agent-platform-backend-round1.md)
- [滴滴 AI Agent 实习一面凉经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-10-didi-ai-agent-intern-round1.md)

## 14. 编码题与手撕题

- 归并次数：`12`
- 来源面经数：`9`
- 分类倾向：`编码题与手撕题`

典型原题：

- LRU 机制
- 手撕一道非 Hot100 题
- 代码题：字符串解码
- LRU 代码题
- 代码题：LeetCode 22，括号生成
- 手撕：全排列

来源样例：

- [快手 AI Agent 开发实习生一二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-09-kuaishou-ai-agent-dev-intern-round12.md)
- [快手 Agent 开发一面 45min](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-21-kuaishou-ai-agent-dev-round1-45m.md)
- [美团 Agent 算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-09-27-meituan-agent-algo-interview.md)
- [小红书 NLP 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-09-xiaohongshu-nlp-algo-round2.md)
- [淘天 Agent 开发实习一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-17-taotian-agent-dev-intern-round1.md)
- [腾讯大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-01-29-tencent-llm-algo-round1.md)

## 15. RLHF / DPO / PPO / 强化学习

- 归并次数：`12`
- 来源面经数：`7`
- 分类倾向：`模型基础、Transformer、LoRA 与 RLHF`

典型原题：

- DeepResearch 和强化学习怎么结合应用
- GRPO 的 loss 怎么计算，训练数据怎么来
- 介绍 PPO、DPO、GRPO
- 为什么需要 reference model，它解决什么问题
- 偏好对如何构造，是自动还是人工
- 在线强化学习和离线强化学习有什么区别，RLHF 属于哪一种

来源样例：

- [美团 Agent 算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-09-27-meituan-agent-algo-interview.md)
- [字节大模型 Agent 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-30-byte-agent-algo-round2.md)
- [蚂蚁大模型 Agent 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-30-ant-agent-algo-round2.md)
- [美团 AI Agent 算法一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-16-meituan-ai-agent-algo-round1.md)
- [腾讯大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-01-29-tencent-llm-algo-round1.md)
- [淘天 AI Agent 二面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-07-taotian-ai-agent-round2.md)

## 16. 多模态与截图理解

- 归并次数：`10`
- 来源面经数：`6`
- 分类倾向：`多模态`

典型原题：

- Playwright 截图时报错或渲染失败怎么办
- 多模态用户信息怎么存储和使用
- 对多模态大模型了解多少，具体结构是什么
- 如果做电商 Agent，会选择哪些模态输入
- CLIP 适用于哪类多模态 RAG，为什么
- 伪多模态 RAG 和多模态 RAG 的区别与实现

来源样例：

- [快手大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-02-kuaishou-llm-algo-interview.md)
- [得物大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-05-dewu-llm-algo-interview.md)
- [字节大模型 Agent 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-30-byte-agent-algo-round2.md)
- [美团 AI Agent 算法一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-16-meituan-ai-agent-algo-round1.md)
- [A厂 Agent 开发一面面经题目整理](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-10-anonymous-agent-dev-round1.md)
- [AI 应用开发 Minimax 面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-27-minimax-ai-app-dev.md)

## 17. MCP

- 归并次数：`9`
- 来源面经数：`9`
- 分类倾向：`工具调用、Function Calling 与 MCP`

典型原题：

- MCP 是什么
- MCP server 的作用
- 腾讯云 MCP 的功能和工具能力有哪些
- MCP 的作用是什么
- 你编写了哪些 MCP 工具

来源样例：

- [大模型应用面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-26-llm-app-dev-general.md)
- [有赞 Agent 开发实习一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-01-23-youzan-agent-dev-intern-round1.md)
- [Agent 开发 字节面试被问麻了](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-09-byte-agent-dev-multi-round.md)
- [分享 AI 应用开发面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-ai-app-dev-shared.md)
- [AI 应用开发 华为校招二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-huawei-ai-app-dev-round2.md)
- [蚂蚁三面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-10-21-ant-ai-agent-app-round3.md)

## 18. Prompt 设计与优化

- 归并次数：`9`
- 来源面经数：`7`
- 分类倾向：`Prompt、意图识别、规划与 ReAct`

典型原题：

- Prompt 模板怎么设计
- Agent 系统 Prompt 怎么设计和迭代，是否做过自动优化
- Prompt 设计时要注意什么
- 提示词注入怎么防
- Prompt 怎么做
- Prompt 设计有哪些注意点

来源样例：

- [阿里实习 AI Agent 开发二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-26-ali-ai-agent-dev-round2.md)
- [小红书 AI 应用开发二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-06-xiaohongshu-ai-app-dev-round2.md)
- [蚂蚁大模型 Agent 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-30-ant-agent-algo-round2.md)
- [适趣AI 大模型应用开发实习一面凉经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-23-shiquai-llm-app-dev-intern-round1.md)
- [AI 应用开发实习面经 得物二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-20-dewu-ai-app-dev-round2.md)
- [AI 应用开发实习面经 快手](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-20-kuaishou-ai-app-dev-intern.md)

## 19. 多 Agent 协作

- 归并次数：`8`
- 来源面经数：`6`
- 分类倾向：`多 Agent 协作`

典型原题：

- 如何让多个 Agent 协同工作，举一个具体机制
- 多 Agent 如何协作
- 多 Agent `A2A` 协议怎么理解
- `RAG + Tool` 如何协同
- 多 Agent workflow 怎么做
- 多 Agent 协作如何设计

来源样例：

- [字节大模型 Agent 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-30-byte-agent-algo-round2.md)
- [大模型应用面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-26-llm-app-dev-general.md)
- [AI 应用开发 华为校招二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-huawei-ai-app-dev-round2.md)
- [携程 AI Agent 开发二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-ctrip-ai-agent-dev-round2.md)
- [腾讯 AI 应用开发二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-tencent-ai-app-dev-round2.md)
- [大模型应用开发日常实习小厂面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-small-company-llm-app-dev-intern.md)

## 20. 幻觉治理与 bad case

- 归并次数：`7`
- 来源面经数：`7`
- 分类倾向：`评测、幻觉治理与 bad case`

典型原题：

- 幻觉治理怎么做
- 幻觉治理方案
- 多服务串联时如何减少幻觉和错误传播
- 如何缓解大模型幻觉
- AI 幻觉不可避免，前端如何从产品交互层面缓解
- 大模型出现复读机现象的原因是什么，有哪些解决方法

来源样例：

- [淘天 Agent 开发实习一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-17-taotian-agent-dev-intern-round1.md)
- [美团大模型算法实习一面 50min](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-meituan-llm-algo-intern-round1.md)
- [百度大模型应用面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-16-baidu-llm-app-interview.md)
- [A厂 Agent 开发一面面经题目整理](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-10-anonymous-agent-dev-round1.md)
- [快手 AI 应用开发一面 日常实习](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-12-kuaishou-ai-app-dev-round1.md)
- [AI应用开发实习面经-得物](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-05-dewu-ai-app-dev-intern.md)

## 21. RAG 链路设计

- 归并次数：`5`
- 来源面经数：`5`
- 分类倾向：`RAG 全链路`

典型原题：

- RAG 链路怎么搭
- 介绍 RAG 流程
- RAG 的整体流程

来源样例：

- [大模型应用面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-26-llm-app-dev-general.md)
- [Soul AI Agent 实习二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-04-soul-ai-agent-intern-round2.md)
- [完美世界 AI Agent 开发一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-perfect-world-ai-agent-dev-round1.md)
- [美团 AI Agent 算法一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-16-meituan-ai-agent-algo-round1.md)
- [360 AI 应用一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-11-360-ai-app-round1.md)

## 22. RAG 分块策略

- 归并次数：`4`
- 来源面经数：`4`
- 分类倾向：`检索、召回与向量库`

典型原题：

- RAG 分块怎么做
- `chunked prefill`
- chunk 策略怎么设计
- Spring AI 文档切分

来源样例：

- [滴滴校招大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-14-didi-llm-algo-interview.md)
- [AI Infra 推理方向日常实习面经总结](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-ai-infra-inference-summary.md)
- [分享 AI 应用开发面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-ai-app-dev-shared.md)
- [蚂蚁三面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-10-21-ant-ai-agent-app-round3.md)

## 23. Qwen 与开源模型理解

- 归并次数：`3`
- 来源面经数：`2`
- 分类倾向：`模型基础、Transformer、LoRA 与 RLHF`

典型原题：

- Qwen 各代的重要突破
- Qwen 系列模型的结构和特点
- Qwen3 的技术原理

来源样例：

- [得物大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-05-dewu-llm-algo-interview.md)
- [小红书 NLP 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-09-xiaohongshu-nlp-algo-round2.md)

## 24. 未完全归一化::LangGraph 怎么用

- 归并次数：`2`
- 来源面经数：`2`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- LangGraph 怎么用

来源样例：

- [分享 AI 应用开发面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-ai-app-dev-shared.md)
- [Agent 实习面经-阿里国际](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-12-alibaba-international-agent-intern.md)

## 25. 未完全归一化::RAG

- 归并次数：`2`
- 来源面经数：`2`
- 分类倾向：`RAG 全链路`

典型原题：

- RAG

来源样例：

- [京东科技后端一面 35min](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-10-jd-backend-ai-round1.md)
- [快手 AI Agent 开发实习生一二面面筋](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-01-15-kuaishou-ai-agent-intern-round12.md)

## 26. 未完全归一化::`MLA`

- 归并次数：`2`
- 来源面经数：`2`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- `MLA`

来源样例：

- [字节 AI Infra 校招一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-28-byte-ai-infra-campus-round1.md)
- [AI Infra 小厂实习面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-ai-infra-small-company-intern.md)

## 27. 未完全归一化::`PD` 分离

- 归并次数：`2`
- 来源面经数：`2`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- `PD` 分离

来源样例：

- [美团北斗 AI Infra 校招面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-28-meituan-beidou-ai-infra-campus.md)
- [AI Infra 推理方向日常实习面经总结](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-ai-infra-inference-summary.md)

## 28. 未完全归一化::AF / PD 分离是什么

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- AF / PD 分离是什么

来源样例：

- [快手 AI Infra 一面拷打](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-kuaishou-ai-infra-round1.md)

## 29. 未完全归一化::AI Agent 前端架构怎么设计

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- AI Agent 前端架构怎么设计

来源样例：

- [快手 AI Agent 前端二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-20-kuaishou-ai-agent-frontend-round2.md)

## 30. 未完全归一化::AI Chat 组件设计

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- AI Chat 组件设计

来源样例：

- [AI 应用开发实习面经 得物二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-20-dewu-ai-app-dev-round2.md)

## 31. 未完全归一化::AI 应用适合哪些业务场景

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`系统设计与项目深挖`

典型原题：

- AI 应用适合哪些业务场景

来源样例：

- [字节后端一面（含 RAG）](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-10-byte-backend-round1-with-rag.md)

## 32. 未完全归一化::AI 时代下，前端工程师的角色发生了哪些变化

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- AI 时代下，前端工程师的角色发生了哪些变化

来源样例：

- [商汤科技Ai agent开发面经（攒人品）](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-05-sensetime-ai-agent-dev-round1.md)

## 33. 未完全归一化::AI 流式输出如何实现

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- AI 流式输出如何实现

来源样例：

- [阿里实习 AI Agent 开发二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-26-ali-ai-agent-dev-round2.md)

## 34. 未完全归一化::AI 聊天产品的前端 UI 应该关注哪些关键点

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- AI 聊天产品的前端 UI 应该关注哪些关键点

来源样例：

- [小红书 AI 开发二面-实习面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-xiaohongshu-ai-dev-round2-intern.md)

## 35. 未完全归一化::API 网关怎么做

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- API 网关怎么做

来源样例：

- [带得科技 大模型应用开发二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-daide-llm-app-dev-round2.md)

## 36. 未完全归一化::Agent workflow 怎么设计

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- Agent workflow 怎么设计

来源样例：

- [腾讯后台开发一面（含 AI 应用）](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-10-tencent-backend-ai-app-round1.md)

## 37. 未完全归一化::Agent 全链路怎么设计

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- Agent 全链路怎么设计

来源样例：

- [携程 AI Agent 开发二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-ctrip-ai-agent-dev-round2.md)

## 38. 未完全归一化::Agent 和 RAG 的关系与边界

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- Agent 和 RAG 的关系与边界

来源样例：

- [AI Agent 开发二面-阿里](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-22-ali-ai-agent-dev-round2.md)

## 39. 未完全归一化::Agent 哪些模块最容易在线上出问题，如何监控与定位

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- Agent 哪些模块最容易在线上出问题，如何监控与定位

来源样例：

- [蚂蚁大模型 Agent 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-30-ant-agent-algo-round2.md)

## 40. 未完全归一化::Agent 在 RAG 链路中的位置

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- Agent 在 RAG 链路中的位置

来源样例：

- [夸克大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-05-quark-llm-algo-interview.md)

## 41. 未完全归一化::Agent 在实际业务里如何组织流程

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`系统设计与项目深挖`

典型原题：

- Agent 在实际业务里如何组织流程

来源样例：

- [阿里实习 AI Agent 开发二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-26-ali-ai-agent-dev-round2.md)

## 42. 未完全归一化::Agent 在金融问答或投研辅助里适不适合，边界在哪里

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- Agent 在金融问答或投研辅助里适不适合，边界在哪里

来源样例：

- [同花顺金融大模型算法一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-04-ths-finance-llm-algo-round1.md)

## 43. 未完全归一化::Agent 工作流如何组织

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- Agent 工作流如何组织

来源样例：

- [Shopee AI Agent 开发二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-shopee-ai-agent-dev-round2.md)

## 44. 未完全归一化::Agent 工程实现细节

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- Agent 工程实现细节

来源样例：

- [Shopee AI Agent 开发一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-shopee-ai-agent-dev-round1.md)

## 45. 未完全归一化::Agent 常见模式有哪些，适合什么任务

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- Agent 常见模式有哪些，适合什么任务

来源样例：

- [某中厂 Agent 开发面经-日常实习](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-mid-company-agent-dev-intern.md)

## 46. 未完全归一化::Agent 开发相关问题

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- Agent 开发相关问题

来源样例：

- [美团后端一面 Agent 开发](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-27-meituan-backend-agent-dev-round1.md)

## 47. 未完全归一化::Agent 的改进方向是什么

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- Agent 的改进方向是什么

来源样例：

- [得物大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-05-dewu-llm-algo-interview.md)

## 48. 未完全归一化::Agent 的编排怎么做，用了什么模式，如何调度

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- Agent 的编排怎么做，用了什么模式，如何调度

来源样例：

- [字节暑期剪映后端和AI agent一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-byte-jianying-backend-ai-agent-round1.md)

## 49. 未完全归一化::Agent 算法在业务落地中的挑战

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`系统设计与项目深挖`

典型原题：

- Agent 算法在业务落地中的挑战

来源样例：

- [阿里云 Agent 算法一面-秋招面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-15-aliyun-agent-algo-round1.md)

## 50. 未完全归一化::CAP 理解

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- CAP 理解

来源样例：

- [阿里 AI Agent 开发一面 40min](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-22-ali-ai-agent-dev-round1.md)

## 51. 未完全归一化::CUDA GEMM 基础

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- CUDA GEMM 基础

来源样例：

- [快手 AI Infra 一面拷打](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-kuaishou-ai-infra-round1.md)

## 52. 未完全归一化::CUDA `GEMM`

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- CUDA `GEMM`

来源样例：

- [字节 AI Infra 校招一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-28-byte-ai-infra-campus-round1.md)

## 53. 未完全归一化::CUDA `prefix-sum`

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- CUDA `prefix-sum`

来源样例：

- [美团北斗 AI Infra 校招面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-28-meituan-beidou-ai-infra-campus.md)

## 54. 未完全归一化::Chat UI 如何设计滚动与流式体验

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- Chat UI 如何设计滚动与流式体验

来源样例：

- [快手前端 AI 应用开发一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-20-kuaishou-frontend-ai-app-dev-round1.md)

## 55. 未完全归一化::ConcurrentHashMap 与 HashMap 区别

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- ConcurrentHashMap 与 HashMap 区别

来源样例：

- [字节暑期剪映后端和AI agent一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-byte-jianying-backend-ai-agent-round1.md)

## 56. 未完全归一化::Context Window 限制如何处理

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- Context Window 限制如何处理

来源样例：

- [百度 LLM 算法校招二面 强度拉满了](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-baidu-llm-algo-round2.md)

## 57. 未完全归一化::Coze Agent 的目的是什么

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- Coze Agent 的目的是什么

来源样例：

- [百度 AI Agent 一面凉经-日常实习](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-12-baidu-ai-agent-round1-intern.md)

## 58. 未完全归一化::DIN 模型相比传统推荐模型有什么改进

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- DIN 模型相比传统推荐模型有什么改进

来源样例：

- [淘天 AI Agent 二面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-07-taotian-ai-agent-round2.md)

## 59. 未完全归一化::GPU / CUDA 基础

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- GPU / CUDA 基础

来源样例：

- [快手实习 AI Infra 一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-04-kuaishou-ai-infra-round1-alt.md)

## 60. 未完全归一化::HTTP 长连接和短连接的区别

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- HTTP 长连接和短连接的区别

来源样例：

- [字节 AI Platform 一面凉经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-26-byte-ai-platform-round1.md)

## 61. 未完全归一化::HTTPS 基础

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- HTTPS 基础

来源样例：

- [字节跳动 AI 开发一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-byte-ai-dev-round1.md)

## 62. 未完全归一化::HashMap 底层实现、扩容、冲突处理

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- HashMap 底层实现、扩容、冲突处理

来源样例：

- [字节暑期剪映后端和AI agent一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-byte-jianying-backend-ai-agent-round1.md)

## 63. 未完全归一化::Java / Go 多态相关问题

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- Java / Go 多态相关问题

来源样例：

- [AI Agent 开发二面-阿里](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-22-ali-ai-agent-dev-round2.md)

## 64. 未完全归一化::K8S 如何使用

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- K8S 如何使用

来源样例：

- [阿里云 AI Agent 开发一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-aliyun-ai-agent-dev-round1.md)

## 65. 未完全归一化::Kafka 的使用场景

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`系统设计与项目深挖`

典型原题：

- Kafka 的使用场景

来源样例：

- [AI Agent 开发二面-阿里](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-22-ali-ai-agent-dev-round2.md)

## 66. 未完全归一化::L1 正则和 L2 正则的区别是什么，为什么 L1 能产生稀疏性

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- L1 正则和 L2 正则的区别是什么，为什么 L1 能产生稀疏性

来源样例：

- [淘天 AI Agent 二面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-07-taotian-ai-agent-round2.md)

## 67. 未完全归一化::LangGraph 和 Agent 编排怎么做

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- LangGraph 和 Agent 编排怎么做

来源样例：

- [Agent 开发 字节面试被问麻了](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-09-byte-agent-dev-multi-round.md)

## 68. 未完全归一化::LangGraph 的使用场景

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`系统设计与项目深挖`

典型原题：

- LangGraph 的使用场景

来源样例：

- [百度 LLM 算法校招二面 强度拉满了](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-baidu-llm-algo-round2.md)

## 69. 未完全归一化::LangGraph 的应用

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- LangGraph 的应用

来源样例：

- [LLM 算法实习 百度二面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-07-baidu-llm-algo-intern-round2.md)

## 70. 未完全归一化::LangGraph 的核心思想是什么

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- LangGraph 的核心思想是什么

来源样例：

- [快手 AI 应用开发一面 日常实习](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-12-kuaishou-ai-app-dev-round1.md)

## 71. 未完全归一化::LangGraph 适用于什么场景，构建 Agent 有哪几种方式

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`系统设计与项目深挖`

典型原题：

- LangGraph 适用于什么场景，构建 Agent 有哪几种方式

来源样例：

- [美团 AI Agent 算法一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-16-meituan-ai-agent-algo-round1.md)

## 72. 未完全归一化::MVCC 细节

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- MVCC 细节

来源样例：

- [快手 AI Agent 开发实习生一二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-09-kuaishou-ai-agent-dev-intern-round12.md)

## 73. 未完全归一化::Multi-Agent 和 Coze 的理解

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- Multi-Agent 和 Coze 的理解

来源样例：

- [AI agent应用开发一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-ai-agent-app-dev-round1.md)

## 74. 未完全归一化::Multi-agent 中 plan 的设计思路是什么

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- Multi-agent 中 plan 的设计思路是什么

来源样例：

- [指数引力 AI Agent 开发一面技术面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-11-zhishuyinli-ai-agent-dev-round1.md)

## 75. 未完全归一化::Multi-agent 如何设计

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- Multi-agent 如何设计

来源样例：

- [百度 Agent 智能体研发日常实习一二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-24-baidu-agent-rd-intern-round12.md)

## 76. 未完全归一化::MySQL / PostgreSQL 对比与使用

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- MySQL / PostgreSQL 对比与使用

来源样例：

- [Shopee AI Agent 开发一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-shopee-ai-agent-dev-round1.md)

## 77. 未完全归一化::MySQL ACID

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- MySQL ACID

来源样例：

- [字节暑期剪映后端和AI agent一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-byte-jianying-backend-ai-agent-round1.md)

## 78. 未完全归一化::MySQL binlog 原理

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- MySQL binlog 原理

来源样例：

- [字节 AI Platform 一面凉经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-26-byte-ai-platform-round1.md)

## 79. 未完全归一化::MySQL 为什么使用 B+ 树

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- MySQL 为什么使用 B+ 树

来源样例：

- [滴滴AI agent开发日常实习面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-09-didi-ai-agent-dev-intern.md)

## 80. 未完全归一化::MySQL 事务隔离与一致性

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- MySQL 事务隔离与一致性

来源样例：

- [快手 AI Agent 开发实习生一二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-09-kuaishou-ai-agent-dev-intern-round12.md)

## 81. 未完全归一化::MySQL 相关基础

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- MySQL 相关基础

来源样例：

- [字节跳动 AI 开发一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-byte-ai-dev-round1.md)

## 82. 未完全归一化::MySQL 相关问题

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- MySQL 相关问题

来源样例：

- [阿里 AI Agent 开发一面 40min](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-22-ali-ai-agent-dev-round1.md)

## 83. 未完全归一化::MySQL 锁

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- MySQL 锁

来源样例：

- [快手 AI Agent 开发实习生一二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-09-kuaishou-ai-agent-dev-intern-round12.md)

## 84. 未完全归一化::OpenClaw 怎么看

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- OpenClaw 怎么看

来源样例：

- [美团大模型算法实习一面 50min](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-meituan-llm-algo-intern-round1.md)

## 85. 未完全归一化::PAI、igraph、GraphScope、图数据库的区别

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`检索、召回与向量库`

典型原题：

- PAI、igraph、GraphScope、图数据库的区别

来源样例：

- [快手大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-02-kuaishou-llm-algo-interview.md)

## 86. 未完全归一化::PD 分离是什么

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- PD 分离是什么

来源样例：

- [AI Infra 应届春招](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-ai-infra-campus.md)

## 87. 未完全归一化::Query 改写策略

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- Query 改写策略

来源样例：

- [字节大模型算法实习-AI 搜索一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-27-byte-llm-algo-ai-search-round1.md)

## 88. 未完全归一化::RAG 优化

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- RAG 优化

来源样例：

- [夸克大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-05-quark-llm-algo-interview.md)

## 89. 未完全归一化::RAG 优化怎么做

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- RAG 优化怎么做

来源样例：

- [字节后端一面（含 RAG）](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-10-byte-backend-round1-with-rag.md)

## 90. 未完全归一化::RAG 优化有哪些思路

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- RAG 优化有哪些思路

来源样例：

- [百度 Agent 智能体研发日常实习一二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-24-baidu-agent-rd-intern-round12.md)

## 91. 未完全归一化::RAG 全流程怎么设计

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- RAG 全流程怎么设计

来源样例：

- [AI 应用开发 华为校招二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-huawei-ai-app-dev-round2.md)

## 92. 未完全归一化::RAG 切片策略如何选择

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- RAG 切片策略如何选择

来源样例：

- [某中厂 Agent 开发面经-日常实习](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-mid-company-agent-dev-intern.md)

## 93. 未完全归一化::RAG 切片策略怎么选

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- RAG 切片策略怎么选

来源样例：

- [快手 AI 应用开发一面 日常实习](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-12-kuaishou-ai-app-dev-round1.md)

## 94. 未完全归一化::RAG 在大模型应用中的作用和局限

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- RAG 在大模型应用中的作用和局限

来源样例：

- [大模型应用开发日常实习小厂面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-small-company-llm-app-dev-intern.md)

## 95. 未完全归一化::RAG 怎么做

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- RAG 怎么做

来源样例：

- [字节大模型算法实习-AI 搜索一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-27-byte-llm-algo-ai-search-round1.md)

## 96. 未完全归一化::RAG 怎么接

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- RAG 怎么接

来源样例：

- [阿里云 AI Agent 开发一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-aliyun-ai-agent-dev-round1.md)

## 97. 未完全归一化::RAG 怎么设计

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- RAG 怎么设计

来源样例：

- [AI 应用开发实习面经 得物二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-20-dewu-ai-app-dev-round2.md)

## 98. 未完全归一化::RAG 数据库存什么

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- RAG 数据库存什么

来源样例：

- [大模型算法实习二面-美团 40min](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-meituan-llm-algo-intern-round2.md)

## 99. 未完全归一化::RAG 整体链路

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- RAG 整体链路

来源样例：

- [有赞 Agent 开发实习一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-01-23-youzan-agent-dev-intern-round1.md)

## 100. 未完全归一化::RAG 是否还有必要

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- RAG 是否还有必要

来源样例：

- [美团大模型算法实习一面 50min](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-meituan-llm-algo-intern-round1.md)

## 101. 未完全归一化::RAG 有哪些分类

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- RAG 有哪些分类

来源样例：

- [美团 AI Agent 算法一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-16-meituan-ai-agent-algo-round1.md)

## 102. 未完全归一化::RAG 的基本链路

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- RAG 的基本链路

来源样例：

- [腾讯后台开发一面（含 AI 应用）](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-10-tencent-backend-ai-app-round1.md)

## 103. 未完全归一化::RAG 的整体链路如何设计

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- RAG 的整体链路如何设计

来源样例：

- [百度 AI Agent 开发二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-13-baidu-ai-agent-dev-round2.md)

## 104. 未完全归一化::RAG 知识库系统全链路设计

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- RAG 知识库系统全链路设计

来源样例：

- [滴滴AI agent开发日常实习面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-09-didi-ai-agent-dev-intern.md)

## 105. 未完全归一化::RAG 遇到模型缺失电商知识时怎么补

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- RAG 遇到模型缺失电商知识时怎么补

来源样例：

- [小红书 NLP 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-09-xiaohongshu-nlp-algo-round2.md)

## 106. 未完全归一化::RAG 链路怎么设计

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- RAG 链路怎么设计

来源样例：

- [AI 应用开发实习面经 快手](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-20-kuaishou-ai-app-dev-intern.md)

## 107. 未完全归一化::RL 或偏好优化怎么理解

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- RL 或偏好优化怎么理解

来源样例：

- [Agent 开发 字节面试被问麻了](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-09-byte-agent-dev-multi-round.md)

## 108. 未完全归一化::RL 相关训练方法

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`模型基础、Transformer、LoRA 与 RLHF`

典型原题：

- RL 相关训练方法

来源样例：

- [字节大模型 LLM 实习算法一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-byte-llm-algo-intern-round1.md)

## 109. 未完全归一化::Redis / MQ 在 AI 应用里的作用

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- Redis / MQ 在 AI 应用里的作用

来源样例：

- [分享 AI 应用开发面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-ai-app-dev-shared.md)

## 110. 未完全归一化::Redis ZSET、AOF、RDB、AOF 重写

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- Redis ZSET、AOF、RDB、AOF 重写

来源样例：

- [字节暑期剪映后端和AI agent一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-byte-jianying-backend-ai-agent-round1.md)

## 111. 未完全归一化::Redis 三剑客

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- Redis 三剑客

来源样例：

- [滴滴AI agent开发日常实习面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-09-didi-ai-agent-dev-intern.md)

## 112. 未完全归一化::Redis 出现大 key、大 value 会带来哪些问题

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- Redis 出现大 key、大 value 会带来哪些问题

来源样例：

- [指数引力 AI Agent 开发一面技术面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-11-zhishuyinli-ai-agent-dev-round1.md)

## 113. 未完全归一化::Redis 在增量更新环节如何使用，是否存在大 key、大 value 问题

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- Redis 在增量更新环节如何使用，是否存在大 key、大 value 问题

来源样例：

- [指数引力 AI Agent 开发一面技术面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-11-zhishuyinli-ai-agent-dev-round1.md)

## 114. 未完全归一化::Redis 基础与使用

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- Redis 基础与使用

来源样例：

- [阿里 AI Agent 开发一面 40min](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-22-ali-ai-agent-dev-round1.md)

## 115. 未完全归一化::ReentrantLock、公平非公平锁、AQS、CLH、自愈

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- ReentrantLock、公平非公平锁、AQS、CLH、自愈

来源样例：

- [字节暑期剪映后端和AI agent一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-byte-jianying-backend-ai-agent-round1.md)

## 116. 未完全归一化::SQL：统计每个商家的评论数并去重

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- SQL：统计每个商家的评论数并去重

来源样例：

- [淘天 AI Agent 二面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-07-taotian-ai-agent-round2.md)

## 117. 未完全归一化::SSE 中断续传如何设计

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- SSE 中断续传如何设计

来源样例：

- [某中厂 Agent 开发面经-日常实习](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-mid-company-agent-dev-intern.md)

## 118. 未完全归一化::SSE 和 WebSocket 的区别

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- SSE 和 WebSocket 的区别

来源样例：

- [快手前端 AI 应用开发一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-20-kuaishou-frontend-ai-app-dev-round1.md)

## 119. 未完全归一化::Sequence Packing 的原理和收益

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- Sequence Packing 的原理和收益

来源样例：

- [字节大模型 LLM 实习算法一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-byte-llm-algo-intern-round1.md)

## 120. 未完全归一化::TP 并行如何做

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- TP 并行如何做

来源样例：

- [快手 AI Infra 一面拷打](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-kuaishou-ai-infra-round1.md)

## 121. 未完全归一化::TaskRunner / 任务编排怎么设计

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- TaskRunner / 任务编排怎么设计

来源样例：

- [Soul AI Agent 实习二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-04-soul-ai-agent-intern-round2.md)

## 122. 未完全归一化::TensorRT 怎么优化

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- TensorRT 怎么优化

来源样例：

- [快手实习 AI Infra 一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-04-kuaishou-ai-infra-round1-alt.md)

## 123. 未完全归一化::Tool 调用链路怎么设计

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- Tool 调用链路怎么设计

来源样例：

- [字节跳动 AI 开发一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-byte-ai-dev-round1.md)

## 124. 未完全归一化::Top-k、Top-p 的实现原理

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`模型基础、Transformer、LoRA 与 RLHF`

典型原题：

- Top-k、Top-p 的实现原理

来源样例：

- [美团 Agent 算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-09-27-meituan-agent-algo-interview.md)

## 125. 未完全归一化::Triton / CUDA

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- Triton / CUDA

来源样例：

- [AI Infra 推理方向日常实习面经总结](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-ai-infra-inference-summary.md)

## 126. 未完全归一化::WebWorker 在前端 AI 应用里怎么用

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- WebWorker 在前端 AI 应用里怎么用

来源样例：

- [AI 应用开发实习面经 快手](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-20-kuaishou-ai-app-dev-intern.md)

## 127. 未完全归一化::Wide&Deep 模型原理是什么，Wide 和 Deep 分别解决什么问题

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- Wide&Deep 模型原理是什么，Wide 和 Deep 分别解决什么问题

来源样例：

- [淘天 AI Agent 二面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-07-taotian-ai-agent-round2.md)

## 128. 未完全归一化::XSS 风险怎么处理

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- XSS 风险怎么处理

来源样例：

- [AI 应用开发实习面经 快手](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-20-kuaishou-ai-app-dev-intern.md)

## 129. 未完全归一化::`GEMM`

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- `GEMM`

来源样例：

- [美团北斗 AI Infra 校招面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-28-meituan-beidou-ai-infra-campus.md)

## 130. 未完全归一化::`IPC`

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- `IPC`

来源样例：

- [字节 AI Infra 实习面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-28-byte-ai-infra-intern.md)

## 131. 未完全归一化::`SmoothQuant`

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- `SmoothQuant`

来源样例：

- [AI Infra 小厂实习面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-ai-infra-small-company-intern.md)

## 132. 未完全归一化::`all-reduce` 通信

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- `all-reduce` 通信

来源样例：

- [字节 AI Infra 实习面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-28-byte-ai-infra-intern.md)

## 133. 未完全归一化::`graph fusion`

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- `graph fusion`

来源样例：

- [字节 AI Infra 实习面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-28-byte-ai-infra-intern.md)

## 134. 未完全归一化::`prefix cache`

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- `prefix cache`

来源样例：

- [字节校招 AI Infra 后端面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-byte-ai-infra-backend-campus.md)

## 135. 未完全归一化::`prefix caching`

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- `prefix caching`

来源样例：

- [AI Infra 推理方向日常实习面经总结](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-ai-infra-inference-summary.md)

## 136. 未完全归一化::`sglang`

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- `sglang`

来源样例：

- [AI Infra 小厂实习面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-ai-infra-small-company-intern.md)

## 137. 未完全归一化::`speculative decoding`

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- `speculative decoding`

来源样例：

- [AI Infra 小厂实习面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-ai-infra-small-company-intern.md)

## 138. 未完全归一化::`static_cast`、`dynamic_cast`、`const_cast`、`reinterpret_cast` 的区别与底层含义

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- `static_cast`、`dynamic_cast`、`const_cast`、`reinterpret_cast` 的区别与底层含义

来源样例：

- [小鹏汽车 AI Infra 一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-02-xpeng-ai-infra-round1-50m.md)

## 139. 未完全归一化::agent 模块设计

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- agent 模块设计

来源样例：

- [字节校招 AI Infra 后端面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-byte-ai-infra-backend-campus.md)

## 140. 未完全归一化::emoji 表情包存储时涉及哪些 MySQL 存储相关知识

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- emoji 表情包存储时涉及哪些 MySQL 存储相关知识

来源样例：

- [指数引力 AI Agent 开发一面技术面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-11-zhishuyinli-ai-agent-dev-round1.md)

## 141. 未完全归一化::fallback 机制如何设计

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- fallback 机制如何设计

来源样例：

- [阿里淘天大模型 Agent 校招面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-27-taotian-llm-agent-campus.md)

## 142. 未完全归一化::k8s 在 Agent 系统里的使用场景

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`系统设计与项目深挖`

典型原题：

- k8s 在 Agent 系统里的使用场景

来源样例：

- [某中厂 Agent 开发面经-日常实习](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-mid-company-agent-dev-intern.md)

## 143. 未完全归一化::kernel 优化

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- kernel 优化

来源样例：

- [字节 AI Infra 校招一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-28-byte-ai-infra-campus-round1.md)

## 144. 未完全归一化::like 查询是否会失效

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- like 查询是否会失效

来源样例：

- [快手 AI Agent 开发实习生一二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-09-kuaishou-ai-agent-dev-intern-round12.md)

## 145. 未完全归一化::reduce 优化

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- reduce 优化

来源样例：

- [百融云创 AI Infra 面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-02-26-bright-ai-infra-offer.md)

## 146. 未完全归一化::token 相关基础

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- token 相关基础

来源样例：

- [有赞 Agent 开发实习一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-01-23-youzan-agent-dev-intern-round1.md)

## 147. 未完全归一化::tool 参数治理怎么做

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- tool 参数治理怎么做

来源样例：

- [AI 应用开发 华为校招二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-huawei-ai-app-dev-round2.md)

## 148. 未完全归一化::topk 截断怎么选

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- topk 截断怎么选

来源样例：

- [快手 Agent 开发一面 45min](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-21-kuaishou-ai-agent-dev-round1-45m.md)

## 149. 未完全归一化::workflow 是什么

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- workflow 是什么

来源样例：

- [百度 AI Agent 一面凉经-日常实习](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-12-baidu-ai-agent-round1-intern.md)

## 150. 未完全归一化::不同设备字段特征不一致时，怎么做统一化训练

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`模型基础、Transformer、LoRA 与 RLHF`

典型原题：

- 不同设备字段特征不一致时，怎么做统一化训练

来源样例：

- [快手大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-02-kuaishou-llm-algo-interview.md)

## 151. 未完全归一化::业务编排怎么做

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`系统设计与项目深挖`

典型原题：

- 业务编排怎么做

来源样例：

- [带得科技 大模型应用开发二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-daide-llm-app-dev-round2.md)

## 152. 未完全归一化::个人基本情况，有无实习经历

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 个人基本情况，有无实习经历

来源样例：

- [字节暑期剪映后端和AI agent一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-byte-jianying-backend-ai-agent-round1.md)

## 153. 未完全归一化::为什么想做金融大模型

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 为什么想做金融大模型

来源样例：

- [同花顺金融大模型算法一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-04-ths-finance-llm-algo-round1.md)

## 154. 未完全归一化::为什么选择这些数据策略

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 为什么选择这些数据策略

来源样例：

- [高德 AI Agent 算法一面面经 1h](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-01-31-gaode-ai-agent-algo-round1.md)

## 155. 未完全归一化::为什么需要 RAG

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- 为什么需要 RAG

来源样例：

- [百度 AI Agent 一面凉经-日常实习](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-12-baidu-ai-agent-round1-intern.md)

## 156. 未完全归一化::人类反馈如何被 Agent 消化，是否用 RL 更新策略

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- 人类反馈如何被 Agent 消化，是否用 RL 更新策略

来源样例：

- [字节大模型 Agent 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-30-byte-agent-algo-round2.md)

## 157. 未完全归一化::什么是 Modular Agent

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- 什么是 Modular Agent

来源样例：

- [阿里淘天大模型 Agent 校招面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-27-taotian-llm-agent-campus.md)

## 158. 未完全归一化::介绍实习公司中负责的关键词命中系统、文档提取系统的特色功能

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 介绍实习公司中负责的关键词命中系统、文档提取系统的特色功能

来源样例：

- [指数引力 AI Agent 开发一面技术面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-11-zhishuyinli-ai-agent-dev-round1.md)

## 159. 未完全归一化::从前端转 Agent 岗位的理解

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- 从前端转 Agent 岗位的理解

来源样例：

- [有赞 Agent 开发实习一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-01-23-youzan-agent-dev-intern-round1.md)

## 160. 未完全归一化::从大模型侧要做什么来适配 Agent

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- 从大模型侧要做什么来适配 Agent

来源样例：

- [得物大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-05-dewu-llm-algo-interview.md)

## 161. 未完全归一化::传统 RAG 的痛点有哪些

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- 传统 RAG 的痛点有哪些

来源样例：

- [美团 AI Agent 算法一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-16-meituan-ai-agent-algo-round1.md)

## 162. 未完全归一化::做 MySQL 治理时有哪些具体优化收获

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 做 MySQL 治理时有哪些具体优化收获

来源样例：

- [指数引力 AI Agent 开发一面技术面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-11-zhishuyinli-ai-agent-dev-round1.md)

## 163. 未完全归一化::做一个应用型 LLM 系统时，如何权衡效果、时延和成本

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 做一个应用型 LLM 系统时，如何权衡效果、时延和成本

来源样例：

- [大模型应用开发日常实习小厂面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-small-company-llm-app-dev-intern.md)

## 164. 未完全归一化::关键词命中系统优化的核心目标是什么，具体如何优化

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 关键词命中系统优化的核心目标是什么，具体如何优化

来源样例：

- [指数引力 AI Agent 开发一面技术面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-11-zhishuyinli-ai-agent-dev-round1.md)

## 165. 未完全归一化::分库分表

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 分库分表

来源样例：

- [阿里云 AI Agent 开发一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-aliyun-ai-agent-dev-round1.md)

## 166. 未完全归一化::前端如何做 AI 质量监控

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 前端如何做 AI 质量监控

来源样例：

- [AI 应用开发 Minimax 面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-27-minimax-ai-app-dev.md)

## 167. 未完全归一化::动态链接库依赖顺序

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 动态链接库依赖顺序

来源样例：

- [小鹏汽车 AI Infra 一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-02-xpeng-ai-infra-round1-50m.md)

## 168. 未完全归一化::协程基础

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 协程基础

来源样例：

- [字节跳动 AI 开发一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-byte-ai-dev-round1.md)

## 169. 未完全归一化::单体还是微服务怎么选

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 单体还是微服务怎么选

来源样例：

- [阿里云 AI Agent 开发一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-aliyun-ai-agent-dev-round1.md)

## 170. 未完全归一化::可用性设计

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 可用性设计

来源样例：

- [阿里云 AI Agent 开发一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-aliyun-ai-agent-dev-round1.md)

## 171. 未完全归一化::各步骤原理

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 各步骤原理

来源样例：

- [滴滴校招大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-14-didi-llm-algo-interview.md)

## 172. 未完全归一化::后端基础

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 后端基础

来源样例：

- [Agent 开发 字节面试被问麻了](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-09-byte-agent-dev-multi-round.md)

## 173. 未完全归一化::后端基础追问

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 后端基础追问

来源样例：

- [腾讯后台开发一面（含 AI 应用）](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-10-tencent-backend-ai-app-round1.md)

## 174. 未完全归一化::后端基础问题

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 后端基础问题

来源样例：

- [字节后端一面（含 RAG）](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-10-byte-backend-round1-with-rag.md)

## 175. 未完全归一化::向量嵌入怎么做

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 向量嵌入怎么做

来源样例：

- [AI 应用开发 华为校招二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-huawei-ai-app-dev-round2.md)

## 176. 未完全归一化::图数据库引入解决了什么问题

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`检索、召回与向量库`

典型原题：

- 图数据库引入解决了什么问题

来源样例：

- [字节暑期剪映后端和AI agent一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-byte-jianying-backend-ai-agent-round1.md)

## 177. 未完全归一化::在 AI 产品迭代中，如何平衡自研组件和成熟 AI UI 库

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 在 AI 产品迭代中，如何平衡自研组件和成熟 AI UI 库

来源样例：

- [AI应用开发实习面经-得物](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-05-dewu-ai-app-dev-intern.md)

## 178. 未完全归一化::在 RAG 系统中，前端如何优化长文档展示与引用来源跳转

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- 在 RAG 系统中，前端如何优化长文档展示与引用来源跳转

来源样例：

- [商汤科技Ai agent开发面经（攒人品）](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-05-sensetime-ai-agent-dev-round1.md)

## 179. 未完全归一化::在处理 AI 响应的长列表消息时，如何实现自动滚动到底部，同时保证用户手动向上滚动时不被干扰

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 在处理 AI 响应的长列表消息时，如何实现自动滚动到底部，同时保证用户手动向上滚动时不被干扰

来源样例：

- [淘宝直播 AI Agent 开发一面 55m](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-26-taobao-live-ai-agent-dev-round1.md)

## 180. 未完全归一化::在工程上如何处理 Agent 任务的状态管理与容错

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- 在工程上如何处理 Agent 任务的状态管理与容错

来源样例：

- [某中厂 Agent 开发面经-日常实习](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-mid-company-agent-dev-intern.md)

## 181. 未完全归一化::基于 AC 自动机构建违禁词匹配查询结构，在实际场景中如何实现

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`系统设计与项目深挖`

典型原题：

- 基于 AC 自动机构建违禁词匹配查询结构，在实际场景中如何实现

来源样例：

- [指数引力 AI Agent 开发一面技术面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-11-zhishuyinli-ai-agent-dev-round1.md)

## 182. 未完全归一化::多 key 场景下 Redis 订阅发布的轮询和监听如何处理

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`系统设计与项目深挖`

典型原题：

- 多 key 场景下 Redis 订阅发布的轮询和监听如何处理

来源样例：

- [指数引力 AI Agent 开发一面技术面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-11-zhishuyinli-ai-agent-dev-round1.md)

## 183. 未完全归一化::多租户场景下知识库和会话如何隔离

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- 多租户场景下知识库和会话如何隔离

来源样例：

- [某中厂 Agent 开发面经-日常实习](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-mid-company-agent-dev-intern.md)

## 184. 未完全归一化::大批量数据场景下，为什么 emoji 匹配要用 AC 自动机

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`系统设计与项目深挖`

典型原题：

- 大批量数据场景下，为什么 emoji 匹配要用 AC 自动机

来源样例：

- [指数引力 AI Agent 开发一面技术面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-11-zhishuyinli-ai-agent-dev-round1.md)

## 185. 未完全归一化::大模型后训练有哪些方式

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`模型基础、Transformer、LoRA 与 RLHF`

典型原题：

- 大模型后训练有哪些方式

来源样例：

- [美团 AI Agent 算法一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-16-meituan-ai-agent-algo-round1.md)

## 186. 未完全归一化::大模型应用开发中 RAG 的基本链路

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- 大模型应用开发中 RAG 的基本链路

来源样例：

- [适趣AI 大模型应用开发实习一面凉经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-23-shiquai-llm-app-dev-intern-round1.md)

## 187. 未完全归一化::如何优化 Agent，让它更智能

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- 如何优化 Agent，让它更智能

来源样例：

- [快手 AI Agent 开发实习生一二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-09-kuaishou-ai-agent-dev-intern-round12.md)

## 188. 未完全归一化::如何做 AI 应用的错误态和降级态设计

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 如何做 AI 应用的错误态和降级态设计

来源样例：

- [小红书 AI 开发二面-实习面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-xiaohongshu-ai-dev-round2-intern.md)

## 189. 未完全归一化::如何处理生成结果不稳定带来的产品体验问题

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 如何处理生成结果不稳定带来的产品体验问题

来源样例：

- [AI 应用开发 Minimax 面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-27-minimax-ai-app-dev.md)

## 190. 未完全归一化::如何实现一个简单的 Markdown 实时渲染引擎，并处理代码高亮

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 如何实现一个简单的 Markdown 实时渲染引擎，并处理代码高亮

来源样例：

- [淘宝直播 AI Agent 开发一面 55m](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-26-taobao-live-ai-agent-dev-round1.md)

## 191. 未完全归一化::如何对 MySQL 进行优化

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 如何对 MySQL 进行优化

来源样例：

- [字节 AI Platform 一面凉经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-26-byte-ai-platform-round1.md)

## 192. 未完全归一化::如何设计 AI Agent 工作流编辑器

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- 如何设计 AI Agent 工作流编辑器

来源样例：

- [AI 应用开发 Minimax 面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-27-minimax-ai-app-dev.md)

## 193. 未完全归一化::如何设计一个 AI 歌词生成系统

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 如何设计一个 AI 歌词生成系统

来源样例：

- [大模型应用开发校招面经-网易](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-07-netease-llm-app-dev-campus.md)

## 194. 未完全归一化::如何设计一套可观测的 AI 应用前端埋点

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 如何设计一套可观测的 AI 应用前端埋点

来源样例：

- [AI 应用开发 Minimax 面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-27-minimax-ai-app-dev.md)

## 195. 未完全归一化::如果 AI Agent 给出的排障建议与实际不符，怎么办

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- 如果 AI Agent 给出的排障建议与实际不符，怎么办

来源样例：

- [滴滴AI agent开发日常实习面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-09-didi-ai-agent-dev-intern.md)

## 196. 未完全归一化::如果做滴滴场景的 Agent，核心价值是什么

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`系统设计与项目深挖`

典型原题：

- 如果做滴滴场景的 Agent，核心价值是什么

来源样例：

- [滴滴 AI Agent 实习一面凉经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-10-didi-ai-agent-intern-round1.md)

## 197. 未完全归一化::如果回答流式输出中断，前端如何处理体验

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 如果回答流式输出中断，前端如何处理体验

来源样例：

- [小红书 AI 开发二面-实习面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-xiaohongshu-ai-dev-round2-intern.md)

## 198. 未完全归一化::如果某个 Agent 误判导致策略冲突，怎么处理

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- 如果某个 Agent 误判导致策略冲突，怎么处理

来源样例：

- [字节大模型 Agent 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-30-byte-agent-algo-round2.md)

## 199. 未完全归一化::如果系统出现网络抖动，而不是真故障，Agent 该如何判断

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- 如果系统出现网络抖动，而不是真故障，Agent 该如何判断

来源样例：

- [滴滴AI agent开发日常实习面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-09-didi-ai-agent-dev-intern.md)

## 200. 未完全归一化::如果线上回答不稳定，怎么排查

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 如果线上回答不稳定，怎么排查

来源样例：

- [适趣AI 大模型应用开发实习一面凉经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-23-shiquai-llm-app-dev-intern-round1.md)

## 201. 未完全归一化::如果要优化相关度和回答效果，有什么思路，如何体系化建设

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 如果要优化相关度和回答效果，有什么思路，如何体系化建设

来源样例：

- [快手 AI Agent 开发实习生一二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-09-kuaishou-ai-agent-dev-intern-round12.md)

## 202. 未完全归一化::如果让你设计一个 AI Agent 的工作流编排画布，类似 LangFlow，你会选什么技术栈，核心难点在哪

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- 如果让你设计一个 AI Agent 的工作流编排画布，类似 LangFlow，你会选什么技术栈，核心难点在哪

来源样例：

- [商汤科技Ai agent开发面经（攒人品）](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-05-sensetime-ai-agent-dev-round1.md)

## 203. 未完全归一化::如果让大模型实现类似 Cloud Code、Cursor 的编程工具，该如何实现

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 如果让大模型实现类似 Cloud Code、Cursor 的编程工具，该如何实现

来源样例：

- [指数引力 AI Agent 开发一面技术面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-11-zhishuyinli-ai-agent-dev-round1.md)

## 204. 未完全归一化::如果设计一个数据处理场景，例如一千条数据求和，如何处理

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`系统设计与项目深挖`

典型原题：

- 如果设计一个数据处理场景，例如一千条数据求和，如何处理

来源样例：

- [快手 AI Agent 开发实习生一二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-09-kuaishou-ai-agent-dev-intern-round12.md)

## 205. 未完全归一化::实际应用问题有哪些

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 实际应用问题有哪些

来源样例：

- [淘天 Agent 开发实习一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-17-taotian-agent-dev-intern-round1.md)

## 206. 未完全归一化::对 AI 大语言模型有什么了解

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 对 AI 大语言模型有什么了解

来源样例：

- [字节 AI Platform 一面凉经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-26-byte-ai-platform-round1.md)

## 207. 未完全归一化::对当前 Agent 能力的预期和现实差距怎么看

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- 对当前 Agent 能力的预期和现实差距怎么看

来源样例：

- [得物大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-05-dewu-llm-algo-interview.md)

## 208. 未完全归一化::对目标业务的理解

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`系统设计与项目深挖`

典型原题：

- 对目标业务的理解

来源样例：

- [滴滴 AI Agent 实习一面凉经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-10-didi-ai-agent-intern-round1.md)

## 209. 未完全归一化::工作流怎么搭建

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 工作流怎么搭建

来源样例：

- [阿里云 AI Agent 开发一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-aliyun-ai-agent-dev-round1.md)

## 210. 未完全归一化::布隆过滤器

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 布隆过滤器

来源样例：

- [快手 AI Agent 开发实习生一二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-09-kuaishou-ai-agent-dev-intern-round12.md)

## 211. 未完全归一化::常见 Agent 框架有什么区别

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- 常见 Agent 框架有什么区别

来源样例：

- [美团 AI Agent 算法一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-16-meituan-ai-agent-algo-round1.md)

## 212. 未完全归一化::平常用什么大模型

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`系统设计与项目深挖`

典型原题：

- 平常用什么大模型

来源样例：

- [零氪科技 NLP / RAG 面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-01-13-linkdoc-nlp-rag-rounds.md)

## 213. 未完全归一化::平时通过什么渠道跟进最新技术

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`系统设计与项目深挖`

典型原题：

- 平时通过什么渠道跟进最新技术

来源样例：

- [小红书 NLP 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-09-xiaohongshu-nlp-algo-round2.md)

## 214. 未完全归一化::开发 agent 使用的框架和语言分别是什么

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- 开发 agent 使用的框架和语言分别是什么

来源样例：

- [指数引力 AI Agent 开发一面技术面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-11-zhishuyinli-ai-agent-dev-round1.md)

## 215. 未完全归一化::异构文档如何处理

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 异构文档如何处理

来源样例：

- [A厂 Agent 开发一面面经题目整理](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-10-anonymous-agent-dev-round1.md)

## 216. 未完全归一化::张量并行

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 张量并行

来源样例：

- [字节 AI Infra 实习面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-28-byte-ai-infra-intern.md)

## 217. 未完全归一化::技术栈里是否考虑过 Hive、Spark 这类大数据链路

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 技术栈里是否考虑过 Hive、Spark 这类大数据链路

来源样例：

- [指数引力 AI Agent 开发一面技术面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-11-zhishuyinli-ai-agent-dev-round1.md)

## 218. 未完全归一化::数据处理场景怎么设计

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`系统设计与项目深挖`

典型原题：

- 数据处理场景怎么设计

来源样例：

- [AI Agent 开发二面 快手面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-21-kuaishou-ai-agent-dev-round2.md)

## 219. 未完全归一化::数据库存储和 RAG 是怎么做的

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- 数据库存储和 RAG 是怎么做的

来源样例：

- [字节暑期剪映后端和AI agent一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-byte-jianying-backend-ai-agent-round1.md)

## 220. 未完全归一化::数据构建怎么做

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 数据构建怎么做

来源样例：

- [字节大模型 LLM 实习算法一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-byte-llm-algo-intern-round1.md)

## 221. 未完全归一化::数据质量和筛选策略怎么做

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 数据质量和筛选策略怎么做

来源样例：

- [高德 AI Agent 算法一面面经 1h](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-01-31-gaode-ai-agent-algo-round1.md)

## 222. 未完全归一化::数据集包括什么

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 数据集包括什么

来源样例：

- [快手 AI Agent 开发实习生一二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-09-kuaishou-ai-agent-dev-intern-round12.md)

## 223. 未完全归一化::日常干活会用哪些 AI 工具

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`系统设计与项目深挖`

典型原题：

- 日常干活会用哪些 AI 工具

来源样例：

- [零氪科技 NLP / RAG 面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-01-13-linkdoc-nlp-rag-rounds.md)

## 224. 未完全归一化::最左前缀原则

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 最左前缀原则

来源样例：

- [字节暑期剪映后端和AI agent一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-byte-jianying-backend-ai-agent-round1.md)

## 225. 未完全归一化::有没有从 0 训练大模型的经历

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`模型基础、Transformer、LoRA 与 RLHF`

典型原题：

- 有没有从 0 训练大模型的经历

来源样例：

- [得物大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-05-dewu-llm-algo-interview.md)

## 226. 未完全归一化::构建 Agent 时遇到过哪些瓶颈

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- 构建 Agent 时遇到过哪些瓶颈

来源样例：

- [蚂蚁大模型 Agent 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-30-ant-agent-algo-round2.md)

## 227. 未完全归一化::消息可靠性如何保证

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 消息可靠性如何保证

来源样例：

- [AI Agent 开发二面-阿里](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-22-ali-ai-agent-dev-round2.md)

## 228. 未完全归一化::游戏公司目前在关注的 AI 漫剧 / 自动化内容方向，你会怎么做方案设计

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 游戏公司目前在关注的 AI 漫剧 / 自动化内容方向，你会怎么做方案设计

来源样例：

- [AI agent应用开发一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-ai-agent-app-dev-round1.md)

## 229. 未完全归一化::热点问题如何处理

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 热点问题如何处理

来源样例：

- [钉钉 Agent 应用开发一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-dingtalk-agent-app-dev-round1.md)

## 230. 未完全归一化::用两三句话介绍 Agent 以及当前挑战

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`Agent 基础与系统架构`

典型原题：

- 用两三句话介绍 Agent 以及当前挑战

来源样例：

- [美团 Agent 算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-09-27-meituan-agent-algo-interview.md)

## 231. 未完全归一化::画出典型的 RAG 结构

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`RAG 全链路`

典型原题：

- 画出典型的 RAG 结构

来源样例：

- [零氪科技 NLP / RAG 面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-01-13-linkdoc-nlp-rag-rounds.md)

## 232. 未完全归一化::知识图谱底层用什么数据结构存

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`检索、召回与向量库`

典型原题：

- 知识图谱底层用什么数据结构存

来源样例：

- [快手大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-02-kuaishou-llm-algo-interview.md)

## 233. 未完全归一化::稀疏多目标场景下，loss 怎么设计，既保证主目标收敛，又不让稀疏目标失效

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`模型基础、Transformer、LoRA 与 RLHF`

典型原题：

- 稀疏多目标场景下，loss 怎么设计，既保证主目标收敛，又不让稀疏目标失效

来源样例：

- [快手大模型算法面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-02-kuaishou-llm-algo-interview.md)

## 234. 未完全归一化::算法题：K 个一组反转链表

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 算法题：K 个一组反转链表

来源样例：

- [字节暑期剪映后端和AI agent一面面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-23-byte-jianying-backend-ai-agent-round1.md)

## 235. 未完全归一化::算法题：`2n+1` 个数两两成对，找出单独那个数

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 算法题：`2n+1` 个数两两成对，找出单独那个数

来源样例：

- [美团 AI Agent 算法一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-16-meituan-ai-agent-algo-round1.md)

## 236. 未完全归一化::系统稳定性怎么保障

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 系统稳定性怎么保障

来源样例：

- [钉钉 Agent 应用开发一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-dingtalk-agent-app-dev-round1.md)

## 237. 未完全归一化::线上大模型应用架构怎么设计

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 线上大模型应用架构怎么设计

来源样例：

- [带得科技 大模型应用开发二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-daide-llm-app-dev-round2.md)

## 238. 未完全归一化::线上问题定位

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`推理部署与性能优化`

典型原题：

- 线上问题定位

来源样例：

- [完美世界 AI Agent 开发一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-perfect-world-ai-agent-dev-round1.md)

## 239. 未完全归一化::结构化输出怎么做

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 结构化输出怎么做

来源样例：

- [大模型应用面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-12-26-llm-app-dev-general.md)

## 240. 未完全归一化::给出 CUDA Kernel 代码，识别其功能

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 给出 CUDA Kernel 代码，识别其功能

来源样例：

- [小鹏汽车 AI Infra 一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-02-xpeng-ai-infra-round1-50m.md)

## 241. 未完全归一化::缓存一致性怎么做

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 缓存一致性怎么做

来源样例：

- [钉钉 Agent 应用开发一面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-dingtalk-agent-app-dev-round1.md)

## 242. 未完全归一化::解释 JS 事件循环，并说明宏任务与微任务在处理 AI 消息推送时的先后顺序

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 解释 JS 事件循环，并说明宏任务与微任务在处理 AI 消息推送时的先后顺序

来源样例：

- [淘宝直播 AI Agent 开发一面 55m](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-26-taobao-live-ai-agent-dev-round1.md)

## 243. 未完全归一化::训练与 `RL` 工程优化

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`模型基础、Transformer、LoRA 与 RLHF`

典型原题：

- 训练与 `RL` 工程优化

来源样例：

- [阿里实习 AI Infra 面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-28-ali-ai-infra-intern.md)

## 244. 未完全归一化::训练样本质量问题会如何影响模型行为

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`模型基础、Transformer、LoRA 与 RLHF`

典型原题：

- 训练样本质量问题会如何影响模型行为

来源样例：

- [蚂蚁大模型 Agent 算法二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2025-11-30-ant-agent-algo-round2.md)

## 245. 未完全归一化::论文经历介绍

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 论文经历介绍

来源样例：

- [高德 AI Agent 算法一面面经 1h](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-01-31-gaode-ai-agent-algo-round1.md)

## 246. 未完全归一化::请求抢占怎么做

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 请求抢占怎么做

来源样例：

- [AI Infra 小厂实习面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-03-ai-infra-small-company-intern.md)

## 247. 未完全归一化::请简述 SSE 和 WebSocket 的区别，在 AI 流式输出场景下如何选择

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`系统设计与项目深挖`

典型原题：

- 请简述 SSE 和 WebSocket 的区别，在 AI 流式输出场景下如何选择

来源样例：

- [淘宝直播 AI Agent 开发一面 55m](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-26-taobao-live-ai-agent-dev-round1.md)

## 248. 未完全归一化::调度队列怎么设计

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 调度队列怎么设计

来源样例：

- [AI Infra 应届春招](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-24-ai-infra-campus.md)

## 249. 未完全归一化::谈谈对 CSS 容器查询的理解，它在 AI 侧边栏组件中有什么作用

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 谈谈对 CSS 容器查询的理解，它在 AI 侧边栏组件中有什么作用

来源样例：

- [淘宝直播 AI Agent 开发一面 55m](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-26-taobao-live-ai-agent-dev-round1.md)

## 250. 未完全归一化::过去一年如何利用 AI 工具提升前端开发效率

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 过去一年如何利用 AI 工具提升前端开发效率

来源样例：

- [AI应用开发实习面经-得物](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-05-dewu-ai-app-dev-intern.md)

## 251. 未完全归一化::还有算法题追问

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 还有算法题追问

来源样例：

- [阿里淘天大模型 Agent 校招面经](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-27-taotian-llm-agent-campus.md)

## 252. 未完全归一化::重试机制怎么做

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 重试机制怎么做

来源样例：

- [AI 应用开发实习面经 得物二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-20-dewu-ai-app-dev-round2.md)

## 253. 未完全归一化::错误态和降级怎么做

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 错误态和降级怎么做

来源样例：

- [快手 AI Agent 前端二面](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-20-kuaishou-ai-agent-frontend-round2.md)

## 254. 未完全归一化::面对快速迭代的 AI 技术，如何保证团队技术栈稳定性与前瞻性

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`其他未稳定归类问题`

典型原题：

- 面对快速迭代的 AI 技术，如何保证团队技术栈稳定性与前瞻性

来源样例：

- [商汤科技Ai agent开发面经（攒人品）](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-03-05-sensetime-ai-agent-dev-round1.md)

## 255. 系统设计题

- 归并次数：`1`
- 来源面经数：`1`
- 分类倾向：`系统设计与项目深挖`

典型原题：

- 系统设计或中间件基础

来源样例：

- [美团后端一面 Agent 开发](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/interviews/2026-02-27-meituan-backend-agent-dev-round1.md)

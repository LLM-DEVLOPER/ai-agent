# 其他中文社区采集稿

采集时间：2026-03-24

## 来源列表

1. 大模型面试百问百答（腾讯云开发者社区）
   https://cloud.tencent.com/developer/article/2397553
   日期：2024-03-18
2. Prompt Engineering 基础知识与挑战（腾讯云开发者社区）
   https://cloud.tencent.com/developer/article/2413713
3. 面向 Prompt 编程全攻略（腾讯云开发者社区）
   https://cloud.tencent.com/developer/article/2454105
4. 大模型-Agent LangGraph 面试八股文（知乎）
   https://www.zhihu.com/tardis/bd/art/32373609214
5. RAG 迅速落地实践（知乎）
   https://zhuanlan.zhihu.com/p/1960349249200944074
6. 腾讯基于 RAG 和 Agent 的混元落地实践（知乎）
   https://zhuanlan.zhihu.com/p/1961830228037985517
7. 通义实验室 - 大模型面经（知乎）
   https://zhuanlan.zhihu.com/p/27695292600
8. 夸克大模型算法面经（知乎）
   https://zhuanlan.zhihu.com/p/1969858660135076294
9. 大厂 RAG 面试题：24 个 RAG 八股文（博客园）
   https://www.cnblogs.com/crazymakercircle/p/18980652
10. 大模型评测方法（博客园）
    https://www.cnblogs.com/fxw-learning/p/18474878
11. 2024 大模型算法工程师面试题汇总（51CTO）
    https://blog.51cto.com/u_16163510/11639012
12. 2024 年最全 AI 大模型面试题合集（51CTO）
    https://blog.51cto.com/u_15404184/12789108
13. AI 大模型 2025 全套教程与面试指导（B 站）
    https://www.bilibili.com/video/BV1eQ6EYHE6z/
14. 2026 版 AI 大模型 LangChain 1.0 面试夺命连环 65 问（B 站）
    https://www.bilibili.com/video/BV1v5i7BYEz4/

## 题目整理

### 1. Agent 框架

- LangGraph 为什么是图而不是链？
- LangGraph 怎么支持多智能体协作？
- 如何让 LLM Agent 具备长期记忆？
- ReAct 的核心优点是什么？

### 2. Prompt

- 什么是 Prompt Engineering？
- Prompt 工程能解决什么问题？
- Prompt 工程的优势和边界是什么？
- 如何系统化优化提示词，而不是靠拍脑袋试错？

### 3. RAG / 知识库

- RAG 技术体系的整体思路是什么？
- 外挂知识库主要解决什么问题？
- 怎么评价一个 RAG 项目的好坏？
- 文档切分、向量化、检索、重排应该如何组织？
- RAG 落地时，业务理想和技术现实冲突时怎么取舍？

### 4. 评测

- 大模型评测有哪些通用指标？
- 公开评测集和业务测试集应该怎么组合？
- 检索评测和生成评测分别怎么看？

### 5. 安全与对齐

- 幻觉问题是什么？
- 复读机问题是什么？
- 如何缓解幻觉和重复生成？
- 如何保证生成内容合规？

### 6. 工程化

- 如何降低 API 服务的延迟和成本？
- 如何保证多轮对话一致性？
- LangChain 的 token 计数问题常见在哪里？
- vLLM 部署大模型时，吞吐和显存通常如何权衡？

### 7. 国内公司面经 / 系统设计

- 超长上下文一般怎么处理？
- MoE 相比 Dense 的训练难点是什么？
- 意图分流 Agent 怎么微调？
- embedding 微调如何构造正负样本？
- 业务接入 Agent 后，如何让系统稳定、快、可评估？

## 观察

- 这一层来源适合补“框架概念 + 工程常识 + 算法追问”。
- 相比 CSDN 和牛客，这些来源更容易补齐 `LangGraph / LangChain / RAG 落地 / 评测方法 / 长上下文 / MoE / vLLM`。
- 如果你的面试方向同时覆盖应用开发和算法，这一层一定要配合牛客一起看。

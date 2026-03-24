# 牛客网采集稿

采集时间：2026-03-24

## 来源列表

1. 大模型应用开发面经（5 年经验）
   https://www.nowcoder.com/feed/main/detail/129eaa1c20444651ac3b932e200d3da4
   日期：2025-07-27
2. 美团大模型产品转正实习面经（已 offer）
   https://www.nowcoder.com/feed/main/detail/1bf4cedab6ba4a3fb96a66178d4e4ea2
   日期：2025-03-26
3. 面试官：大模型评测的核心指标有哪些？
   https://www.nowcoder.com/feed/main/detail/2cd080b9db6b407ab48c33745e6c84a2
   日期：2025-03-21
4. 源络 NLP AI 算法面经
   https://www.nowcoder.com/feed/main/detail/d41020fcfb4547b98ca7609f52f78a98
   日期：2024-12-04
5. 好未来大模型面经
   https://www.nowcoder.com/feed/main/detail/01c48825391e4c22994f4bdc8f3e2f89
   日期：2024-04-23
6. 滴滴大模型一面面经
   https://www.nowcoder.com/creation/subject/278ae3e75eca413fa6f96d70cd03ae57
   日期：2024-08-15
7. AI Agent 应用开发一面面经
   https://www.nowcoder.com/feed/main/detail/416c3118a9c84fe0a43dc00f9eb9bec2
   日期：2026-03-03
8. 滴滴 AI Agent 开发日常实习面经
   https://www.nowcoder.com/feed/main/detail/9b2042a59f2e4d7cb0b2b43ceda5cdbb
   日期：2026-03
9. 大模型算法 Agent 八股整理（秋招面经）
   https://www.nowcoder.com/feed/main/detail/7567d685ec4c4533ba96c51af7c4d96b
   日期：2026-02-06
10. Agent 实习面经 - 阿里国际
    https://www.nowcoder.com/feed/main/detail/a1e6f0141e284dba99889d26342b33ef
    日期：2026-03
11. 淘天 Agent 算法一面 - 实习面经
    https://www.nowcoder.com/feed/main/detail/081a647969c54ae2b81d090fd5a50329
    日期：2026-01
12. 淘天 Agent 面经
    https://www.nowcoder.com/feed/main/detail/485fbcf14893475a8dbb137064ea34f5
    日期：2025-11-03

## 题目整理

### 1. Agent 系统设计

- 为什么要手搓 Agent，而不是直接用框架？
- Single-Agent 和 Multi-Agent 一般怎么设计？
- Agent 和 Workflow 的区别是什么？
- 如果给你一个“AI 漫剧创作”场景，如何设计完整 Agent 系统？
- 做复杂任务时，Agent 应该怎么拆步骤，拆得太细和太粗各有什么问题？

### 2. 工具调用 / MCP / ReAct

- Function Call 是怎么训练或实现的？
- MCP 是什么，和 Function Calling 的区别是什么？
- 你自己写过哪些 MCP 工具？
- ReAct 的几种模式怎么区分？
- 工具调用超时后如何降级？

### 3. RAG

- RAG 是什么，最难的环节在哪里？
- RAG 完整流程应该怎么讲？
- 文档切割怎么做，如何避免语义切坏？
- RAG 检索准确率怎么统计？
- 标准 RAG 系统应该包含哪些模块？
- chunk 优化、召回优化、重排优化分别怎么做？

### 4. 模型能力与幻觉

- 大模型幻觉怎么治理？
- Agent 给出的排障建议和真实情况不一致时怎么处理？
- 模型生成时出现循环和复读，如何排查？
- DPO 训完后输出长度变短或变长，怎么修？

### 5. 多轮对话与记忆

- 上下文管理一般怎么做？
- 长短期记忆分别怎么存，粒度应该多大？
- 多轮对话里为什么历史信息会逐渐衰减？
- 超长上下文下，记忆与检索如何配合？

### 6. 评估

- 回答效果怎么量化？
- 检索效果和回答效果应该分开看哪些指标？
- bad case 应该如何定义？
- 指令跟随能力一般如何评估？
- 大模型评测的核心指标有哪些？

### 7. 部署 / 高可用 / 成本

- 端到端延迟怎么优化？
- LLM 服务并发太高怎么办？
- Agent 服务高可用和稳健性怎么保证？
- 显存不够时可以做哪些优化？

### 8. 业务落地

- 垂类大模型主要解决什么问题？
- AI 产品怎么找到盈利模式？
- 如果做游戏客服助手，如何绑定游戏黑话和内部文档？
- 面试时如果岗位偏应用开发，为什么更爱追问“怎么上线、怎么评估、怎么赚钱”？

### 9. 项目追问

- 请你介绍项目，重点讲模块细节。
- 训练集和测试集怎么构建？
- 为什么选 Qwen，不选其他模型？
- 项目里最难的 bad case 是什么，如何解决？

## 观察

- 牛客最贴近真实面试，明显偏“系统设计 + 追问 + 项目复盘”，不是纯八股。
- 2025-2026 的趋势很明确：`Agent 架构`、`MCP / 工具调用`、`记忆`、`RAG 指标`、`上线稳健性`。
- 如果目标是国内公司的 AI Agent 应用开发岗，牛客这批题最值得反复过。

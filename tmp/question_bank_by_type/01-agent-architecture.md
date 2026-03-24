# Agent 基础与系统架构

频次：

- `Agent 基础 / 架构 / Workflow`：`92`
- 覆盖面经数：`56`

核心问题：

1. 什么是 `AI Agent`？它和普通 ChatBot 的区别是什么？
2. Agent 和 `Workflow` 的边界是什么？
3. 生产级 Agent 的核心模块有哪些？
4. 单 Agent 和多 Agent 如何选型？
5. Agent 为什么线上容易不稳定？
6. Router、Planner、Executor、Memory、Evaluator 怎么拆？
7. 通用 Agent 和垂直 Agent 怎么选？
8. Agent 平台和普通 AI 应用后端差异在哪里？

高频追问：

1. ReAct、Plan-and-Execute、Reflexion 的差异是什么？
2. Agent 为什么容易任务漂移？
3. Agent 的动作空间为什么要收敛？
4. 为什么很多业务最后做成“半 Agent、半 Workflow”？

回答抓手：

- 先讲 Agent 是系统，不是 Prompt
- 再讲 `感知 + 规划 + 记忆 + 工具 + 执行`
- 再讲生产要求：`可观测、可回放、可评估、可降级`

常见坑：

- 只会讲概念
- 不会讲线上失败模式
- 滥用多 Agent

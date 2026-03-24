# Agent 基础与系统架构

重要性：

- 高频程度：最高
- 对应原始题库：[01-agent-architecture.md](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/raw_question_source_by_type/01-agent-architecture.md)

## 这一类在考什么

这一类不只是考“你知不知道 Agent 这个词”，而是在考你是否能把 Agent 当成一个完整系统来理解。面试官通常想知道你有没有把 Agent 从 `demo` 视角切换到 `生产系统` 视角。

## 这一类的核心主线

回答 Agent 问题时，建议始终围绕这条主线：

1. `定义`
2. `核心模块`
3. `为什么需要`
4. `和 Workflow 的边界`
5. `生产系统为什么难`

## 必会主问题

1. 什么是 `AI Agent`？和普通 ChatBot 的区别是什么？
2. Agent 和 `Workflow` 的边界是什么？
3. 一个生产级 Agent 的核心模块有哪些？
4. 单 Agent 和多 Agent 怎么选？
5. Agent 为什么 demo 看着聪明，线上却容易脆？
6. Agent 的动作空间为什么一定要受限？
7. Agent 平台和普通 AI 应用后端有什么不同？
8. Router、Planner、Executor、Memory、Evaluator 应该怎么拆？
9. 通用 Agent 和垂直 Agent 应该怎么选？
10. Agent 为什么经常在真实业务里退化成“半 Agent、半 Workflow”？

## 高频追问

1. ReAct、Plan-and-Execute、Reflexion 分别适合什么任务？
2. Agent 的“自主性”应该放到什么程度？
3. 任务漂移、重复思考、无效工具调用的根源是什么？
4. 什么场景根本不应该做 Agent？
5. 如果业务要求高并发、低延迟、低成本，Agent 要砍掉哪些能力？

## 标准回答抓手

- 定义不要空泛，先讲 `目标驱动 + 可调用工具 + 有状态 + 可迭代执行`
- 一定强调 Agent 是 `系统`，不是一段 Prompt
- 讲模块时要讲边界，不要只列单词
- 讲难点时重点说：`稳定性、观测、容错、成本`

## 常见失分点

- 把 Agent 讲成“会自动调工具的聊天机器人”
- 不会说清 Agent 和 Workflow 的边界
- 无法解释为什么很多业务不适合上 Agent
- 不会讲生产级约束

## 最后该怎么复习

把这一类练到可以稳定回答三句话：

1. Agent 是什么
2. 为什么需要它
3. 为什么线上比 demo 难很多

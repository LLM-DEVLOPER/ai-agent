# Agent

## 1. 概念题

1. 什么是 `AI Agent`？
2. Agent 和普通 ChatBot 的根本区别是什么？
3. Agent 和 Workflow 的区别是什么？
4. 什么场景应该上 Workflow，什么场景必须上 Agent？
5. Agent 和传统自动化脚本的边界是什么？
6. Agent 和单纯的 Prompt orchestration 有什么不同？

## 2. 架构题

1. 一个生产级 Agent 至少应该包含哪些模块？
2. Router、Planner、Executor、Memory、Evaluator 应该怎么拆？
3. Observation 在 Agent 里扮演什么角色？
4. Policy / Guardrail 适合放在哪一层？
5. Agent 的动作空间为什么要收敛？
6. 工具系统应该归属于 Agent 内部还是外部服务层？
7. Agent 平台和普通 AI 应用后端最大的差异是什么？

## 3. 模式题

1. ReAct、Plan-and-Execute、Reflexion 分别适合什么任务？
2. 单 Agent 和多 Agent 应该怎么选？
3. DeepResearch 类 Agent 和普通任务型 Agent 有什么差异？
4. 通用 Agent 和垂直 Agent 应该怎么做取舍？
5. Agent 的“自主性”应该放到什么程度？
6. 如何限制 Agent 的试错成本？

## 4. 落地题

1. Agent 为什么 demo 看起来聪明，线上却很脆？
2. Agent 为什么容易任务漂移？
3. Agent 为什么容易出现重复思考和重复执行？
4. Agent 为什么会无效地反复调工具？
5. 如何让 Agent 系统变得可观测、可回放、可评估？
6. 如何解释“不是所有业务都适合做 Agent”？
7. 如果业务要求高并发、低延迟、低成本，Agent 该砍掉哪些能力？

## 5. 项目关联题

1. 你项目里的 Agent 架构是怎么设计的？
2. 为什么你们选择做 Agent，而不是纯 Workflow？
3. 你负责的是 Planner、Memory、Tool 还是编排层？
4. 线上最难的 bad case 是什么？
5. 如果让你重做一遍，你会改哪里？

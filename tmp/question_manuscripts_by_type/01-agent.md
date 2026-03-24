# Agent  (面试题整理版)

## 1. 为什么 Agent 这一类题这么重要？

如果你面的是 `AI Agent 开发`、`LLM 应用开发`、`Agent 平台` 相关岗位，那么 Agent 不是一个点状问题，而是一整条主线。很多面试会从“什么是 Agent”开场，随后一路追到 `架构拆分`、`执行流程`、`Agent 和 Workflow 的边界`、`为什么线上不稳定`，最后再回到你的项目上。也就是说，这一类题不是一题，而是一串题。

## 2. 面试官通常会怎么展开这一类题？

最常见的展开顺序大致如下：

1. 先问定义：你怎么理解 Agent。
2. 再问边界：它和 ChatBot、Workflow、自动化脚本有什么区别。
3. 再问架构：一个生产级 Agent 该怎么拆模块。
4. 再问能力：规划、记忆、工具、执行、观察分别起什么作用。
5. 再问落地：为什么 Agent 在线上经常不稳定。
6. 最后追到项目：你项目里的 Agent 是怎么设计的。

## 3. 第一层：概念开场题

1. 什么是 `AI Agent`？
2. Agent 和普通 ChatBot 的根本区别是什么？
3. Agent 和 Workflow 的区别是什么？
4. 什么场景应该上 Workflow，什么场景必须上 Agent？
5. Agent 和传统自动化脚本的边界是什么？
6. Agent 和单纯的 Prompt orchestration 有什么不同？

## 4. 第二层：架构拆分题

1. 一个生产级 Agent 至少应该包含哪些模块？
2. Router、Planner、Executor、Memory、Evaluator 应该怎么拆？
3. Observation 在 Agent 里扮演什么角色？
4. Policy / Guardrail 适合放在哪一层？
5. Agent 的动作空间为什么要收敛？
6. 工具系统应该归属于 Agent 内部还是外部服务层？
7. Agent 平台和普通 AI 应用后端最大的差异是什么？

## 5. 第三层：模式与能力题

1. ReAct、Plan-and-Execute、Reflexion 分别适合什么任务？
2. 单 Agent 和多 Agent 应该怎么选？
3. DeepResearch 类 Agent 和普通任务型 Agent 有什么差异？
4. 通用 Agent 和垂直 Agent 应该怎么做取舍？
5. Agent 的“自主性”应该放到什么程度？
6. 如何限制 Agent 的试错成本？

## 6. 第四层：落地与稳定性题

1. Agent 为什么 demo 看起来聪明，线上却很脆？
2. Agent 为什么容易任务漂移？
3. Agent 为什么容易出现重复思考和重复执行？
4. Agent 为什么会无效地反复调工具？
5. 如何让 Agent 系统变得可观测、可回放、可评估？
6. 如何解释“不是所有业务都适合做 Agent”？
7. 如果业务要求高并发、低延迟、低成本，Agent 该砍掉哪些能力？

## 7. 第五层：项目追问关联题

1. 你项目里的 Agent 架构是怎么设计的？
2. 为什么你们选择做 Agent，而不是纯 Workflow？
3. 你负责的是 Planner、Memory、Tool 还是编排层？
4. 线上最难的 bad case 是什么？
5. 如果让你重做一遍，你会改哪里？

## 8. 这一类题最容易和哪些类型串起来？

- `记忆 / 上下文工程`
- `工具调用 / Function Calling / MCP`
- `项目深挖`
- `系统设计`
- `多 Agent`

## 9. 原始题库参考

- [01-agent-architecture.md](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/raw_question_source_by_type/01-agent-architecture.md)
- [all_questions_normalized.md](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/raw_question_source_by_type/all_questions_normalized.md)

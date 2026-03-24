# Prompt、意图识别、规划与 ReAct

重要性：

- 高频程度：中高
- 对应原始题库：[06-prompt-planning-react.md](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/raw_question_source_by_type/06-prompt-planning-react.md)

## 这一类在考什么

本类重点不是“提示词技巧”，而是你是否能把 Prompt、意图识别、规划机制放回系统里看。

## 必会主问题

1. Prompt Engineering 的目标是什么？
2. 用户意图不完整时如何补全？
3. Prompt 如何约束结构化输出？
4. 什么情况下需要 ReAct？
5. Planner 失败时怎么恢复？
6. Prompt Injection 是什么？怎么防？
7. Prompt 优化和后处理规则的边界是什么？

## 高频追问

1. 为什么同一份 Prompt 在线上不稳定？
2. 什么时候该交给 Workflow，而不是继续让模型规划？
3. Prompt 自动优化能做到什么程度？

## 标准回答抓手

- Prompt 是约束设计，不是灵感创作
- 结构建议：`角色、目标、边界、格式、异常策略`
- 意图识别先决定“要不要调工具、要不要检索、要不要规划”

## 常见失分点

- 把 Prompt Engineering 讲成玄学
- 所有问题都想用 Prompt 解决
- 不会讲 Prompt Injection 的风险面

# Prompt、意图识别、规划与 ReAct  (面试题整理版)

## 1. 这一类题在考什么？

这一类不是考“提示词写得花不花”，而是在考你是否理解：Prompt、意图识别、规划机制和工具调用之间的边界。

## 2. 第一层：Prompt 基础题

1. Prompt Engineering 的目标是什么？
2. Prompt 如何约束结构化输出？
3. Prompt 优化和后处理规则的边界是什么？
4. 为什么同一份 Prompt 在线上可能不稳定？

## 3. 第二层：意图识别题

1. 用户意图不完整时如何补全？
2. 意图识别应该先于检索还是先于工具调用？
3. 意图识别失败会导致什么类型的错误？

## 4. 第三层：规划与 ReAct 题

1. 什么情况下需要 ReAct？
2. Planner 失败时怎么恢复？
3. 什么时候该交给 Workflow，而不是继续让模型规划？
4. ReAct 在什么场景下会明显失效？

## 5. 第四层：安全题

1. Prompt Injection 是什么？
2. 哪些路径最容易被注入？
3. Prompt 自动优化做到什么程度才值得在线上用？

## 6. 原始题库参考

- [06-prompt-planning-react.md](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/raw_question_source_by_type/06-prompt-planning-react.md)

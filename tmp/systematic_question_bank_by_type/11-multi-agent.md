# 多 Agent 协作

重要性：

- 高频程度：中
- 对应原始题库：[11-multi-agent.md](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/raw_question_source_by_type/11-multi-agent.md)

## 这一类在考什么

考的是你会不会在复杂度和收益之间做权衡，而不是为了听起来高级就上多 Agent。

## 必会主问题

1. 什么情况下值得上多 Agent？
2. 多 Agent 和单 Agent 的收益与成本是什么？
3. 多 Agent 状态共享怎么做？
4. 多 Agent 通信协议怎么设计？
5. 多个 Agent 结果冲突时谁来裁决？
6. 如何避免死循环、重复执行和互相推诿？

## 高频追问

1. 多 Agent 是否一定比单 Agent 好？
2. 多 Agent 如何做成本控制？
3. 检索 Agent、生成 Agent、评审 Agent 这种拆法什么时候值？

## 标准回答抓手

- 先讲收益：专业分工、并行化
- 再讲代价：状态复杂、观测困难、成本上升
- 最后讲角色边界和裁决机制

## 常见失分点

- 滥用多 Agent
- 不考虑状态同步
- 不知道裁决机制该怎么设计

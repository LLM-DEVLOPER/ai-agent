# 系统设计题

重要性：

- 高频程度：高
- 对应原始题库：[13-system-design-project.md](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/raw_question_source_by_type/13-system-design-project.md)

## 这一类在考什么

考的是你能不能把 `业务目标 -> 数据 -> 模型 -> 检索 -> 工具 -> 评测 -> 工程化` 串成一个完整方案。

## 高频题型

1. 设计一个企业知识库问答 Agent
2. 设计一个客服 Agent
3. 设计一个社区内容问答 / 生成 Agent
4. 设计一个 DeepResearch 类 Agent
5. 设计一个可观测、可灰度、可回放的 Agent 平台

## 推荐回答模板

1. 业务目标和用户是谁
2. 数据和知识源有哪些
3. 模型、检索、工具、记忆怎么选
4. 评测指标怎么定义
5. 工程化怎么落地：并发、容错、成本、发布

## 高频追问

1. 为什么不用纯 Workflow？
2. 为什么不用微调？
3. 预算很少时先做哪一层？
4. 最难的 bad case 是什么？

## 常见失分点

- 一上来只谈模型，不谈业务目标
- 不讲评测指标
- 不考虑成本、时延、容错

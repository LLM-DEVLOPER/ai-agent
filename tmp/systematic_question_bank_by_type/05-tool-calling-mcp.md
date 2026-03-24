# 工具调用、Function Calling 与 MCP

重要性：

- 高频程度：最高
- 对应原始题库：[05-tool-calling-mcp.md](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/raw_question_source_by_type/05-tool-calling-mcp.md)

## 这一类在考什么

不是考你会不会调 API，而是在考你是否理解“模型负责选择，系统负责治理”。

## 这一类的核心主线

1. `协议边界`
2. `调用正确性`
3. `失败恢复`
4. `多工具编排`
5. `可观测性`

## 必会主问题

1. Function Calling 是什么？
2. Tool Calling 和 Function Calling 的关系是什么？
3. MCP 是什么？核心价值是什么？
4. 工具 schema 和工具描述怎么写？
5. 为什么模型会误调、漏调、重复调工具？
6. 工具超时、失败、脏数据、权限错误如何兜底？
7. 多工具调度如何做？
8. 工具调用结果如何回写上下文？

## 高频追问

1. 如何让模型稳定输出结构化参数？
2. Prompt、schema、后处理、规则引擎分别解决什么问题？
3. MCP 和普通 HTTP API 的区别是什么？
4. 如何统计工具调用成功率？

## 标准回答抓手

- 模型只负责“选”，系统负责“校验、执行、回传、重试、降级”
- 一定讲：`参数校验、超时重试、熔断、幂等、审计`
- MCP 重点说标准化工具接入和扩展性

## 常见失分点

- 把工具调用讲成“模型自己会”
- 完全不讲异常路径
- 不知道 MCP 为什么会比散装工具好

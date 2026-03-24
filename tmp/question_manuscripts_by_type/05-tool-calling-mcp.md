# 工具调用、Function Calling 与 MCP  (面试题整理版)

## 1. 为什么这类题是 Agent 开发的硬主线？

因为很多所谓的 Agent 能力，最终都要落到“模型如何决定调用工具、系统如何保证调用可靠”这件事上。如果你讲不清这一层，Agent 基本就立不住。

## 2. 面试官通常怎么展开？

1. 先问 Function Calling 是什么。
2. 再问 Tool Calling 和 MCP 的边界。
3. 再问 schema、参数和工具描述怎么设计。
4. 再问工具失败、超时、脏数据怎么兜底。
5. 最后追到多工具调度和调用成功率。

## 3. 第一层：概念边界题

1. Function Calling 是什么？
2. Tool Calling 和 Function Calling 的关系是什么？
3. MCP 是什么？
4. MCP 和普通 HTTP API 的区别是什么？

## 4. 第二层：调用正确性题

1. 如何让模型稳定输出结构化参数？
2. 工具 schema 应该怎么写？
3. 工具描述应该怎么写，模型才更容易调用对？
4. 为什么模型会误调、漏调、重复调工具？

## 5. 第三层：异常处理题

1. 工具超时如何兜底？
2. 工具失败如何降级？
3. 脏数据和结构变化怎么处理？
4. 权限错误和鉴权失败怎么办？
5. 工具调用结果如何回写上下文？

## 6. 第四层：编排与观测题

1. 多工具调度如何做？
2. 工具调用成功率如何统计？
3. 如何减少无效工具调用？
4. 工具调用链条如何做日志和回放？

## 7. 原始题库参考

- [05-tool-calling-mcp.md](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/raw_question_source_by_type/05-tool-calling-mcp.md)

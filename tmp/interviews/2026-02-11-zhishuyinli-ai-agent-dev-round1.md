# 指数引力 AI Agent 开发一面技术面经

- 来源平台：牛客
- 原始 URL：https://www.nowcoder.com/feed/main/detail/e29b36c7ab554d3aa60fc4ec68150346?sourceSSR=%E5%85%B6%E4%BB%96
- 日期：2026-02-11
- 公司/岗位：指数引力 / AI Agent 开发
- 梳理状态：已完成首轮提炼
- 可信度：中高，基于搜索结果摘要整理，未拿到完整正文页

## 原始问题梳理

1. 介绍实习公司中负责的关键词命中系统、文档提取系统的特色功能
2. 基于 AC 自动机构建违禁词匹配查询结构，在实际场景中如何实现
3. 技术栈里是否考虑过 Hive、Spark 这类大数据链路
4. 关键词命中系统优化的核心目标是什么，具体如何优化
5. Redis 在增量更新环节如何使用，是否存在大 key、大 value 问题
6. Redis 出现大 key、大 value 会带来哪些问题
7. 多 key 场景下 Redis 订阅发布的轮询和监听如何处理
8. emoji 表情包存储时涉及哪些 MySQL 存储相关知识
9. 大批量数据场景下，为什么 emoji 匹配要用 AC 自动机
10. 做 MySQL 治理时有哪些具体优化收获
11. 介绍项目中的 AI 实践，以及对 React agent、Multi-agent 技术栈的理解
12. 某笔记管理网站的前后端技术栈如何选型
13. 腾讯云 MCP 的功能和工具能力有哪些
14. MCP、skill、function call 三个概念有什么区别和联系
15. function call 在 RAG 知识库中的业务逻辑如何实现
16. skill 被 agent 使用后是否占用上下文，它的优势是什么
17. 开发 agent 使用的框架和语言分别是什么
18. 如果让大模型实现类似 Cloud Code、Cursor 的编程工具，该如何实现
19. Multi-agent 中 plan 的设计思路是什么
20. 长任务执行后上下文接近阈值时，如何做上下文压缩
21. 开发 agent 时有哪些上下文管理方式，分别适合什么场景

## 分类整理

### 工程与系统

- 关键词命中系统、文档提取系统的功能和优化
- AC 自动机在违禁词匹配和 emoji 匹配中的应用
- Hive、Spark 这类大数据链路是否需要接入
- Redis 增量更新、大 key、大 value、订阅发布监听方案
- MySQL 治理和存储层优化

### Agent / MCP / Tool Use

- 对 React agent、Multi-agent 技术栈的理解
- 腾讯云 MCP 的功能和工具能力有哪些
- MCP、skill、function call 的区别和联系
- function call 在 RAG 知识库中的业务逻辑如何实现
- skill 被 agent 使用后是否占用上下文，它的优势是什么
- 开发 agent 使用的框架和语言分别是什么

### Agent 设计

- 如果让大模型实现类似 Cloud Code、Cursor 的编程工具，该如何实现
- Multi-agent 中 plan 的设计思路是什么
- 长任务执行后上下文接近阈值时，如何做上下文压缩
- 开发 agent 时有哪些上下文管理方式，分别适合什么场景

## 备注

- 这篇面经覆盖面很广，明显偏 `工程系统 + Agent 框架 + MCP / Function Call + 上下文管理`。
- 虽然部分内容来自搜索摘要，但题目密度高、结构完整，适合作为高频题池来源。

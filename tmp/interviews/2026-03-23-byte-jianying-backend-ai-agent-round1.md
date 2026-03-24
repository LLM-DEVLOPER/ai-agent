# 字节暑期剪映后端和AI agent一面面经

- 来源平台：牛客
- 原始 URL：https://www.nowcoder.com/feed/main/detail/01be970b368a42bc9173505a7ce91509?sourceSSR=enterprise
- 日期：2026-03-23
- 公司/岗位：字节 / 剪映后端与 AI Agent
- 梳理状态：已完成首轮提炼
- 可信度：高，页面正文可见

## 原始问题梳理

1. 个人基本情况，有无实习经历
2. 项目的整体架构是什么样的
3. Agent 的编排怎么做，用了什么模式，如何调度
4. 混合记忆架构怎么实现，短期记忆、长期记忆、记忆槽位怎么设计
5. 数据库存储和 RAG 是怎么做的
6. 项目中遇到过什么问题
7. token 消耗大，类似 MCP 的上下文协议占 token，如何降低消耗
8. 子 Agent 动态分配如何实现，如何提高任务执行和工具调用准确率
9. 图数据库引入解决了什么问题
10. HashMap 底层实现、扩容、冲突处理
11. ConcurrentHashMap 与 HashMap 区别
12. ReentrantLock、公平非公平锁、AQS、CLH、自愈
13. MySQL ACID
14. 最左前缀原则
15. Redis ZSET、AOF、RDB、AOF 重写
16. Kafka 高可用
17. 算法题：K 个一组反转链表
18. 反问

## 分类整理

### Agent 架构与调度

- 项目的整体架构是什么样的
- Agent 的编排怎么做，用了什么模式，如何调度
- 子 Agent 动态分配如何实现，如何提高任务执行和工具调用准确率

### 记忆与知识库

- 混合记忆架构怎么实现，短期记忆、长期记忆、记忆槽位怎么设计
- 数据库存储和 RAG 是怎么做的
- 图数据库引入解决了什么问题

### 工程优化

- token 消耗大，类似 MCP 的上下文协议占 token，如何降低消耗
- 项目中遇到过什么问题

### 基础八股与编码

- HashMap / ConcurrentHashMap
- ReentrantLock / AQS / CLH
- MySQL ACID / 最左前缀原则
- Redis ZSET / AOF / RDB
- Kafka 高可用
- 算法题：K 个一组反转链表

## 备注

- 这篇强度很高，是真正的 `Agent 项目深挖 + 后端八股 + 算法题` 混合面。
- 如果你的背景是 Java/后端做 Agent，这篇价值非常高。


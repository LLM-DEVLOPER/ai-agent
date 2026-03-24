# 字节大模型 Agent 算法二面

- 来源平台：牛客
- 原始 URL：https://www.nowcoder.com/feed/main/detail/52021a7b98024061a3e7d83ae762465e
- 日期：2025-11-30
- 公司/岗位：字节 / 大模型 Agent 算法二面
- 梳理状态：已完成首轮提炼
- 可信度：高，基于搜索摘要整理

## 原始问题梳理

1. 介绍 self-attention，并分析时间复杂度
2. 为什么要用 multi-head attention
3. PPO 的 clip 机制是什么
4. 在线强化学习和离线强化学习有什么区别，RLHF 属于哪一种
5. 为什么需要 reference model，它解决什么问题
6. 如何让多个 Agent 协同工作，举一个具体机制
7. 如果某个 Agent 误判导致策略冲突，怎么处理
8. 是否用过 AutoGen 或 LangChain，为什么选这个框架
9. Agent 的记忆系统怎么设计
10. 长期记忆如何存储，历史数据很大时如何优化查询效率
11. 是否做过记忆衰退，避免旧数据干扰新任务
12. 人类反馈如何被 Agent 消化，是否用 RL 更新策略
13. 是否做过模型压缩，车载端或低端设备如何推理加速
14. 量化后理解能力下降如何做精度补偿
15. 响应速度与推理精度之间如何权衡
16. 如果做电商 Agent，会选择哪些模态输入

## 分类整理

### Transformer 与强化学习

- self-attention 与 multi-head attention
- PPO clip、在线/离线 RL、RLHF
- reference model 的作用

### 多 Agent 与记忆系统

- 多 Agent 协同机制
- 冲突处理
- Agent 框架选型
- 长短期记忆设计与记忆衰退

### 推理优化与多模态

- 模型压缩与端侧推理
- 量化后的精度补偿
- 延迟与精度 tradeoff
- 电商 Agent 的多模态输入

## 备注

- 这篇强度很高，属于 `Transformer + RLHF + 多 Agent + 推理优化` 混合拷打。

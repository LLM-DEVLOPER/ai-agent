# 模型基础、Transformer、LoRA 与 RLHF  (面试题整理版)

## 1. 这一类题的真正作用是什么？

这类题不是要把你问成算法研究员，而是要确认你不只是“会调 API”，而是知道模型能力和应用方案是怎么接起来的。

## 2. 第一层：Transformer 基础题

1. Transformer 的核心结构是什么？
2. 为什么多头注意力有效？
3. Self-Attention 和 Cross-Attention 的区别是什么？
4. 位置编码为什么必要？

## 3. 第二层：微调题

1. LoRA、QLoRA、SFT、DPO、PPO 分别解决什么问题？
2. 什么时候该微调，什么时候只做 Prompt 和 RAG？
3. embedding 微调和生成模型微调的区别是什么？
4. 为什么 LoRA 足够高效？

## 4. 第三层：对齐与强化学习题

1. RLHF / DPO 对 Agent 能力提升主要体现在哪？
2. DPO 和 PPO 的差异是什么？
3. reference model 为什么需要存在？
4. 偏好对如何构造？

## 5. 第四层：开源模型认知题

1. Qwen、MoE、长上下文这些特性如何影响应用设计？
2. 长上下文能不能替代记忆系统？
3. 为什么不是所有问题都靠换模型解决？

## 6. 原始题库参考

- [10-model-foundation-finetuning.md](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/raw_question_source_by_type/10-model-foundation-finetuning.md)

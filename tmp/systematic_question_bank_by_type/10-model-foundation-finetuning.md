# 模型基础、Transformer、LoRA 与 RLHF

重要性：

- 高频程度：中高
- 对应原始题库：[10-model-foundation-finetuning.md](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/raw_question_source_by_type/10-model-foundation-finetuning.md)

## 这一类在考什么

不是考你会不会背论文，而是在考你是否有足够模型基础，能和应用侧决策接上。

## 必会主问题

1. Transformer 的核心结构是什么？
2. 为什么多头注意力有效？
3. Self-Attention 和 Cross-Attention 的区别是什么？
4. LoRA、QLoRA、SFT、DPO、PPO 分别解决什么问题？
5. Qwen、MoE、长上下文这些特性如何影响应用设计？
6. 什么时候该微调，什么时候只做 Prompt 和 RAG？
7. RLHF / DPO 对 Agent 能力提升主要体现在哪？

## 高频追问

1. LoRA 为什么高效？
2. DPO 和 PPO 的差异是什么？
3. 长上下文能不能替代记忆系统？
4. embedding 微调和生成模型微调的区别是什么？

## 标准回答抓手

- 不用讲到论文深度，但一定要自洽
- 把训练侧能力翻译成应用侧收益
- 回答时优先讲选择理由，不要只堆术语

## 常见失分点

- 基础概念混淆
- 只会背名词
- 不会把模型能力和业务方案连接起来

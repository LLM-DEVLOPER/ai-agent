# 模型基础、Transformer、LoRA 与 RLHF

频次：

- `模型基础 / Transformer / Attention`：`25`
- `微调 / 对齐 / RLHF`：`28`

核心问题：

1. Transformer 的核心结构是什么？
2. 为什么多头注意力有效？
3. Self-Attention 和 Cross-Attention 的区别是什么？
4. LoRA、QLoRA、SFT、DPO、PPO 分别解决什么问题？
5. Qwen、MoE、长上下文这些特性如何影响应用设计？
6. 什么时候该微调，什么时候只做 Prompt 和 RAG？
7. RLHF / DPO 对 Agent 能力提升主要体现在哪？

高频追问：

1. LoRA 为什么高效？
2. DPO 和 PPO 的差异是什么？
3. 长上下文真的能替代记忆系统吗？
4. embedding 微调和生成模型微调区别是什么？

回答抓手：

- 不必讲到论文级，但一定要自洽
- 把训练侧能力翻译成应用侧价值
- 回答时多讲选择理由，少堆术语

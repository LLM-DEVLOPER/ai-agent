# AI Agent / 大模型面试题采集说明

采集时间：2026-03-24

本目录按“先采集、后整理”的思路拆成两层：

当前主用目录：

- `baguwen_questions_by_type/`
  当前最新、正在持续打磨的 question 主库，按 15 个主题整理，适合直接学习和继续精修。
- `raw_question_source_by_type/`
  从 100 篇面经中逐题拆出的原始题库，适合作为回溯、查漏和补题参考。
- `interviews/`
  单篇面经目录，一个 URL 对应一份 markdown，适合按来源回看上下文。

- `raw_xiaohongshu.md`
  小红书相关公开来源汇总。注意：小红书站内公开索引较弱，部分题点来自招聘页、外部面经站、摘要页，文件内已标注 `基于摘要推断`。
- `raw_csdn.md`
  CSDN 面试题与面经整理，偏题库化、适合补八股和应用开发链路。
- `raw_nowcoder.md`
  牛客网面经整理，偏真实面试追问、项目追问、系统设计和业务落地。
- `raw_other_platforms.md`
  其他中文社区整理，包括知乎、腾讯云开发者、博客园、51CTO、B 站等。
- `high_quality_question_bank.md`
  跨来源去重、归类后的高质量题库，按面试场景重组，适合后续背诵和扩展答案。
- `source_pool_100_plus.md`
  第二轮扩采后的大来源池，当前保守收录 109 条中文公开来源，适合作为后续持续扩采基座。
- `strict_ai_agent_interview_urls_100_plus.md`
  严格按 URL 计数的一版，当前整理为 100 个独立链接，只收录 AI Agent / 大模型相关面经、面试题、经验帖、汇总帖。
- `pure_real_interview_urls_100.md`
  当前最接近目标口径的一版：100 个去重后的真实面经 URL，按 `AI Agent / 应用型 LLM / 算法推理` 分组。
- `interview_url_queue.md`
  当前边采边梳理的主队列，按 `agent / app / algo` 标记。
- `interview_url_queue_agent.md`
  AI Agent 优先队列。
- `interview_url_queue_app.md`
  大模型应用 / AI 产品队列。
- `interview_url_queue_algo.md`
  大模型算法队列。
- `interviews/`
  单篇面经 markdown 目录，一个 URL 对应一份整理稿。

使用建议：

- 先看 `high_quality_question_bank.md`，建立完整知识地图。
- 然后按目标岗位回看原始来源：
  Agent 应用开发优先看 `raw_nowcoder.md` 和 `raw_csdn.md`；
  算法/推理/微调补 `raw_other_platforms.md`；
  小红书相关岗位和业务风格看 `raw_xiaohongshu.md`。
- 后续如果要继续扩采，建议新增两个维度：
  `按公司维度`：阿里、腾讯、字节、美团、快手、小红书、滴滴、淘天、夸克、通义。
  `按岗位维度`：AI 应用开发、Agent 平台、RAG 工程、模型算法、推理部署、产品经理。

注意事项：

- 文件内容以公开可见网页、摘要、公开面经整理为主，不等于官方题库或逐字真题。
- 标记为 `基于摘要推断` 的内容，适合作为高频准备方向，不应当视为逐字原题。

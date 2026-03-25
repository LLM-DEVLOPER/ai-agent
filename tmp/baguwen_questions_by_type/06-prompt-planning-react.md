# Prompt、示例策略、规划与 ReAct

## 1. Prompt 的定义、作用与边界

1. 什么是 Prompt Engineering？
2. Prompt 在 LLM 应用里到底起什么作用？
3. 为什么 Prompt 不是简单的“多写几句提示词”？
4. Prompt 在 Agent 系统里为什么尤其重要？
5. Prompt 的核心价值通常体现在哪些方面？
6. 为什么很多线上问题最后都会继续追到 Prompt 层？

## 2. Prompt 的分层与组织方式

1. System Prompt、Developer Prompt、User Prompt 的边界是什么？
2. 指令、约束、上下文、示例这几部分通常分别在做什么？
3. 为什么 Prompt 一般不能只写成一整段自然语言？
4. Prompt 模板和运行时上下文的边界应该怎么划？
5. 为什么很多 Agent 系统都要把 Prompt 做成模块化配置？
6. Prompt 分层为什么有助于后续维护、调试和迭代？

## 3. Zero-shot、Few-shot 与示例策略

1. Zero-shot Prompting 和 Few-shot Prompting 的区别是什么？
2. 什么情况下 Zero-shot 就够了，什么情况下值得引入 Few-shot？
3. Few-shot 示例到底在帮助模型学什么？
4. 示例数量为什么不是越多越好？
5. 示例选择为什么会直接影响效果稳定性？
6. 正例、反例、边界样例分别适合解决什么问题？
7. Few-shot 示例通常应该放在 Prompt 的什么位置更合适？

## 4. CoT、推理提示与 Self-Consistency

1. 什么是 CoT（Chain-of-Thought），它在解决什么问题？
2. 为什么 CoT 对复杂推理任务通常更有效？
3. 什么任务特别适合显式 CoT，什么任务加了 CoT 收益反而不大？
4. CoT 和普通 Few-shot Prompt 的核心区别是什么？
5. 推理提示为什么经常会和任务拆解、步骤约束一起出现？
6. 什么是 Self-Consistency，它为什么常常和 CoT 一起出现？
7. 多次采样再聚合在解决什么问题，它的代价又体现在哪些方面？

## 5. Prompt 设计原则与稳定性问题

1. 一个好的 Prompt 一般具备哪些特征？
2. Prompt 设计时最重要的原则通常是什么？
3. 为什么 Prompt 既要清晰，又不能过度啰嗦？
4. 角色设定、任务定义、边界条件、拒答规则通常应该怎么组织？
5. 为什么示例、约束、输出格式三者经常要一起设计？
6. 为什么同一份 Prompt 在线上会表现不稳定？
7. Prompt 不稳定通常是 Prompt 本身的问题，还是链路协同的问题？

## 6. 意图识别与任务规划

1. 什么是意图识别，它为什么经常是执行前的第一步？
2. query 改写和意图识别的边界是什么？
3. 用户请求不完整时，为什么不能直接让模型“猜着做”？
4. 任务规划在 Agent 系统里到底解决什么问题？
5. 为什么不是所有任务都需要显式规划？
6. 什么时候应该先规划再执行，什么时候直接执行反而更好？
7. 任务拆解粒度过粗和过细分别会带来什么问题？

## 7. ReAct、Plan-and-Execute 与 Reflection

1. 什么是 ReAct，它为什么会成为 Agent 里的经典模式？
2. ReAct 在解决什么问题，它和单次直接回答的区别是什么？
3. ReAct 和 Plan-and-Execute 的区别是什么？
4. 什么任务特别适合 ReAct，什么任务用 ReAct 反而会变差？
5. 什么是 Reflection 或反思机制？
6. Reflection 在解决什么类型的错误，它和 ReAct 的关系是什么？
7. 什么时候值得加 Reflection，什么时候加了只会增加成本和时延？

## 8. Prompt、规划、工具和检索的协同

1. Prompt 和规划之间的关系是什么？
2. Prompt 和工具调用之间的关系是什么？
3. Prompt 和检索之间的关系是什么？
4. Prompt 里应该把工具约束写到什么程度？
5. 为什么很多工具误调、检索失效问题本质上也和 Prompt 有关？
6. Prompt、Planner、Tool Schema、检索上下文之间的边界通常应该怎么划？
7. 为什么 Prompt 一旦和工具、记忆、检索耦合，调试成本就会迅速上升？

## 9. Prompt Injection 与防护

1. 什么是 Prompt Injection？
2. Prompt Injection 和普通越权输入的区别是什么？
3. 为什么 Agent 场景下 Prompt Injection 风险更高？
4. 检索内容、网页内容、工具返回结果为什么都可能成为注入源？
5. Prompt Injection 在本质上是在攻击系统的哪一层？
6. 为什么“告诉模型不要被注入”通常不够？
7. Prompt Injection 应该从哪些层面防？
8. 指令隔离、上下文清洗、工具权限控制、输出约束、二次校验分别在解决什么问题？

## 10. Prompt 的管理、评测与项目深挖

1. Prompt 模板为什么需要版本管理、配置化和模板化？
2. Prompt 修改为什么最好能配合回放验证？
3. Prompt 迭代通常应该看哪些指标？
4. 如何判断一次 Prompt 改动是真的提升了效果，而不是只是碰巧命中样本？
5. Prompt 自动优化什么时候值得做，它的风险又是什么？
6. Agent 的规划与执行能力通常应该怎么评估？
7. 一个 Prompt / Planning 项目里的链路通常应该怎么设计？
8. 什么情况下值得做 Few-shot、CoT、Self-Consistency、意图识别、任务规划或 Reflection？
9. 线上最难处理的 Prompt / Planning bad case 通常是什么？
10. 如果重做一次这套 Prompt / Planning 体系，通常最值得优先改哪一层？

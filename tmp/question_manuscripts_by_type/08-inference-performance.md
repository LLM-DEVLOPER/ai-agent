# 推理部署与性能优化  (面试题整理版)

## 1. 为什么这类题不能只靠背名词？

因为面试官想听的不是你会不会说 `vLLM`、`KV Cache`、`FlashAttention`，而是你能不能把线上延迟拆回具体链路，并说清每种优化究竟解决哪一层的问题。

## 2. 第一层：链路拆解题

1. 大模型应用的端到端延迟由哪些环节组成？
2. 为什么很多系统的瓶颈不在模型本身？
3. 检索、工具、推理、后处理各自通常占什么比例？

## 3. 第二层：优化手段题

1. `vLLM`、`KV Cache`、`Batching`、`Streaming` 分别解决什么问题？
2. `FlashAttention`、`PagedAttention` 的优化对象是什么？
3. 显存不足时有哪些常见优化手段？
4. Prompt 裁剪为什么也是性能优化？

## 4. 第三层：工程治理题

1. 为什么线上必须做限流、超时、重试、熔断？
2. 模型路由如何平衡效果、成本、时延？
3. 延迟高时怎么判断是检索慢、工具慢还是推理慢？
4. 什么时候值得做异步化和任务队列化？

## 5. 原始题库参考

- [08-inference-performance.md](/Users/nako/WebstormProjects/github/thefoxfairy/interview/interview/tmp/raw_question_source_by_type/08-inference-performance.md)

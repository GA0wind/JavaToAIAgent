# Spring AI Observability

## 定义
Spring AI Observability 为 ChatClient、ChatModel、EmbeddingModel 和 VectorStore 等核心调用提供观测事件/指标/追踪集成，接入 Spring Boot 的观测基础设施。

## 原理
组件调用产生 observation，携带耗时、状态和低/高基数属性，并可传播 trace；提示与 completion 内容通常默认不导出，显式开启需考虑敏感数据风险。

## 为什么这样设计
AI 请求由多个远程调用构成，统一观测模型可串联业务与模型链路；区分低/高基数属性能控制指标存储规模。

## Java 工程关联
配置 Micrometer/OTel 导出与采样，补充业务 trace ID、用量和成本；不要将用户原文作为高基数标签或无保护日志。

## 高频面试题
1. **Spring AI 自动观测覆盖什么？**答题要点：按当前文档说明其核心组件，但业务自定义节点仍需埋点。
2. **提示正文默认不导出有何价值？**答题要点：保护隐私、控制数据量；排障时需授权、脱敏和限时采集。
3. **指标标签如何控制？**答题要点：低基数维度进指标，高基数 ID/内容放受控 trace 或日志。

## 自测
检查一个请求是否能从 Web 入站追到检索、模型与工具，并确认敏感内容未意外导出。

## 参考资料
- [Spring AI：Observability](https://docs.spring.io/spring-ai/reference/observability/index.html)，官方文档，访问日期：2026-11-10；属性和配置随版本变化。

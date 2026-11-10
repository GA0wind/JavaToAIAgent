# Agent Trace 与可观测性

## 定义
Trace 是一次请求跨模型、检索、工具和工作流节点的因果执行记录；Span 表示其中一个操作。Metrics 聚合数值，Logs 记录离散事件，三者互补。

## 原理
为一次请求生成 trace ID，各操作创建有父子关系的 span，记录耗时、状态和必要属性；将链路发送到观测后端，便于定位慢点和失败步骤。

## 为什么这样设计
Agent 由多次模型和工具调用组成，单条应用日志难以说明哪一步耗时或失败。分布式追踪提供跨组件因果链；敏感内容默认应脱敏/关闭记录。

## Java 工程关联
Spring AI 支持核心模型/向量组件的指标和追踪，Spring Boot/Micrometer/OTel 可接入后端。控制高基数标签和提示/回答采集，避免凭证与个人信息泄露。

## 高频面试题
1. **Trace、Metric、Log 有何区别？**答题要点：请求级因果链、聚合数值、离散事件；按问题组合使用。
2. **Agent Trace 应记录什么？**答题要点：节点名、模型/工具、耗时、状态、用量和安全的关联 ID；内容最小化。
3. **为什么提示内容不宜默认上报？**答题要点：可能含隐私/秘密，且体积和基数大；需授权、脱敏和保留策略。

## 自测
画一条 RAG+工具调用 trace，标出每个 span 的输入输出边界与脱敏字段。

## 参考资料
- [OpenTelemetry：What is OpenTelemetry?](https://opentelemetry.io/docs/what-is-opentelemetry/)，官方文档，访问日期：2026-11-10。
- [Spring AI：Observability](https://docs.spring.io/spring-ai/reference/observability/index.html)，官方文档，访问日期：2026-11-10；指标字段随版本变化。

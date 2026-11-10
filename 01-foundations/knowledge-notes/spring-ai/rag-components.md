# Spring AI RAG 组件

## 定义
Spring AI RAG 能力提供可组合的查询增强、检索、上下文组装和生成组件；Advisor 可快速接入常见问答模式，RAG 模块也提供更细粒度的模块化管线。

## 原理
通常先通过查询转换/增强得到检索查询，再从 VectorStore 或其他检索器获取文档，按策略压缩/排序，注入 Prompt 后调用模型；响应可关联来源文档。

## 为什么这样设计
将 RAG 常见步骤分解为可替换组件，便于适应不同语料和验证故障点；初始 Advisor 简化原型，复杂场景可显式编排而不把全部逻辑塞进一个调用。

## Java 工程关联
选定本项目 Spring AI 版本，分别测试文档解析、过滤、检索和生成；避免把教程中的默认 Advisor 当作完整生产 RAG。引用、无答案和租户隔离需自建评测。

## 高频面试题
1. **Advisor RAG 与模块化 RAG 如何选？**答题要点：简单流程用高层组件；需可控查询变换、重排/门槛、审计时显式组合。
2. **Spring AI RAG 能保证来源正确吗？**答题要点：提供组件不等于验证结论；应用需核验引用和支持关系。
3. **如何调试 RAG？**答题要点：逐段保存查询、候选、排序、上下文和输出，再结合标注集定位。

## 自测
写一条从 Document 到检索结果再到 ChatResponse 的数据流图，标出可以替换的组件。

## 参考资料
- [Spring AI：RAG](https://docs.spring.io/spring-ai/reference/api/retrieval-augmented-generation.html)，官方文档，访问日期：2026-11-10；API 随版本变化。
- [Spring AI：Advisors](https://docs.spring.io/spring-ai/reference/api/advisors.html)，官方文档，访问日期：2026-11-10。

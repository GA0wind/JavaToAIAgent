# Spring AI ETL Pipeline

## 定义
Spring AI ETL（Extract, Transform, Load）由 `DocumentReader`、`DocumentTransformer` 和 `DocumentWriter` 等组件组成，负责将原始资料读取、转换并写入 VectorStore 等目标。

## 原理
Reader 产生 Document；Transformer 清洗、切分或补充元数据；Writer 写入索引。Document 将文本与元数据在各阶段传递，流水线可以组合自定义处理器。

## 为什么这样设计
文档摄取与在线问答分离后，可单独批处理、重试和检查，且 Reader/Transformer/Writer 可替换。管线抽象也让内容质量和元数据治理显式化。

## Java 工程关联
将索引任务做成可重跑、可观测的后台流程；记录原文件版本、解析状态和 chunk 来源。默认 Reader/Tokenizer 只是组件，不一定适合所有 PDF、表格或中文结构。

## 高频面试题
1. **ETL 三个阶段分别做什么？**答题要点：读取来源、转换清洗/切分/增强、写入索引。
2. **Document 元数据有什么作用？**答题要点：过滤、追踪来源、引用定位和版本控制。
3. **如何处理增量更新？**答题要点：稳定 ID、文档版本、幂等写入、旧片段清理和失败重试。

## 自测
用合成文本从 Reader 到 VectorStore 走通一遍，额外验证元数据保留和重复导入。

## 参考资料
- [Spring AI：ETL Pipeline](https://docs.spring.io/spring-ai/reference/api/etl-pipeline.html)，官方文档，访问日期：2026-11-10；Reader/Transformer 实现随版本扩展。

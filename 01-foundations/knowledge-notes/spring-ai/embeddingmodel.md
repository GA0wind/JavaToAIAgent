# Spring AI EmbeddingModel

## 定义
`EmbeddingModel` 是 Spring AI 对文本向量化服务的抽象，把文本映射为 Embedding，并提供模型相关的响应/用量信息（依 Provider 支持）。

## 原理
应用提交一批文本，Provider 实现调用对应嵌入模型并返回向量；批处理、维度和请求大小受供应商限制。生成向量后可交给 VectorStore 写入或查询。

## 为什么这样设计
统一调用形状可替换嵌入服务和接入 Spring 配置；但向量空间由具体模型定义，切换不能只替换 Bean 而继续混用旧向量。

## Java 工程关联
使用相同兼容模型编码文档和查询；记录模型、维度、批次和索引版本。模型切换安排重嵌入、迁移和检索回归。

## 高频面试题
1. **ChatModel 和 EmbeddingModel 是一类东西吗？**答题要点：职责不同，前者生成聊天响应，后者生成向量表示。
2. **Embedding 维度变了怎么办？**答题要点：新索引/字段并重算语料向量，双读迁移并评估。
3. **批量向量化如何稳健？**答题要点：限批次、限并发、重试可恢复错误、失败隔离和进度记录。

## 自测
为批处理任务定义向量模型配置、失败重试和索引版本迁移记录。

## 参考资料
- [Spring AI：Embedding Models](https://docs.spring.io/spring-ai/reference/api/embeddings.html)，官方文档，访问日期：2026-11-10；Provider 能力随版本变化。

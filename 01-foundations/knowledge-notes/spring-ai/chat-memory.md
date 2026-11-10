# Spring AI ChatMemory

## 定义
`ChatMemory` 是 Spring AI 对对话历史保存/检索的抽象，用于在无状态模型 API 调用之间恢复必要上下文。`ChatMemory` 与用于展示的完整 Chat History 概念并不完全相同。

## 原理
应用提供 conversation ID，Advisor 在调用前读取相关消息并加入 Prompt，调用后按策略保存新消息；存储实现可为内存或持久化仓库，保留窗口可受限制。

## 为什么这样设计
模型本身通常不替应用跨请求保存状态；抽象仓库使应用能替换存储并控制上下文窗口。只保存必要历史可避免无限增长。

## Java 工程关联
会话 ID 不能作为授权凭据；需绑定认证主体/租户，设置 TTL、删除和容量策略。大对话用摘要/结构化状态辅助，不忽略 Token 预算。

## 高频面试题
1. **ChatMemory 与 ChatHistory 区别？**答题要点：Memory 是供推理选取和注入的信息；History 可用于审计/展示且可能更完整。
2. **如何避免会话越权？**答题要点：服务端将会话与主体绑定，校验每次访问并隔离存储。
3. **内存库适合生产吗？**答题要点：适合本地实验；多实例、重启恢复和合规需求需持久化实现。

## 自测
设计 conversation ID 与用户绑定方案，验证伪造他人 ID 无法读写历史。

## 参考资料
- [Spring AI：Advisors API](https://docs.spring.io/spring-ai/reference/api/advisors.html)，官方文档，访问日期：2026-11-10；接口和实现以项目版本为准。

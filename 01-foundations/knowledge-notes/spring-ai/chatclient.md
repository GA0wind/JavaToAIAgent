# Spring AI ChatClient

## 定义
`ChatClient` 是 Spring AI 面向应用层的流式/非流式聊天调用入口，提供类似 `WebClient` 的 fluent API，用于组合提示、参数、工具、Advisor 和响应处理。它是调用门面，不是模型本身。

## 原理
应用构建 Prompt 并调用 `call()` 或 `stream()`；ChatClient 将请求交给 `ChatModel`，并按 Advisor 链执行上下文增强、工具循环等横切逻辑，最后映射响应。自动配置可从 Spring Boot 容器提供 Builder。

## 为什么这样设计
链式 API 降低常见模型调用的样板代码，并利用 Spring DI/配置体系；分层把应用调用体验与底层 Provider 模型适配分开。

## Java 工程关联
与 `WebClient` 类比只限 fluent 调用体验，模型请求不是普通 REST DTO。默认配置适合通用参数，调用级配置用于特例；注意 Advisor 顺序和敏感日志。

## 高频面试题
1. **ChatClient 与 ChatModel 区别？**答题要点：前者是高层调用门面，可组合 Advisor；后者是模型 API 抽象。
2. **为何不直接用 ChatClient 实现业务流程？**答题要点：保留领域服务边界，长流程状态/权限/事务不应藏在调用链。
3. **如何测试 ChatClient 调用？**答题要点：抽象 Provider、固定输入输出样例，另做模型集成评测与脱敏。

## 自测
实现一个薄的 AI 应用服务，说明每次调用使用的默认与请求级参数。

## 参考资料
- [Spring AI：ChatClient API](https://docs.spring.io/spring-ai/reference/api/chatclient.html)，官方滚动文档，访问日期：2026-11-10；按项目版本核对。

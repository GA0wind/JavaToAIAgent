# Spring AI MCP 集成组件

## 定义
Spring AI MCP 集成通过 Spring Boot Starters 与注解支持构建 MCP Client/Server，让 Spring 应用消费或暴露 MCP 能力。它在协议实现外提供 Spring 配置、依赖注入和应用集成。

## 原理
Client Starter 配置传输并连接外部 Server；Server Starter 将应用中的工具、资源和提示注册为协议能力。当前不同 Starter 分别支持特定传输与 Web 技术，需按版本文档确认。

## 为什么这样设计
Java 应用无需从底层协议开始拼装，可利用 Spring Boot 配置和组件发现；将 MCP 服务化后也可供不同兼容客户端使用。

## Java 工程关联
区分 MCP Java SDK 与 Spring AI Starter 的职责；按目标使用场景选 client/server 和 MVC/WebFlux/stdio 依赖。连接远端服务时实现认证、授权、超时和可信端点管理。

## 高频面试题
1. **MCP Java SDK 与 Spring AI Starter 关系？**答题要点：SDK 提供协议层 API；Starter 集成 Spring Boot 与相应传输/配置。
2. **把业务方法加 MCP 注解就安全吗？**答题要点：不安全，仍需身份/权限校验、参数验证和审计。
3. **如何选择客户端/服务端 Starter？**答题要点：看应用是消费还是暴露能力及传输/Servlet 技术栈，并按版本确认兼容性。

## 自测
为一个只读查询服务挑选 Server Starter，列出传输、认证和权限检查点，不复制真实业务数据。

## 参考资料
- [Spring AI：MCP Overview](https://docs.spring.io/spring-ai/reference/api/mcp/mcp-overview.html)，官方文档，访问日期：2026-11-10；当前页面说明 Spring AI 2.x 组件，旧版坐标不同。

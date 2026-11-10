# Spring AI 自动配置与 Starter

## 定义
Spring AI Starter 是用于引入模型、向量存储或 MCP 等能力的依赖入口；自动配置依据 classpath、配置项和用户 Bean 创建默认组件。

## 原理
Spring Boot 条件装配检查依赖与属性，在满足条件且用户未提供替代 Bean 时注册配置；应用可通过属性配置 Provider，也可自定义 Bean 覆盖默认实现。具体条件随版本变化。

## 为什么这样设计
减少手工装配和重复配置，融入 Spring Boot 生命周期；条件化与可覆盖机制保留渐进定制空间。

## Java 工程关联
固定 Spring Boot/Spring AI BOM 与 Starter 版本；遇到 Bean 不符合预期时检查 classpath、条件报告、属性名和自动配置顺序。避免混用多个 Provider 的冲突默认 Bean。

## 高频面试题
1. **Starter 和自动配置一样吗？**答题要点：Starter 管依赖组合；自动配置是运行时条件注册机制。
2. **如何自定义默认 Bean？**答题要点：查看版本文档，通过用户 Bean/属性覆盖，并验证条件装配。
3. **为什么要锁版本？**答题要点：依赖坐标、属性、自动配置条件和 API 都可能变化。

## 自测
检查一个模型 Starter 从 Maven 依赖、配置属性到实际 Bean 的生效链路。

## 参考资料
- [Spring AI：API Overview](https://docs.spring.io/spring-ai/reference/api/)，官方文档，访问日期：2026-11-10；官方当前文档版本为 2.0.x，项目应按兼容矩阵选择。

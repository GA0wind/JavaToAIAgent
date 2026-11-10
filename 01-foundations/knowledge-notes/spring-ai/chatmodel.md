# Spring AI ChatModel 与 ChatResponse

## 定义
`ChatModel` 是 Spring AI 对聊天模型能力的核心抽象；`Prompt` 表示请求消息/选项，`ChatResponse` 封装模型返回结果及元数据。不同 Provider 实现该抽象并暴露特定选项。

## 原理
应用将消息与模型选项交给 ChatModel；Provider 适配器把公共请求映射成服务商协议，再将返回转换为 Spring AI 响应对象。流式能力由对应模型实现支持。

## 为什么这样设计
统一核心接口便于替换模型供应商和测试；仍保留 Provider 特定选项以免抽象抹掉有用能力。统一接口不等于各模型效果/参数相同。

## Java 工程关联
项目可在高层使用 ChatClient，需要精细控制或实现基础设施时才直接依赖 ChatModel。记录 provider/model、finish reason、usage 和错误信息，谨慎记录正文。

## 高频面试题
1. **模型适配抽象解决什么？**答题要点：统一调用形状与依赖注入；不消除服务商语义差异。
2. **ChatResponse 中哪些信息有用？**答题要点：生成结果、停止原因、用量和 Provider 元数据，按模型支持情况处理。
3. **何时用底层 ChatModel？**答题要点：需要自定义底层流程/基础设施或框架提供的高层入口不满足时。

## 自测
画出 ChatClient → ChatModel → Provider API → ChatResponse 的对象转换链。

## 参考资料
- [Spring AI：API Overview](https://docs.spring.io/spring-ai/reference/api/)，官方文档，访问日期：2026-11-10；当前索引为 2.x 文档，项目需核对兼容版本。

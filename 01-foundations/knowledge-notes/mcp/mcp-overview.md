# MCP（Model Context Protocol）

## 定义
MCP 是一种开放协议，用于让 AI 应用以标准方式连接提供上下文、工具和提示模板的外部服务。协议统一交互方式，但不自动授予业务权限。

## 原理
Host 管理用户交互和模型，Client 代表 Host 与 Server 建立协议连接；Server 声明能力并暴露 tools、resources、prompts 等原语。初始化阶段协商协议版本和能力，之后按传输方式交换请求/通知。

## 为什么这样设计
将模型应用与数据/工具提供方解耦，复用服务能力，减少每个客户端各自适配。标准化传输和发现不等于统一安全边界、身份或业务语义。

## Java 工程关联
将 MCP Server 视为外部 API：认证授权、输入校验、超时、审计和网络边界仍由服务端实现；客户端只连接可信端点并限制暴露能力。

## 高频面试题
1. **MCP 与 Tool Calling 有何区别？**答题要点：Tool Calling 是模型提出动作请求的交互模式；MCP 是应用/服务之间发现和调用能力的协议，可承载工具。
2. **MCP Server 能直接信任模型参数吗？**答题要点：不能，服务端必须按调用主体校验权限和输入。
3. **MCP 能力协商做什么？**答题要点：明确双方协议版本及可用能力，客户端据此决定可调用操作。

## 自测
画出 Host、Client、Server、模型和工具执行的边界，分别标注身份与数据流。

## 参考资料
- [MCP 官方文档](https://modelcontextprotocol.io/docs)，官方协议文档，访问日期：2026-11-10；协议/API 会演进。
- [Spring AI：MCP](https://docs.spring.io/spring-ai/reference/api/mcp/mcp-overview.html)，官方框架文档，访问日期：2026-11-10。

# MCP 面试题

[返回题库](README.md) · [概念](../../01-foundations/mcp/README.md) · 全部掌握状态：未开始。基础协议按 2025-06-18 版解释。

## MCP-01｜MCP 和 Function / Tool Calling、REST API 有什么区别？

- 优先级：P0；题源：[N02](../../02-resources/papers-and-articles/interview-sources.md#n02) 改写；依据：[F14](../../02-resources/official-docs/foundation-sources.md#f14)、[F07](../../02-resources/official-docs/foundation-sources.md#f07)。
- 考察点：层次划分。
- 回答要点：Tool Calling 是模型提出结构化调用的机制，MCP 规范应用如何发现和访问外部能力，REST 可继续承载底层业务接口。MCP 不替代模型，也不自动替代现有业务服务。固定本地工具可以直接调用，不要求强行增加 Server。
- 追问：现有 Java API 能接入吗？可由 MCP Server 适配，并保留认证、授权和错误语义。
- 验证要求：画出模型、Host、Client、Server、业务 API 五者关系。

## MCP-02｜Host、Client、Server 各做什么？

- 优先级：P0；题源：工程补充；依据：F14。
- 考察点：连接与安全边界。
- 回答要点：Host 管理 AI 应用、客户端与上下文；Client 管理与单个 Server 的协议连接；Server 暴露能力。一个 Host 可以管理多个 Client，能力和版本需要协商，不能将模型、最终用户和 Client 混为一谈。
- 追问：不同 Server 能默认读到彼此上下文吗？不能把能力连接当作共享所有会话数据的许可，应由 Host 控制传递范围。
- 验证要求：为两个只读 Server 标出连接数量和各自可见数据。

## MCP-03｜Tools、Resources、Prompts 分别用于什么？

- 优先级：P0；题源：工程补充；依据：[F16](../../02-resources/official-docs/foundation-sources.md#f16)。
- 考察点：能力建模。
- 回答要点：Tools 暴露操作，Resources 通过 URI 提供上下文，Prompts 提供可发现的参数化消息模板。规范中的模型、应用、用户控制定位描述交互方式，不意味着绕开执行和读取权限；返回内容也不自动可信。
- 追问：静态说明文档一定要建工具吗？可用资源承载，需结合客户端能力和读取方式决定。
- 验证要求：分别设计一个虚构工具、资源 URI 和模板参数，说明权限范围。

## MCP-04｜stdio 与 Streamable HTTP 怎么选？接通就安全吗？

- 优先级：P1；题源：N02 安全主题的工程补充；依据：[F15](../../02-resources/official-docs/foundation-sources.md#f15)、[F17](../../02-resources/official-docs/foundation-sources.md#f17)。
- 考察点：传输和授权不是同一层。
- 回答要点：stdio 常用于本地子进程，stdout 保持协议消息；Streamable HTTP 面向 HTTP 通信，可承载流式交互。需匹配协议版本，不能只会背旧 HTTP+SSE。连接成功不表示资源授权，必须做令牌范围校验、权限限制和可信端点配置，本地程序也不应任意读盘联网。
- 追问：为什么不能无校验透传令牌？接收者和授权范围可能不匹配，导致代理混淆和越权。
- 验证要求：说明本地与远程两种部署的身份来源、信任边界和拒绝路径。

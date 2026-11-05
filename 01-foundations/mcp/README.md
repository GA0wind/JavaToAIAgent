# MCP

目标：解释 MCP 标准化了哪一层，以及为什么它不替代权限与业务 API。关联第 9～11 周的扩展学习；[面试题 MCP-01～04](../../04-interview/question-bank/mcp.md)。整理日期：2026-11-05；个人掌握与实践状态：未开始。

## 角色与能力

本文基础协议以 **2025-06-18 修订版**为学习基线，不声称它是最新版本。实际实现前需确认所选 SDK 与 Server 的共同协议版本。

| 概念 | 职责 | 类比与边界 |
|---|---|---|
| Host | AI 应用，管理客户端、上下文与用户授权 | 应用容器和协调层，不是语言模型本体 |
| Client | Host 内负责与单个 Server 建立连接的协议组件 | 一个 Host 可有多个 Client；不是最终用户 |
| Server | 暴露能力和上下文 | 可包装现有 Java Service / REST API，不要求自行部署模型 |
| Tools | 可调用操作，包含描述和输入 Schema | 例如查询模拟状态，执行仍受应用策略约束 |
| Resources | 通过 URI 标识的上下文数据 | 不应把所有数据读取都理解为执行工具 |
| Prompts | 可发现和参数化的提示模板 | 不是可以覆盖 Host 权限的最高指令 |

规范中的交互定位通常是 Tools 由模型选择、Resources 由应用组织、Prompts 由用户选择；实际 UI 可有不同实现，不能据此取消服务端校验。依据：[F14](../../02-resources/official-docs/foundation-sources.md#f14)、[F16](../../02-resources/official-docs/foundation-sources.md#f16)。

## 连接与传输

通信使用 JSON-RPC；初始化阶段协商版本与能力。该基线定义 stdio 和 Streamable HTTP：前者通常用于本地子进程，通过标准输入输出通信，日志不应污染标准输出；后者用于 HTTP 通信，可利用 SSE 承载流式消息。不能把所有带 SSE 的接口都叫 MCP，也不能把旧版 HTTP+SSE 教程当作所有版本的唯一实现。依据：[F15](../../02-resources/official-docs/foundation-sources.md#f15)。

## 与 Tool Calling 的关系

Tool Calling 描述模型怎样提出结构化动作请求；MCP 描述应用如何发现和访问外部能力。两者可组合：`模型请求 → 应用校验 → MCP Client → MCP Server → 后端 API`。无需 MCP 也可直接注册本地工具；只做一次固定接口调用时，要权衡额外协议层的收益与维护成本。

## 安全边界

连接成功不代表用户被授权访问全部资源；工具描述和返回内容也可能不可信。只接受服务范围匹配的令牌，不把传入令牌无校验地透传给下游；本地子进程也需要最小文件和网络权限。安全指导页面核验时跳转到 2025-11-25 路径，与本文基础协议版本分开记录。依据：[F17](../../02-resources/official-docs/foundation-sources.md#f17)。

## 最小练习与验收（待执行）

先画出本地只读 Server 的 Host / Client / Server 和身份传递关系，再设计一个工具与一个资源。验收需记录协商版本、能力发现、一次成功读取、非法参数和越权拒绝；当前未安装 SDK、未启动 Server。

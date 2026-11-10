# MCP Resources

## 定义
MCP Resource 是 Server 以 URI 标识并向 Client 提供的上下文数据，例如文件、数据结构或应用信息。Resource 偏向可读取的数据表达，不等于 Agent 记忆或自动检索系统。

## 原理
Client 可列举资源、读取 URI 或参数化 Resource Template；Server 可声明资源变化通知/订阅能力。Host 决定如何把读取内容呈现或加入模型上下文。

## 为什么这样设计
以统一 URI 和内容类型发布上下文，让应用可按需选择和缓存；把数据读取与模型发起动作区分，便于设计权限和 UI。

## Java 工程关联
校验 URI scheme/path，阻止目录穿越、任意文件读取和跨租户访问；Resource 内容也视为不可信上下文，不能仅因来自 MCP Server 就当作安全指令。

## 高频面试题
1. **Resource 和 Tool 的核心区别？**答题要点：Resource 提供应用可读取的上下文；Tool 执行动作，可能有副作用。
2. **Resource 是否必然只读？**答题要点：协议语义是读取资源；改变系统状态应通过明确的 Tool/API。
3. **如何控制 Resource 权限？**答题要点：服务端对每次 URI 读取按调用者范围授权并过滤内容。

## 自测
设计一个带租户路径参数的 Resource Template，检查未授权 URI 和路径注入。

## 参考资料
- [MCP Specification：Resources](https://modelcontextprotocol.io/docs/concepts/resources)，官方协议文档，访问日期：2026-11-10；规范持续演进。

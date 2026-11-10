# MCP Tools、Resources 与 Prompts

## 定义
MCP Tools 是可由模型/客户端选择并执行的动作；Resources 是应用可读取并加入上下文的数据；Prompts 是用户或客户端选择的可复用消息模板。三者区分能力的控制方和用途。

## 原理
Server 声明原语及输入/输出契约；Client 发现可用能力。工具调用产生操作结果，资源通过 URI/模板读取，提示返回带参数的消息。协议定义传输和结构，具体业务含义由 Server 提供。

## 为什么这样设计
将“执行动作”“提供数据”“复用提示”分开，利于发现、授权和 UI 交互；客户端可按能力协商，不必把所有内容当作模型可调用函数。

## Java 工程关联
Resources 通常应有明确只读权限和 URI 访问校验；Tools 按风险分级；Prompts 不能替代后端输入校验。输出只包含调用者可访问数据。

## 高频面试题
1. **三种原语分别由谁驱动？**答题要点：工具通常由模型提出调用；资源由应用读取；提示由用户/客户端选择。
2. **工具与资源为何不能混用？**答题要点：副作用与控制方不同，混淆会造成权限和审计问题。
3. **MCP Schema 验证足够吗？**答题要点：只验证协议形状，业务授权、范围和语义仍需检查。

## 自测
为一个只读产品目录和一个查询工具分别定义 MCP 原语，并标注访问控制策略。

## 参考资料
- [MCP Python SDK：First Steps](https://py.sdk.modelcontextprotocol.io/get-started/first-steps/)，官方 SDK 指南，访问日期：2026-11-10；概念参考，示例语言为 Python。
- [MCP Java SDK：Server](https://java.sdk.modelcontextprotocol.io/latest/server/)，官方 Java SDK 文档，访问日期：2026-11-10；版本需与项目核对。

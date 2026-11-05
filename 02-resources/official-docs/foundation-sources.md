# 基础概念官方资料卡

统一访问日期：**2026-11-05**。以下均为第一手官方资料；核验结果只覆盖页面阅读与本轮引用内容。未运行框架示例，未验证具体提供商能力，未选定项目依赖版本。动态文档的发布日期未显示时不推测。

## F01

- 标题：LLM Course — Introduction；作者/来源：Hugging Face；类型：官方课程。
- 链接：[课程概览](https://huggingface.co/learn/llm-course/en/chapter1/1)。
- 发布日期或版本：持续更新在线课程，访问页未给出固定发布日期。
- 适用范围：LLM / NLP、Transformer、训练与推理的入门定位；不用于证明某个商业模型的当前能力。
- 核验状态：已核验页面与课程章节范围；实践未开始。
- 选择原因与核心内容：用官方课程建立模型应用与底层原理的关系，当前只取基础概念，不要求完整学习所有训练章节。

## F02

- 标题：LLM Course — Tokenizers；作者/来源：Hugging Face；类型：官方课程。
- 链接：[Tokenizers](https://huggingface.co/learn/llm-course/en/chapter2/4)。
- 发布日期或版本：持续更新在线课程，固定发布日期未显示。
- 适用范围：分词单位、Token ID 与模型输入；不能推导固定汉字换算率。
- 核验状态：已核验；尚未用选定模型的 Tokenizer 做计数实验。
- 选择原因与核心内容：理解字符、子词与模型输入的差异，避免用 Java 字符串长度估算 Token。

## F03

- 标题：Transformers — Generation；作者/来源：Hugging Face；类型：官方 API 文档。
- 链接：[生成参数](https://huggingface.co/docs/transformers/main_classes/text_generation)。
- 发布日期或版本：动态在线文档，本轮未固定 Transformers 包版本。
- 适用范围：temperature、top_p 等生成机制；不直接代表托管模型接口的参数或默认值。
- 核验状态：已核验参数定义；没有执行参数对照。
- 选择原因与核心内容：区分采样机制和事实正确性，具体接口支持应回到所用模型文档确认。

## F04

- 标题：Chat Client API；作者/来源：Spring AI / Spring；类型：官方文档。
- 链接：[ChatClient](https://docs.spring.io/spring-ai/reference/api/chatclient.html)。
- 发布日期或版本：访问页标示 Spring AI 2.0.2，动态 reference；不是项目锁定版本。
- 适用范围：ChatClient、消息组织、普通与流式调用。
- 核验状态：已核验页面与组件职责；未编译运行。
- 选择原因与核心内容：以 Java 熟悉的服务调用方式建立模型接入认识；实际开发需确认 Boot、JDK 和 AI 依赖兼容性。

## F05

- 标题：Output Converters；作者/来源：Spring AI / Spring；类型：官方文档。
- 链接：[输出转换](https://docs.spring.io/spring-ai/reference/api/structured-output/converters.html)。
- 发布日期或版本：访问页标示 Spring AI 2.0.2；旧路径 `api/structured-output-converter.html` 在核验时跳转到本链接。
- 适用范围：结构化文本解析、类型映射与 best-effort 边界，不承诺业务正确。
- 核验状态：已核验重定向与转换限制；未做 Schema 或 DTO 测试。
- 选择原因与核心内容：转换器在请求前提供格式信息，响应后映射类型；需区分转换、提供商原生约束与应用校验。

## F06

- 标题：Retrieval Augmented Generation；作者/来源：Spring AI / Spring；类型：官方文档。
- 链接：[RAG](https://docs.spring.io/spring-ai/reference/api/retrieval-augmented-generation.html)。
- 发布日期或版本：访问页标示 Spring AI 2.0.2，动态 reference。
- 适用范围：RAG 模块、查询变换、检索与后处理、元数据过滤；具体过滤实现需对照向量库。
- 核验状态：已核验；未建立知识库或评估数据。
- 选择原因与核心内容：连接概念与 Java 实现，理解空上下文处理及检索增强流程；框架引导模型拒答不等于应用已实现强保证。

## F07

- 标题：Tool Calling；作者/来源：Spring AI / Spring；类型：官方文档。
- 链接：[工具调用](https://docs.spring.io/spring-ai/reference/api/tools.html)。
- 发布日期或版本：访问页标示 Spring AI 2.0.2；文档明确区分 2.0 与 1.x 工具循环架构。
- 适用范围：工具定义、调用循环与执行职责；不同版本代码不可混用。
- 核验状态：已核验“模型请求、应用执行”的边界；未注册业务工具。
- 选择原因与核心内容：模型提供参数不代表授权，执行逻辑由应用拥有；本文不直接复制版本相关循环代码。

## F08

- 标题：Python Tutorial — 环境、数据结构与函数；作者/来源：Python Software Foundation；类型：官方教程。
- 链接：[虚拟环境](https://docs.python.org/3/tutorial/venv.html)、[数据结构](https://docs.python.org/3/tutorial/datastructures.html)、[函数及参数](https://docs.python.org/3/tutorial/controlflow.html)。
- 发布日期或版本：`/3/` 为动态 Python 3 文档，访问页显示 3.15.2；不是本地解释器或项目选型。
- 适用范围：venv、容器、可变默认参数等基础；版本相关新特性使用前需与本地解释器核对。
- 核验状态：已核验；尚未执行本文练习。
- 选择原因与核心内容：补齐 Java 开发者处理脚本环境、引用共享和函数参数时容易忽略的差异。

## F09

- 标题：Coroutines and Tasks；作者/来源：Python Software Foundation；类型：官方文档。
- 链接：[asyncio 任务](https://docs.python.org/3/library/asyncio-task.html)。
- 发布日期或版本：动态 Python 3 文档，访问页显示 3.15.2。
- 适用范围：协程、任务、超时与取消；具体 API 需匹配实际 Python 版本。
- 核验状态：已核验；无并发性能测试。
- 选择原因与核心内容：理解协作式调度、阻塞调用的影响及有界并发，避免把 async 当作自动加速。

## F10

- 标题：Observability；作者/来源：Spring AI / Spring；类型：官方文档。
- 链接：[可观测性](https://docs.spring.io/spring-ai/reference/observability/index.html)。
- 发布日期或版本：访问页标示 Spring AI 2.0.2，动态 reference。
- 适用范围：模型、Advisor、向量与客户端观测，Token 与耗时，日志内容控制。
- 核验状态：已核验；未接入监控平台或采集实际指标。
- 选择原因与核心内容：AI 调用需要关联多阶段耗时；指标和 trace 的标签基数与敏感原文导出需分别考虑。

## F11

- 标题：Evaluation Testing；作者/来源：Spring AI / Spring；类型：官方文档。
- 链接：[评估与测试](https://docs.spring.io/spring-ai/reference/api/testing.html)。
- 发布日期或版本：访问页标示 Spring AI 2.0.2；核验时旧 `evaluation-testing.html` 路径不可访问，改用当前可读页面。
- 适用范围：Evaluator 与模型辅助评审；不作为社区题频率或项目准确率证据。
- 核验状态：已核验可读页面；没有实际评审或基准分数。
- 选择原因与核心内容：把生成结果的内容评估纳入测试；模型评审不替代权限断言、业务检查和人工复核。

## F12

- 标题：pgvector README；作者/来源：pgvector 维护者；类型：官方源码仓库文档。
- 链接：[向量检索与过滤](https://github.com/pgvector/pgvector)。
- 发布日期或版本：访问时仓库默认分支文档，未固定 tag；不宣称项目已安装该版本。
- 适用范围：精确/近似近邻、距离、HNSW / IVFFlat、过滤与索引取舍。
- 核验状态：已核验 README，特别是过滤对近似候选数量的影响；未执行数据库实验。
- 选择原因与核心内容：用熟悉的 SQL/数据库认识向量检索；调参、查询计划及租户划分要在实际数据上验证。

## F13

- 标题：Cross-Encoder — Usage；作者/来源：Sentence Transformers 项目；类型：官方文档。
- 链接：[Cross-Encoder 使用](https://www.sbert.net/docs/cross_encoder/usage/usage.html)。
- 发布日期或版本：持续更新文档，未锁定包版本或具体模型。
- 适用范围：逐对评分与候选重排，性能取舍不代表所有场景必然提升。
- 核验状态：已核验特点说明；未做重排实验。
- 选择原因与核心内容：Cross-Encoder 需要对候选对计算，常用于召回后排序，不能直接修复不存在的候选。

## F14

- 标题：MCP Architecture；作者/来源：Model Context Protocol 项目；类型：官方规范。
- 链接：[架构](https://modelcontextprotocol.io/specification/2025-06-18/architecture)。
- 发布日期或版本：2025-06-18 修订版；历史学习基线，不声明最新。
- 适用范围：Host / Client / Server、能力协商与隔离职责。
- 核验状态：已核验指定版本页面；未建立协议连接。
- 选择原因与核心内容：明确模型、AI 应用与协议组件的区别；实现需再次匹配协议和 SDK 版本。

## F15

- 标题：MCP Transports；作者/来源：Model Context Protocol 项目；类型：官方规范。
- 链接：[传输](https://modelcontextprotocol.io/specification/2025-06-18/basic/transports)。
- 发布日期或版本：2025-06-18 修订版。
- 适用范围：JSON-RPC 消息、stdio 与 Streamable HTTP。
- 核验状态：已核验两类标准传输及 stdio 输出约束；未运行 Server。
- 选择原因与核心内容：区分协议、传输与旧版 SSE 教程；实际兼容性需单独测试。

## F16

- 标题：MCP Server Features — Tools / Resources / Prompts；作者/来源：Model Context Protocol 项目；类型：官方规范章节组。
- 链接：[Tools](https://modelcontextprotocol.io/specification/2025-06-18/server/tools)、[Resources](https://modelcontextprotocol.io/specification/2025-06-18/server/resources)、[Prompts](https://modelcontextprotocol.io/specification/2025-06-18/server/prompts)。
- 发布日期或版本：三章均为 2025-06-18 修订版。
- 适用范围：操作、URI 上下文与消息模板的能力区分及交互定位。
- 核验状态：三个章节均已访问核验；未设计完成可运行 Server。
- 选择原因与核心内容：按能力建模，不能把交互定位解释成自动授权。

## F17

- 标题：MCP Security Best Practices；作者/来源：Model Context Protocol 项目；类型：官方安全指导。
- 链接：[安全最佳实践](https://modelcontextprotocol.io/docs/2025-11-25/tutorials/security/security_best_practices)。
- 发布日期或版本：原 2025-06-18 安全链接访问时跳转到上述 2025-11-25 文档路径；不将其冒充为同版规范正文。
- 适用范围：代理混淆、令牌透传、会话与本地 Server 风险等安全边界。
- 核验状态：已于访问日核验指导内容；未做渗透测试或完整安全审计。
- 选择原因与核心内容：协议连通不等于授权；令牌需限定接收方及范围，本地程序也要控制权限。

## F18

- 标题：LLM01:2025 Prompt Injection；作者/来源：OWASP GenAI Security Project；类型：官方安全指南。
- 链接：[提示注入](https://genai.owasp.org/llmrisk/llm01-prompt-injection/)。
- 发布日期或版本：LLM Top 10 的 2025 分类页面；安全建议已于访问日复核。
- 适用范围：直接/间接提示注入与分层缓解；不是中国法律意见或完整合规结论。
- 核验状态：已核验定义与缓解原则；尚未执行安全用例。
- 选择原因与核心内容：将 Prompt 限制、输入输出验证、最小权限和高风险动作审核组合使用，避免声称单一提示能完全防御。

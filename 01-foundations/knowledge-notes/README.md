# AI Agent 工程知识点索引

这里是知识笔记的主体目录：**一篇笔记聚焦一个可以单独解释、练习和评估的知识点**。12 章课程页负责学习顺序和项目练习；此处负责概念本身，避免把整门课写进一个 README。每篇笔记统一包含定义、工作原理、设计原因、Java/Spring 关联、高频面试题答题要点、自测和来源。

## 怎么判断要不要拆成单篇

当一个概念有独立定义、需要独立练习/面试回答，或可能独立变化时，就单独建页；上下位关系通过链接组织。例如 RAG 是专题入口，混合检索、重排、引用溯源分别有自己的页。实现组件与通用原理分开：通用 Agent 工具调用与 Spring AI Tool Calling 各讲其边界。

## 按主题浏览

### 模型基础与调用

- [大语言模型（LLM）](core/llm.md)
- [Transformer 与注意力](core/transformer-attention.md)
- [Token 与分词器](../llm-basics/token-and-tokenizer.md)
- [上下文窗口与预算](core/context-window.md)
- [上下文工程](core/context-engineering.md)
- [KV Cache 与 Prompt Cache](core/kv-cache.md)
- [Prompt 设计与版本管理](core/prompt-engineering.md)
- [采样参数与非确定性](core/sampling.md)
- [幻觉与无依据回答](core/hallucination.md)
- [模型 API 与消息协议](core/model-api.md)
- [结构化输出与 Schema 校验](core/structured-output.md)
- [流式响应](core/streaming.md)
- [材料结构化抽取与人工复核](core/material-extraction-review.md)

### RAG 与检索

- [RAG 总览](rag/rag-overview.md)
- [文档解析与索引构建](rag/document-ingestion.md)
- [文档切块](rag/chunking.md)
- [Embedding](rag/embedding.md)
- [向量检索与向量数据库](rag/vector-search.md)
- [混合检索](rag/hybrid-retrieval.md)
- [重排（Reranking）](rag/reranking.md)
- [元数据过滤与租户隔离检索](rag/metadata-filtering.md)
- [引用与来源溯源](rag/citation-provenance.md)
- [无答案检测与拒答](rag/no-answer.md)
- [上下文压缩](rag/context-compression.md)
- [对话记忆与长期记忆](rag/memory.md)
- [Agentic RAG](rag/agentic-rag.md)
- [知识组织与结构化索引](rag/knowledge-organization.md)
- [用户记忆生命周期与审核](rag/memory-lifecycle.md)

### Agent 与工作流

- [Tool Calling](agents/tool-calling.md)
- [Agent 循环与停止条件](agents/agent-loop.md)
- [ReAct](agents/react.md)
- [Agent 规划](agents/planning.md)
- [Agent Workflow](agents/workflow.md)
- [Checkpoint 与状态恢复](agents/checkpoint.md)
- [子 Agent](agents/subagents.md)
- [多 Agent 架构](agents/multi-agent.md)
- [Agent 记忆](agents/agent-memory.md)
- [幂等与工具调用副作用](agents/idempotency.md)
- [Harness Engineering](agents/harness-engineering.md)
- [Agent Skills 与渐进式披露](agents/skills.md)
- [Agent 状态上下文](agents/context-state.md)
- [Agent 工具设计](agents/tool-design.md)
- [工具发现与按需加载](agents/tool-discovery.md)
- [提议者—审核者模式](agents/proposer-reviewer.md)
- [Coding Agent](agents/coding-agent.md)（进阶延伸）
- [事件驱动 Agent 运行时](agents/event-driven-runtime.md)（进阶延伸）
- [持续改进闭环](agents/continuous-improvement.md)（进阶延伸）
- [多 Agent 协作拓扑](agents/multi-agent-topologies.md)
- [多 Agent 失效模式](agents/multi-agent-failure-modes.md)

### MCP

- [MCP 协议总览](mcp/mcp-overview.md)
- [MCP Tools](mcp/tools.md)
- [MCP Resources](mcp/resources.md)
- [MCP Prompts](mcp/prompts.md)
- [Tools、Resources 与 Prompts](mcp/tools-resources-prompts.md)
- [传输、会话与生命周期](mcp/transport-and-lifecycle.md)

### 评测与可观测性

- [评测集与回归测试](evaluation/evaluation-dataset.md)
- [检索指标：Recall@K 与排序质量](evaluation/retrieval-metrics.md)
- [模型评分与 LLM-as-a-Judge](evaluation/model-grading.md)
- [答案质量：正确性、忠实度与引用质量](evaluation/answer-quality.md)
- [Agent Trace 与可观测性](evaluation/observability-tracing.md)
- [Token、成本与延迟](evaluation/cost-latency.md)
- [Agent 可靠性：Pass@k 与 Pass^k](evaluation/agent-reliability.md)
- [评测统计不确定性](evaluation/statistical-significance.md)

### 安全与上线

- [Prompt Injection](security/prompt-injection.md)
- [身份、权限与租户隔离](security/authorization-tenant-isolation.md)
- [权限沙箱与执行隔离](security/sandbox.md)
- [Agent 工具安全](security/tool-security.md)
- [超时、重试、降级与人工接管](security/reliability-fallback.md)
- [容器化部署、配置与健康检查](security/docker-health.md)

### 框架选型

- [LangChain](frameworks/langchain.md)
- [LangGraph](frameworks/langgraph.md)
- [AgentScope](frameworks/agentscope.md)
- [RAGFlow](frameworks/ragflow.md)
- [LangChain4j](frameworks/langchain4j.md)

### Spring AI 组件

- [ChatClient](spring-ai/chatclient.md)
- [ChatModel 与 ChatResponse](spring-ai/chatmodel.md)
- [Prompt 与 PromptTemplate](spring-ai/prompt-template.md)
- [Advisors](spring-ai/advisors.md)
- [Tool Calling 组件](spring-ai/tool-calling.md)
- [ChatMemory](spring-ai/chat-memory.md)
- [EmbeddingModel](spring-ai/embeddingmodel.md)
- [VectorStore](spring-ai/vectorstore.md)
- [Spring AI RAG 组件](spring-ai/rag-components.md)
- [Spring AI Observability](spring-ai/observability.md)
- [Spring AI 自动配置与 Starter](spring-ai/auto-configuration.md)
- [Spring AI ETL Pipeline](spring-ai/etl-pipeline.md)
- [Spring AI Evaluation API](spring-ai/evaluation.md)
- [Spring AI MCP 集成组件](spring-ai/mcp-integration.md)

## 16 周学习路径入口

| 周次 | 核心知识点 | 单篇笔记入口 |
|---|---|---|
| 1–2 | 模型调用、Token、采样、非确定性、结构化与流式 | [模型基础](core/llm.md)、[Token](../llm-basics/token-and-tokenizer.md)、[模型 API](core/model-api.md)、[结构化输出](core/structured-output.md)、[流式响应](core/streaming.md) |
| 3 | Prompt、上下文、记忆和压缩 | [Prompt](core/prompt-engineering.md)、[上下文窗口](core/context-window.md)、[上下文工程](core/context-engineering.md)、[KV Cache](core/kv-cache.md)、[对话记忆](rag/memory.md)、[上下文压缩](rag/context-compression.md) |
| 4 | 项目边界、安全和数据契约 | [模型 API](core/model-api.md)、[权限隔离](security/authorization-tenant-isolation.md)、[工具安全](security/tool-security.md) |
| 5–6 | RAG 管线、文档、Embedding、引用和无答案 | [RAG 总览](rag/rag-overview.md)、[索引构建](rag/document-ingestion.md)、[Embedding](rag/embedding.md)、[Agentic RAG](rag/agentic-rag.md)、[知识组织](rag/knowledge-organization.md)、[引用溯源](rag/citation-provenance.md)、[无答案](rag/no-answer.md) |
| 7 | 评测集与模型评分 | [评测集](evaluation/evaluation-dataset.md)、[答案评分](evaluation/model-grading.md)、[答案质量](evaluation/answer-quality.md)、[Pass@k/Pass^k](evaluation/agent-reliability.md)、[统计不确定性](evaluation/statistical-significance.md) |
| 8 | 检索优化 | [切块](rag/chunking.md)、[向量检索](rag/vector-search.md)、[混合检索](rag/hybrid-retrieval.md)、[重排](rag/reranking.md)、[检索指标](evaluation/retrieval-metrics.md) |
| 9–10 | Tool Calling 与权限治理 | [Tool Calling](agents/tool-calling.md)、[工具设计](agents/tool-design.md)、[工具发现](agents/tool-discovery.md)、[幂等](agents/idempotency.md)、[工具安全](security/tool-security.md)、[权限隔离](security/authorization-tenant-isolation.md)、[MCP](mcp/mcp-overview.md)、[MCP Tools](mcp/tools.md) |
| 11–12 | Agent 流程、ReAct、子 Agent、checkpoint、材料结构化抽取 | [Agent 循环](agents/agent-loop.md)、[Harness](agents/harness-engineering.md)、[ReAct](agents/react.md)、[规划](agents/planning.md)、[Workflow](agents/workflow.md)、[Checkpoint](agents/checkpoint.md)、[状态上下文](agents/context-state.md)、[子 Agent](agents/subagents.md)、[结构化输出](core/structured-output.md)、[材料预审](core/material-extraction-review.md) |
| 13–14 | 部署、Trace、成本、安全、降级上线 | [容器部署与健康检查](security/docker-health.md)、[可观测性](evaluation/observability-tracing.md)、[成本与延迟](evaluation/cost-latency.md)、[沙箱](security/sandbox.md)、[可靠性与降级](security/reliability-fallback.md)、[注入防护](security/prompt-injection.md)、[事件运行时](agents/event-driven-runtime.md)（延伸） |
| 15–16 | 框架对比、作品集和面试 | [框架选型](frameworks/langchain.md)、[LangGraph](frameworks/langgraph.md)、[AgentScope](frameworks/agentscope.md)、[RAGFlow](frameworks/ragflow.md)、[持续改进](agents/continuous-improvement.md)（延伸）、[Coding Agent](agents/coding-agent.md)（延伸）、[阶段路线图](../agent-engineering/README.md) |

## 框架/API 资料维护

框架介绍用于理解定位、核心组件和选型边界，不表示本项目已采用或完成实战。技术/API 类笔记记录本次查阅的官方来源和日期；真实开发前仍要按项目固定版本重新核对。新增知识点时，更新本索引及对应课程周次，不将多个独立机制塞入一个大纲文件。

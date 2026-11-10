# 会话记录：拆分 16 周计划中的原子知识点

- 日期：2026-11-10
- 类型：知识体系整理 / 文档组织
- 本次目标：将学习计划中可独立定义、解释、练习或面试考察的概念拆成单篇 Markdown，而不是只依赖 12 章课程页。

## 结构决定

- 16 周路线图仍负责顺序和阶段交付；12 章课程地图仍负责课程视角的路径、练习和验收。
- 新增 `01-foundations/knowledge-notes/` 作为原子知识点主体，按模型基础、RAG、Agent、MCP、评测、安全、框架生态和 Spring AI 组件分类。
- 每篇原子笔记按定义、工作原理、设计原因、Java/Spring 关联、面试题答题要点、自测、参考资料组织。
- 区分通用概念与框架实现，例如通用 Tool Calling 对照 Spring AI Tool Calling 组件；RAG 通用原理对照 Spring AI 和 RAGFlow 的实现定位。
- 技术/API 来源按 2026-11-10 访问的官方文档编写；依赖版本/API 细节在实际编码时仍需按项目版本核对。

## 本次产出

新增 69 篇独立知识笔记，覆盖：LLM/Transformer/Token/上下文/Prompt/采样/API/结构化输出/流式/材料抽取；RAG 管线、文档摄取、切块、Embedding、向量与混合检索、重排、权限过滤、引用、拒答、压缩和记忆；Tool Calling、幂等、Agent 循环、ReAct、规划、Workflow、Checkpoint、子 Agent、多 Agent；MCP 原语与传输；评测集、Recall@K、模型评分、答案质量、Trace、成本延迟；提示注入、租户隔离、沙箱、工具安全、降级和容器部署；LangChain、LangGraph、AgentScope、RAGFlow、LangChain4j；Spring AI ChatClient、ChatModel、PromptTemplate、Advisors、Tool Calling、ChatMemory、EmbeddingModel、VectorStore、RAG、ETL、Evaluation、MCP 与可观测组件。

新增知识点总索引 [knowledge-notes/README.md](../01-foundations/knowledge-notes/README.md)，将 16 周主题映射到具体单篇资料；并更新根 README、基础知识入口、课程地图和阶段进度。

## 验证

- 共 69 篇原子概念笔记；索引逐篇链接，未发现未收录条目；每篇均有定义、原理、设计原因、面试题、自测和来源。
- 扫描 72 份相关 Markdown 文件的本地链接、尾随空白和替换字符，未发现问题；`git diff --check` 通过。
- 不运行应用测试；未声称已完成项目实现或个人学习掌握。

## 遗留边界与下一步

- 资料覆盖计划范围，但框架介绍用于理解和选型，不代表采用了这些框架。
- 一些框架/API 页面是滚动文档，项目开发需锁定版本后再复核代码级细节。
- 建议按知识索引的 16 周映射学习；每周将自测答案和实际实验结果写入学习记录。

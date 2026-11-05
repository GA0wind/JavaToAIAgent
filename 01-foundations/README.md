# 基础知识

面向 Java / Spring 后端转 AI 应用开发，按“理解概念 → 回答面试题 → 做练习 → 留下证据”使用。本轮为资料整理，学习掌握程度与实验结果尚未验证。

## 阅读顺序

| 顺序 | 主题 | 读完应能解释 | 面试练习 |
|---|---|---|---|
| 1 | [LLM 基础](llm-basics/README.md) | Token、Transformer、上下文、采样、幻觉、微调 | [LLM-01～06](../04-interview/question-bank/llm-basics.md) |
| 2 | [Java 与 Spring AI](java-spring-ai/README.md) | 模型接入、结构化输出、流式响应、调用治理 | [JAVA-01～05](../04-interview/question-bank/java-spring-ai.md) |
| 3 | [Python](python/README.md) | 环境隔离、数据处理、生成器、异步 I/O | [PY-01～04](../04-interview/question-bank/python.md) |
| 4 | [RAG](rag/README.md) | 索引与查询、分块、检索、重排、引用 | [RAG-01～06](../04-interview/question-bank/rag.md) |
| 5 | [评估](evaluation/README.md) | 检索与答案指标、对照实验、成本和延迟 | [EVAL-01～05](../04-interview/question-bank/evaluation.md) |
| 6 | [Agent](agent/README.md) | 工具循环、工作流、状态、记忆与恢复 | [AGENT-01～06](../04-interview/question-bank/agent.md) |
| 7 | [MCP](mcp/README.md) | Host / Client / Server、能力与传输边界 | [MCP-01～04](../04-interview/question-bank/mcp.md) |
| 8 | [安全](security/README.md) | 提示注入、租户隔离、工具授权和日志边界 | [SEC-01～04](../04-interview/question-bank/security.md) |

第 1～3 周优先读前两项，Python 按脚本任务补齐；其余主题随 [16 周计划](../00-roadmap/16-week-plan/AI转型计划_Java工程师_16周路线图.md)展开。表中顺序是阅读建议，不表示调整原计划。

## 使用约定

- 每个主题含概念、Java 类比、易错点及待做练习；题库含考察点、回答要点、追问和验证要求。
- 所有业务练习均为虚构场景，不包含公司源码、TAPD 原文或真实业务规则。
- 来源与核验边界见 [资料索引](../02-resources/README.md)；联网核验日期为 2026-11-05。
- 练习完成后在 [学习笔记](../05-notes/learning-notes/README.md)记录实际输入、结果与失败案例，再更新进度。文档存在不代表本人已掌握。

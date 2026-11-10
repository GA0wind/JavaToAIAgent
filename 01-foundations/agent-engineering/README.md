# Agent 工程课程地图

本课程地图把 Agent 开发拆成“基础 → 原理 → 工程 → 就业”四阶段，章节依据用户提供的课程路线截图整理，并映射到仓库既有的 16 周学习计划。此处 12 章负责学习顺序、项目练习和验收；可独立学习的知识概念已经拆分为[原子知识点笔记](../knowledge-notes/README.md)，以单篇笔记作为概念详解入口。课程示例项目与本仓库主项目不同，练习统一落到本仓库现有的个人作品集项目和虚构数据上。

12 章页是课程讲义和项目练习入口，提供阶段性概念概览、验收证据和面试练习；详细知识拆到上面的单点笔记，避免把所有独立概念只放在章节大纲里。面试问题按已有题库和常见主题归纳，不代表量化过的市场频率。技术概念可以用于学习，框架/API 和岗位动态信息仍需查对应时点的官方资料。

## 学习路径

| 阶段 | 章节 | 资料 |
|---|---|---|
| 基础 | 01 基础入门 | [目标、范式与全程项目](01-foundation.md) |
| 基础 | 02 模型 API | [消息、流式与结构化输出](02-model-api.md) |
| 原理 | 03 原理够用 | [Token、上下文、Embedding 与模型边界](03-principles.md) |
| 原理 | 04 手写最小 Agent | [工具循环、终止条件与 Trace](04-minimal-agent.md) |
| 工程 | 05 工具、MCP、Skill | [工具契约与能力接入](05-tools-mcp-skills.md) |
| 工程 | 06 上下文与 RAG | [预算、检索、压缩与引用](06-context-rag.md) |
| 工程 | 07 规划与多 Agent | [状态、检查点与任务拆分](07-planning-multi-agent.md) |
| 工程 | 08 框架实战 | [框架比较与取舍](08-frameworks.md) |
| 工程 | 09 评测与可观测 | [评测集、指标与 Trace](09-evaluation-observability.md) |
| 工程 | 10 安全与上线 | [权限、注入防护与服务化](10-security-release.md) |
| 就业 | 11 岗位与面试 | [JD 拆解与证据化作答](11-jobs-interviews.md) |
| 就业 | 12 作品集与答辩 | [作品集、简历与结课答辩](12-portfolio-defense.md) |

## 与 16 周计划的对应

本表按课程章节概括每周任务；如果想按单个知识点学习，使用[原子知识点索引中的 16 周映射](../knowledge-notes/README.md#16-周学习路径入口)，每周条目会直接链接到对应概念页。

| 周次 | 本周主题 | 对应知识资料 |
|---|---|---|
| 1–3 | 模型 API、Token、Prompt、上下文、结构化与流式输出 | [第 2 章](02-model-api.md)、[第 3 章](03-principles.md)、[Token 笔记](../llm-basics/token-and-tokenizer.md)、[Java/Spring AI](../java-spring-ai/README.md) |
| 4 | 项目骨架、范围与业务边界 | [第 1 章](01-foundation.md)、[第 10 章](10-security-release.md)、[项目架构入口](../../03-projects/loan-platform-engineering-copilot/architecture/README.md) |
| 5–8 | RAG、来源引用、权限、评测和检索优化 | [第 6 章](06-context-rag.md)、[第 9 章](09-evaluation-observability.md)、[RAG 专题](../rag/README.md) |
| 9–10 | Tool Calling、业务工具安全和异常治理 | [第 5 章](05-tools-mcp-skills.md)、[第 10 章](10-security-release.md)、[Agent 专题](../agent/README.md) |
| 11–12 | 工作流、状态管理、结构化抽取与人工复核 | [第 4 章](04-minimal-agent.md)、[第 7 章](07-planning-multi-agent.md)、[第 2 章](02-model-api.md) |
| 13–14 | 部署、日志、指标、测试、安全与降级 | [第 9 章](09-evaluation-observability.md)、[第 10 章](10-security-release.md)、[Python 专题（脚本补充）](../python/README.md) |
| 15–16 | 项目包装、简历、面试与市场反馈 | [第 11 章](11-jobs-interviews.md)、[第 12 章](12-portfolio-defense.md) |

Python 是计划中的辅助能力，主要服务数据清洗和离线评估，不替换 Java/Spring 主线。环境隔离、数据结构和异步基础见 [Python 专题](../python/README.md)及对应[面试题](../../04-interview/question-bank/python.md)。

## 贯穿项目与完成口径

每章都围绕一个逐步增加能力的应用练习，避免只看视频。当前仓库主项目是 [Loan Platform Engineering Copilot](../../03-projects/loan-platform-engineering-copilot/README.md)，定位为使用合成或明确获授权材料的个人作品集，不代表已完成。课程介绍中的研发值班助手只作为课程案例，不替换本项目目标，也不复制公司源码、日志、需求或数据库结构。

底部能力链“能自己循环 → 能调用工具 → 能查文档 → 能多步排查 → 能衡量效果 → 能安全上线 → 能拿去面试”映射第 4～12 章。完成某章意味着留下相应代码、测试、报告或复盘证据；读完资料本身不算掌握。章节练习完成后，在 [学习笔记](../../05-notes/learning-notes/README.md) 记录日期、输入、结果、失败与证据路径，再按实际情况更新[阶段进度](../../00-roadmap/progress/README.md)。

## 原有专题资料

- [LLM 基础](../llm-basics/README.md) 与 [Java/Spring AI](../java-spring-ai/README.md)
- [Python](../python/README.md)
- [RAG](../rag/README.md)、[Agent](../agent/README.md)、[MCP](../mcp/README.md)
- [评估](../evaluation/README.md)、[安全](../security/README.md)
- [官方文档索引](../../02-resources/official-docs/README.md)和[资料卡](../../02-resources/README.md)

技术 API、模型能力、框架版本及招聘市场会变化；实际编码或求职前重新核对官方资料。每章优先连接仓库中已记录的来源，版本状态和访问日期以对应资料卡为准。

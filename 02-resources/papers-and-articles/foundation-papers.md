# 基础论文与原作者文章

以下统一访问日期为 **2026-11-05**，均为第一手来源。本轮核验题名、作者、版本信息与基础方法，不表示完成全文精读或实验复现。

## P01

- 标题：Attention Is All You Need；作者：Ashish Vaswani 等；类型：原始论文。
- 链接：[arXiv:1706.03762](https://arxiv.org/abs/1706.03762)。
- 发布日期或版本：v1 2017-06-12；访问页列 v7 2023-08-02。
- 适用范围：原始 Transformer、注意力与位置机制；不用于代替所有现代 LLM 架构说明。
- 核验状态：已核验基础机制与版本；未实现或复现翻译实验。
- 选择原因与核心内容：提供 Q/K/V、缩放点积注意力与 Encoder–Decoder 的原始来源；Decoder-only 等后续变体应另看对应模型资料。

## P02

- 标题：LoRA: Low-Rank Adaptation of Large Language Models；作者：Edward J. Hu 等；类型：原始论文。
- 链接：[arXiv:2106.09685](https://arxiv.org/abs/2106.09685)。
- 发布日期或版本：v1 2021-06-17；v2 2021-10-16。
- 适用范围：冻结基础权重并训练低秩增量，不代表量化或具体训练资源承诺。
- 核验状态：已核验方法及版本；未训练模型。
- 选择原因与核心内容：解释参数高效适配的矩阵形式；本文只做原理与虚构尺寸算例，不引用实验收益作为项目指标。

## P03

- 标题：Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks；作者：Patrick Lewis 等；类型：原始论文。
- 链接：[arXiv:2005.11401](https://arxiv.org/abs/2005.11401)。
- 发布日期或版本：v1 2020-05-22；v4 2021-04-12。
- 适用范围：参数化模型结合外部检索的基本思想；现代应用流水线不必复刻原论文训练方法。
- 核验状态：已核验方法定位与版本；未复现实验。
- 选择原因与核心内容：说明外部证据和模型生成可以组合；不能据此宣称 RAG 消除幻觉或保证当前业务事实正确。

## P04

- 标题：ReAct: Synergizing Reasoning and Acting in Language Models；作者：Shunyu Yao 等；类型：原始论文。
- 链接：[arXiv:2210.03629](https://arxiv.org/abs/2210.03629)。
- 发布日期或版本：v1 2022-10-06；v3 2023-03-10。
- 适用范围：推理与动作交替、依据观察继续决策；不表示所有 Agent 必须遵循同一框架。
- 核验状态：已核验基本方法与版本；未复现任务结果。
- 选择原因与核心内容：理解工具反馈怎样影响后续决策；工程审计依赖动作与结果，不要求暴露完整内部推理。

## P05

- 标题：Building effective agents；作者/来源：Anthropic Engineering；类型：原作者工程文章。
- 链接：[文章](https://www.anthropic.com/research/building-effective-agents)。
- 发布日期或版本：2024-12-19；原 `/engineering/` 链接核验时跳转到 `/research/`。
- 适用范围：Workflow 与 Agent 的概念区分、简单可组合模式和复杂度取舍；不作为当前 SDK 用法指南。
- 核验状态：已核验文章；页面提醒工具生态已有变化；未复现文中应用。
- 选择原因与核心内容：按任务确定控制流程，不因使用模型就默认采用自由规划；框架或托管产品细节需另查现行文档。

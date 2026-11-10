# LangChain

## 定义
LangChain 是用于构建 LLM 应用与 Agent 的框架，提供模型、提示、工具、检索、Agent 执行和中间件等组合能力。其语言实现、API 与版本线需区分。

## 原理
应用将模型调用、工具和上下文组装成可复用组件或 Agent；当前官方 Python 文档中，较高层 Agent 能力建立在 LangGraph 原语之上，复杂状态流程可直接使用 LangGraph。

## 为什么这样设计
高层接口缩短常见模式开发时间，生态集成降低连接成本；抽象也可能隐藏控制流和版本差异，所以需要理解运行时边界并锁定依赖版本。

## Java 工程关联
本计划主线是 Java/Spring AI；LangChain 用于理解 Python 生态招聘词汇与框架对比，不要求和 Spring AI 同时建设双主线。Java 可另看 LangChain4j。

## 高频面试题
1. **LangChain 与 LangGraph 的定位关系？**答题要点：LangChain 提供常见高层 Agent/组件；LangGraph 支持显式状态图和更细控制，二者可组合。
2. **框架能保证 Agent 正确吗？**答题要点：不能，正确性、安全与评测需应用层负责。
3. **如何避免框架锁定？**答题要点：分离领域服务与框架适配，固定版本并保留可替换接口。

## 自测
选一个简单检索工具流程，画出框架抽象与底层模型/工具调用链的对应关系。

## 参考资料
- [LangChain：Overview](https://docs.langchain.com/oss/python/langchain/overview)，官方文档，访问日期：2026-11-10；当前 API 可能迭代。

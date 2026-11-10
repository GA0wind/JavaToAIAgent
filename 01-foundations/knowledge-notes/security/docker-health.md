# 容器化部署、配置与健康检查

## 定义
容器化部署将应用及运行时依赖打包为可重复交付单元；配置在部署环境注入；健康检查用于判断实例是否可接流量或存活。

## 原理
镜像封装应用和启动命令，环境变量/Secret 提供环境差异；readiness 探针决定是否接流量，liveness 探针发现进程失活后重启。探针应反映服务能力，避免依赖短暂下游抖动导致重启风暴。

## 为什么这样设计
镜像可复现，配置与代码分离；探针能配合编排器滚动发布和恢复。模型服务是远程依赖，健康状态设计要区分应用进程健康与某次 Provider 不可用。

## Java 工程关联
多阶段构建、非 root 用户、只读文件系统、最小镜像；API Key 用 Secret/环境配置注入，不写入镜像或日志。分别暴露 liveness/readiness，限制探测频率和超时。

## 高频面试题
1. **Readiness 和 Liveness 区别？**答题要点：前者决定是否接流量，后者判断是否需要重启。
2. **模型 API 不可用时应用该不该不健康？**答题要点：取决于服务定义；通常需区分应用存活和能力降级，避免重启无效。
3. **容器有 Secret 为什么还要权限控制？**答题要点：Secret 仍可能通过进程/日志/镜像泄漏，需最小化访问并轮换。

## 自测
为 Spring Boot AI 服务编写镜像交付检查表，包含凭证、探针、资源限制和模型下游故障。

## 参考资料
- [Docker：Build best practices](https://docs.docker.com/build/building/best-practices/)，官方文档，访问日期：2026-11-10。
- [Spring Boot：Actuator Endpoints](https://docs.spring.io/spring-boot/reference/actuator/endpoints.html)，官方文档，访问日期：2026-11-10；端点配置随版本变化。

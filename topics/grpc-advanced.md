# gRPC 进阶专题

这个专题关注 gRPC 在 Python 项目中的代码生成、流式调用、拦截器和服务治理能力。

## 适用场景

- 内部服务间高性能 RPC
- 需要明确 schema 和多语言 SDK 的平台
- 流式日志、推送、模型推理和长连接接口

## 常见主题

- `.proto` 设计
- 代码生成
- unary / stream 模式
- 拦截器与元数据
- 超时、重试和可观测性

## 设计要点

- `.proto` 设计要先考虑兼容，再考虑语法便利
- 服务超时、截止时间和重试策略必须统一约束
- gRPC 更适合内部调用，不天然替代公网 API
- 生成代码、发布 SDK 和接口评审要纳入流程

## 关联阅读

- [grpcio](../third_party/grpc.md)
- [grpcio-tools](../third_party/grpcio_tools.md)
- [API 开发专题](./api-development.md)
- [HTTP/2 与流式响应专题](./http2-and-streaming.md)
- [代理与 Egress 治理专题](./proxy-and-egress.md)
- [Triton 推理服务专题](./triton-inference-serving.md)

返回 [索引](../README.md)

# Schema Registry 专题

这个专题关注事件载荷和流式数据结构如何被集中管理、版本化和兼容检查。

## 适用场景

- Kafka 事件的 Avro / Protobuf / JSON Schema 治理
- 多团队共享主题和消费者模型
- 需要控制字段演进和兼容策略的流处理平台

## 常见主题

- schema 注册与 subject 命名
- backward / forward / full compatibility
- 序列化与反序列化策略
- 默认值、可空字段和枚举演进
- 消费者升级顺序

## 设计要点

- 兼容策略要和真实发布顺序匹配，而不是只看理论定义
- schema 文档要覆盖字段语义，不只是类型
- 事件 topic、subject、领域模型三者需要清晰映射关系
- 要有失败数据旁路和坏消息观测机制

## 关联阅读

- [流处理专题](./stream-processing.md)
- [数据契约专题](./data-contracts.md)
- [Schema 演进专题](./schema-evolution.md)
- [gRPC 进阶专题](./grpc-advanced.md)

返回 [索引](../README.md)

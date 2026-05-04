# Event Sourcing 专题

这个专题关注把状态变化记录为事件流，而不是只保留最终结果。

## 适用场景

- 需要完整审计和状态回放的业务
- 聚合根变更规则复杂，需要强业务历史语义
- 需要从领域事件重建多种投影模型

## 常见主题

- 事件存储
- 状态重放
- 快照
- 事件版本演进
- 与 CQRS 组合

## 设计要点

- 先确认你需要的是“领域事件”，不是简单的 CDC 日志
- 事件命名、顺序和幂等语义必须长期稳定
- 快照是性能优化，不应破坏回放语义
- 事件 schema 演进成本通常会被低估

## 关联阅读

- [CQRS 专题](./cqrs.md)
- [事件驱动架构专题](./event-driven-architecture.md)
- [Schema 演进专题](./schema-evolution.md)
- [Schema Registry 专题](./schema-registry.md)

返回 [索引](../README.md)

# 事件驱动架构专题

这个专题关注系统通过事件而不是同步调用协作时，如何管理边界、时序和一致性。

## 常见主题

- 领域事件与集成事件区分
- 生产者和消费者解耦
- 至少一次投递与最终一致性
- 事件 schema 和版本演进
- 消费者幂等与回放

## 常见场景

- 订单状态驱动多个下游系统
- 埋点、通知、清结算等异步流水
- 数据同步和变更广播

## 关联阅读

- [消息系统专题](./message-systems.md)
- [Outbox / Inbox 模式专题](./outbox-inbox-patterns.md)
- [数据契约专题](./data-contracts.md)
- [Schema 演进专题](./schema-evolution.md)
- [CQRS 专题](./cqrs.md)
- [Event Sourcing 专题](./event-sourcing.md)
- [Saga 模式专题](./saga-patterns.md)

返回 [索引](../README.md)

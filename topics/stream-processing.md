# 流处理专题

这个专题关注数据不是按天离线落表，而是持续地产生、传输、聚合和消费。

## 适用场景

- 实时订单、日志、监控、风控事件处理
- Kafka 上的持续聚合和窗口统计
- 事件流接入数据湖、数仓和实时服务

## 常见主题

- 生产者、消费者和 consumer group
- offset 提交和重平衡
- 时间窗口与 watermark
- 批消费、背压和积压治理
- 事件 schema、兼容和回放

## 设计要点

- 明确至少一次、至多一次、恰好一次的代价差异
- 消费端必须设计幂等键和重复处理策略
- 把 DLQ、重试、补偿和告警当成主流程的一部分
- 区分业务时间、事件时间和处理时间

## 关联阅读

- [消息系统专题](./message-systems.md)
- [Consumer Group 运维专题](./consumer-group-operations.md)
- [Schema Registry 专题](./schema-registry.md)
- [变更数据捕获专题](./change-data-capture.md)
- [aiokafka](../third_party/aiokafka.md)
- [confluent-kafka](../third_party/confluent_kafka.md)

返回 [索引](../README.md)

# Consumer Group 运维专题

这个专题关注 Kafka 等消息系统中的 consumer group 如何扩缩容、再均衡、追 lag 和做故障恢复。

## 适用场景

- 消费积压波动大
- 扩 worker 后吞吐没有提升
- 消费者重启或发布时频繁再均衡

## 常见主题

- partition 与并行度
- lag 监控
- 再均衡
- offset 提交
- 消费幂等

## 设计要点

- consumer 数量不能只看机器数，还要看 partition 数
- 再均衡策略会直接影响可用性和恢复时间
- lag 只是结果指标，还要追单条处理时长和失败率
- 批量消费和手动提交要和幂等边界一起设计

## 关联阅读

- [消息系统专题](./message-systems.md)
- [流处理专题](./stream-processing.md)
- [Kafka 重试与 DLQ 专题](./kafka-retry-dlq.md)
- [背压与流控专题](./backpressure-and-flow-control.md)

返回 [索引](../README.md)

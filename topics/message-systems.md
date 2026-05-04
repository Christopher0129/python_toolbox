# 消息系统专题

这个专题关注 Python 系统中的异步消息流：任务队列、事件流和消费者模型。

## 常见工具

| 工具 | 作用 |
| --- | --- |
| `redis` | 轻量缓存与队列 |
| `celery` | 任务消息流 |
| `Kafka` | 高吞吐事件流 |
| `RabbitMQ` | AMQP 队列路由 |
| `NATS` | 低延迟发布订阅 |

## 关联阅读

- [redis-py](../third_party/redis.md)
- [celery](../third_party/celery.md)
- [kafka-python](../third_party/kafka_python.md)
- [缓存与队列专题](./cache-queues.md)
- [事件驱动架构专题](./event-driven-architecture.md)
- [Outbox / Inbox 模式专题](./outbox-inbox-patterns.md)
- [消费者驱动契约专题](./consumer-driven-contracts.md)
- [RabbitMQ 专题](./rabbitmq-messaging.md)
- [NATS 专题](./nats-messaging.md)

返回 [索引](../README.md)

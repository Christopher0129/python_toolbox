# aiokafka

`aiokafka` 适合在 `asyncio` 服务里做 Kafka 生产和消费，避免把同步客户端硬塞进异步应用。

## 安装

```bash
pip install aiokafka
```

## 基本示例

```python
from aiokafka import AIOKafkaConsumer

consumer = AIOKafkaConsumer(
    "orders",
    bootstrap_servers="localhost:9092",
    group_id="billing",
)
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `AIOKafkaProducer` | 异步发送消息 |
| `AIOKafkaConsumer` | 异步消费消息 |
| `consumer.getmany(...)` | 批量拉取消息 |

## 适用场景

- FastAPI / asyncio 服务内嵌 Kafka 客户端
- 低延迟异步消费与批处理
- 事件驱动接口和流式 ETL

## 关联阅读

- [流处理专题](../topics/stream-processing.md)
- [消息系统专题](../topics/message-systems.md)
- [事件驱动架构专题](../topics/event-driven-architecture.md)

返回 [索引](../README.md)

# confluent-kafka

`confluent-kafka` 基于 `librdkafka`，适合追求高吞吐、低延迟和更完整 Kafka 特性的生产环境。

## 安装

```bash
pip install confluent-kafka
```

## 基本示例

```python
from confluent_kafka import Consumer

consumer = Consumer(
    {
        "bootstrap.servers": "localhost:9092",
        "group.id": "orders-reader",
        "auto.offset.reset": "earliest",
    }
)
consumer.subscribe(["orders"])
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `Producer(...)` | 高性能生产消息 |
| `Consumer(...)` | 拉取和提交消息 |
| `SerializingProducer` | 带序列化器的生产者 |

## 适用场景

- 高吞吐 Kafka 消息读写
- 与 Schema Registry、Avro、Protobuf 生态配合
- 需要更稳定交付和更低客户端开销的服务

## 关联阅读

- [Schema Registry 专题](../topics/schema-registry.md)
- [流处理专题](../topics/stream-processing.md)
- [Kafka 重试与 DLQ 专题](../topics/kafka-retry-dlq.md)

返回 [索引](../README.md)

# pika

`pika` 是 Python 访问 RabbitMQ 的常用客户端，适合队列消费、任务分发和事件推送。

## 安装

```bash
pip install pika
```

## 基本示例

```python
import pika

connection = pika.BlockingConnection(pika.ConnectionParameters("localhost"))
channel = connection.channel()
channel.queue_declare(queue="tasks")
```

## 关联阅读

- [RabbitMQ 专题](../topics/rabbitmq-messaging.md)
- [消息系统专题](../topics/message-systems.md)
- [幂等与重试专题](../topics/idempotency-retries.md)

返回 [索引](../README.md)

# Dramatiq

`Dramatiq` 适合构建比 Celery 更轻量的后台任务系统，尤其适合 Redis / RabbitMQ 驱动的异步作业。

## 安装

```bash
pip install dramatiq redis
```

## 基本示例

```python
import dramatiq

@dramatiq.actor
def send_mail(user_id: int) -> None:
    print(user_id)
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `@dramatiq.actor` | 声明后台任务 |
| `send_mail.send(...)` | 投递任务 |
| `RabbitmqBroker(...)` / `RedisBroker(...)` | 配置 broker |

## 关联阅读

- [任务队列架构专题](../topics/task-queue-architectures.md)
- [缓存与队列专题](../topics/cache-queues.md)
- [消息系统专题](../topics/message-systems.md)

返回 [索引](../README.md)

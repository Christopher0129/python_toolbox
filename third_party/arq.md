# arq

`arq` 适合在 `asyncio` 应用里基于 Redis 做异步任务队列，比同步 worker 更容易融入异步 Web 服务。

## 安装

```bash
pip install arq redis
```

## 基本示例

```python
from arq import create_pool
from arq.connections import RedisSettings

redis = await create_pool(RedisSettings())
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `create_pool(...)` | 建立 Redis 任务连接 |
| `enqueue_job(...)` | 投递异步任务 |
| `WorkerSettings` | 声明 worker 配置 |

## 关联阅读

- [任务队列架构专题](../topics/task-queue-architectures.md)
- [异步编程专题](../topics/async-programming.md)
- [Redis 高级专题](../topics/redis-advanced.md)

返回 [索引](../README.md)

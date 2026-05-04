# tenacity

`tenacity` 适合给容易受网络抖动、临时锁冲突、外部依赖波动影响的操作增加重试、退避和停止条件。

## 安装

```bash
pip install tenacity
```

## 基本示例

```python
from tenacity import retry, stop_after_attempt, wait_exponential


@retry(
    stop=stop_after_attempt(3),
    wait=wait_exponential(multiplier=1, min=1, max=8),
)
def fetch_remote_data():
    return "ok"
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `@retry(...)` | 给函数声明重试策略 |
| `stop_after_attempt()` | 限制最大尝试次数 |
| `wait_exponential()` | 指数退避，减少雪崩 |

## 使用建议

- 只对暂时性错误做重试，不要把参数错误或权限错误也纳入重试
- 写操作先解决幂等问题，再谈自动重试
- 把超时、重试次数和总耗时预算一起设计

## 关联阅读

- [幂等与重试专题](../topics/idempotency-retries.md)
- [Kafka 重试与 DLQ 专题](../topics/kafka-retry-dlq.md)
- [API 开发专题](../topics/api-development.md)

返回 [索引](../README.md)

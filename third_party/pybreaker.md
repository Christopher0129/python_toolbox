# pybreaker

`pybreaker` 适合在访问不稳定外部依赖时实现断路器，避免失败请求持续压垮下游和本服务线程池。

## 安装

```bash
pip install pybreaker
```

## 基本示例

```python
import pybreaker

breaker = pybreaker.CircuitBreaker(fail_max=5, reset_timeout=60)

@breaker
def call_remote():
    return "ok"
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `CircuitBreaker(...)` | 创建断路器 |
| `fail_max` | 连续失败阈值 |
| `reset_timeout` | 半开前等待时间 |

## 使用建议

- 断路器适合保护慢依赖，不替代超时和重试
- 断路状态要纳入指标和告警
- 失败分类要谨慎，参数错误不应计入断路

## 关联阅读

- [断路器与隔离专题](../topics/circuit-breakers-bulkheads.md)
- [幂等与重试专题](../topics/idempotency-retries.md)
- [可观测性专题](../topics/observability.md)

返回 [索引](../README.md)

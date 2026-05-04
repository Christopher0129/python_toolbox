# Pact

`Pact` 适合做消费者驱动契约测试，确保提供方升级后不会破坏关键消费者依赖的字段和行为。

## 安装

```bash
pip install pact-python
```

## 基本示例

```python
from pact import Consumer, Provider

pact = Consumer("order-web").has_pact_with(Provider("order-api"))
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `Consumer(...).has_pact_with(...)` | 声明消费者与提供方 |
| `given(...).upon_receiving(...)` | 描述交互前提和请求 |
| `will_respond_with(...)` | 声明消费者期望的响应 |

## 适用场景

- 微服务接口兼容回归
- 前后端约定字段验证
- 第三方服务替身契约校验

## 关联阅读

- [消费者驱动契约专题](../topics/consumer-driven-contracts.md)
- [契约测试专题](../topics/contract-testing.md)
- [API 版本治理专题](../topics/api-versioning.md)

返回 [索引](../README.md)

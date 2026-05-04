# Unleash

`Unleash` 适合做特性开关和渐进发布，让功能上线与代码部署解耦。

## 安装

```bash
pip install UnleashClient
```

## 基本示例

```python
from UnleashClient import UnleashClient

client = UnleashClient(url="http://127.0.0.1:4242/api", app_name="demo")
client.initialize_client()
enabled = client.is_enabled("new_checkout_flow")
print(enabled)
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `is_enabled(...)` | 判断某个特性开关是否开启 |
| 渐进发布 | 按百分比、环境、用户群发布 |
| 变体 | 给实验和灰度提供多种分支 |

## 关联阅读

- [特性开关专题](../topics/feature-flags.md)
- [发布策略专题](../topics/deployment-strategies.md)
- [实验跟踪专题](../topics/experiment-tracking.md)

返回 [索引](../README.md)

# sentry-sdk

`sentry-sdk` 适合错误监控和性能采样，能把异常、请求链路和部分性能信息上报到 Sentry。

## 安装

```bash
pip install sentry-sdk
```

## 基本示例

```python
import sentry_sdk

sentry_sdk.init(
    dsn="https://examplePublicKey@o0.ingest.sentry.io/0",
    sample_rate=1.0,
    traces_sample_rate=1.0,
)
```

## 适用场景

- 线上错误收集
- 性能采样
- 发布后问题回溯

## 注意事项

- 采样率不要盲目开满
- 日志与错误平台要职责分清
- 敏感信息上传前要评估

## 关联阅读

- [错误监控专题](../topics/error-monitoring.md)
- [可观测性专题](../topics/observability.md)
- [安全基础专题](../topics/security-basics.md)

返回 [索引](../README.md)

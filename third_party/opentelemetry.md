# OpenTelemetry

`OpenTelemetry` 适合为 Python 服务补充 traces、metrics 和 logs，是当前较通用的可观测性基础标准。

## 安装

```bash
pip install opentelemetry-api opentelemetry-sdk
```

## Trace 基本示例

```python
from opentelemetry import trace
from opentelemetry.sdk.trace import TracerProvider
from opentelemetry.sdk.trace.export import BatchSpanProcessor, ConsoleSpanExporter

provider = TracerProvider()
provider.add_span_processor(BatchSpanProcessor(ConsoleSpanExporter()))
trace.set_tracer_provider(provider)
tracer = trace.get_tracer("demo")
```

## Metric 基本示例

```python
from opentelemetry import metrics
from opentelemetry.sdk.metrics import MeterProvider
from opentelemetry.sdk.metrics.export import ConsoleMetricExporter, PeriodicExportingMetricReader

reader = PeriodicExportingMetricReader(ConsoleMetricExporter())
metrics.set_meter_provider(MeterProvider(metric_readers=[reader]))
meter = metrics.get_meter("demo")
```

## 适用场景

- 服务链路追踪
- 请求耗时观测
- 自定义业务指标

## 关联阅读

- [可观测性专题](../topics/observability.md)
- [遥测与链路追踪专题](../topics/telemetry-tracing.md)
- [prometheus-client](./prometheus_client.md)

返回 [索引](../README.md)

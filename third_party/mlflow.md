# MLflow

`MLflow` 适合实验跟踪、参数记录、指标记录和模型产物管理。

## 安装

```bash
pip install mlflow
```

## 基本示例

```python
import mlflow

with mlflow.start_run():
    mlflow.log_param("learning_rate", 0.01)
    mlflow.log_metric("accuracy", 0.95)
```

模型治理里也常见：

```python
import mlflow

mlflow.register_model("runs:/<run_id>/model", "fraud_model")
```

## 适用场景

- 模型实验记录
- 参数和指标对比
- 训练结果可追溯
- 模型版本注册和提升

## 注意事项

- fluent tracking API 不是线程安全的
- 需要规划 tracking URI 和 artifact 存储

## 关联阅读

- [实验跟踪专题](../topics/experiment-tracking.md)
- [分析工程专题](../topics/analytics-engineering.md)
- [模型注册专题](../topics/model-registry.md)

返回 [索引](../README.md)

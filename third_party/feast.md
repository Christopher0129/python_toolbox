# Feast

`Feast` 是常见的特征库工具，适合管理训练和在线推理共用的特征定义、历史回放和低延迟特征读取。

## 安装

```bash
pip install feast
```

## 基本示例

```python
from feast import FeatureStore
import pandas as pd

store = FeatureStore(repo_path=".")
entity_df = pd.DataFrame(
    {
        "driver_id": [1001],
        "event_timestamp": [pd.Timestamp.utcnow()],
    }
)
training_df = store.get_historical_features(
    entity_df=entity_df,
    features=store.get_feature_service("model_v1"),
).to_df()
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `FeatureStore(...)` | 连接特征仓库 |
| `get_historical_features(...)` | 生成训练 / 批量评分特征 |
| `get_online_features(...)` | 在线推理取最新特征 |

## 使用建议

- 训练集要保留时间戳，避免点位泄漏
- 把一组模型所需特征收敛成 feature service
- 关注离线与在线特征的一致性

## 关联阅读

- [特征库专题](../topics/feature-stores.md)
- [实验跟踪专题](../topics/experiment-tracking.md)
- [数据管道专题](../topics/data-pipelines.md)

返回 [索引](../README.md)

# XGBoost

`XGBoost` 适合表格数据上的梯度提升模型训练，常见于风控、推荐和排序任务。

## 安装

```bash
pip install xgboost
```

## 基本示例

```python
import xgboost as xgb

model = xgb.XGBClassifier(n_estimators=200, max_depth=6)
```

## 关联阅读

- [传统机器学习专题](../topics/classical-ml.md)
- [特征工程专题](../topics/feature-engineering.md)
- [模型服务专题](../topics/model-serving.md)

返回 [索引](../README.md)

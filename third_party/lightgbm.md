# LightGBM

`LightGBM` 适合高效训练 GBDT 模型，常见于大规模表格数据与特征工程场景。

## 安装

```bash
pip install lightgbm
```

## 基本示例

```python
import lightgbm as lgb

model = lgb.LGBMClassifier(num_leaves=64)
```

## 关联阅读

- [传统机器学习专题](../topics/classical-ml.md)
- [特征工程专题](../topics/feature-engineering.md)
- [实验跟踪专题](../topics/experiment-tracking.md)

返回 [索引](../README.md)

# pandera

`pandera` 适合给 `pandas` DataFrame 声明列类型、可空性和校验规则，用在数据契约和表结构校验场景很合适。

## 安装

```bash
pip install pandera
```

## 基本示例

```python
import pandera.pandas as pa

schema = pa.DataFrameSchema(
    {
        "user_id": pa.Column(int, nullable=False),
        "amount": pa.Column(float, checks=pa.Check(lambda s: s >= 0)),
    },
    strict=True,
)
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `DataFrameSchema(...)` | 定义整张表的结构约束 |
| `Column(...)` | 定义列类型和校验 |
| `schema.validate(df)` | 校验并返回通过验证的数据 |

## 适用场景

- DataFrame 输入输出校验
- ETL 中间层结构约束
- 数据契约落地

## 关联阅读

- [数据契约专题](../topics/data-contracts.md)
- [Schema 演进专题](../topics/schema-evolution.md)
- [数据质量测试专题](../topics/data-quality-testing.md)

返回 [索引](../README.md)

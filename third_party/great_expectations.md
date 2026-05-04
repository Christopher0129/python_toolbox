# Great Expectations

`Great Expectations` 适合把数据质量校验声明成可复用规则。

## 安装

```bash
pip install great-expectations
```

## 基本示例

```python
validator.expect_column_values_to_not_be_null("pickup_datetime")
validator.expect_column_values_to_be_between("passenger_count", min_value=1, max_value=6)
```

## 适用场景

- 数据仓库质量检查
- ETL 输出校验
- 数据团队共享质量规则
- 数据契约中的质量约束落地

## 关联阅读

- [数据质量测试专题](../topics/data-quality-testing.md)
- [数据契约专题](../topics/data-contracts.md)
- [Schema 演进专题](../topics/schema-evolution.md)

返回 [索引](../README.md)

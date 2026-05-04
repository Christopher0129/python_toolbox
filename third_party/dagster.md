# Dagster

`Dagster` 适合把数据资产、依赖关系、调度和物化过程显式建模，常见于现代数据平台。

## 安装

```bash
pip install dagster
```

## 基本示例

```python
from dagster import asset


@asset
def orders():
    return [{"id": 1}]
```

## 关联阅读

- [工作流编排专题](../topics/workflow-orchestration.md)
- [数据仓库与 ETL 专题](../topics/data-warehouse-etl.md)
- [分析工程专题](../topics/analytics-engineering.md)

返回 [索引](../README.md)

# polars

`polars` 适合高性能表格处理，尤其适合大数据量、本地分析和 lazy query 场景。

## 安装

```bash
pip install polars
```

## Eager 示例

```python
import polars as pl

df = pl.read_csv("data.csv")
result = df.group_by("city").agg(pl.col("sales").mean())
print(result)
```

## Lazy 示例

```python
import polars as pl

q = (
    pl.scan_csv("data.csv")
    .filter(pl.col("sales") > 0)
    .group_by("city")
    .agg(pl.col("sales").sum())
)

df = q.collect()
```

## 适用场景

- 本地列式分析
- 比 `pandas` 更偏性能的批处理
- 大文件和 lazy pipeline

## 关联阅读

- [pandas](./pandas.md)
- [DuckDB](./duckdb.md)
- [列式数据处理专题](../topics/columnar-data-processing.md)

返回 [索引](../README.md)

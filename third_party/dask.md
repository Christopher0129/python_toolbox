# Dask

`Dask` 适合在单机或集群上扩展 `pandas` / `numpy` 风格计算，处理内存外和并行数据任务。

## 安装

```bash
pip install dask[complete]
```

## 基本示例

```python
import dask.dataframe as dd

df = dd.read_csv("data/*.csv")
result = df.groupby("city").amount.sum().compute()
print(result)
```

## 关联阅读

- [分布式计算专题](../topics/distributed-computing.md)
- [列式数据处理专题](../topics/columnar-data-processing.md)
- [数据管道专题](../topics/data-pipelines.md)

返回 [索引](../README.md)

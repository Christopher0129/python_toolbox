# PySpark

`PySpark` 适合在 Spark 集群上做大规模批处理、SQL 分析和分布式 ETL。

## 安装

```bash
pip install pyspark
```

## 基本示例

```python
from pyspark.sql import SparkSession

spark = SparkSession.builder.appName("demo").getOrCreate()
df = spark.read.csv("data.csv", header=True)
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `SparkSession.builder...getOrCreate()` | 创建 Spark 入口 |
| `spark.read.csv(...)` | 读取分布式数据 |
| `df.groupBy(...).count()` | 执行聚合计算 |

## 关联阅读

- [Spark 数据处理专题](../topics/spark-data-processing.md)
- [分布式计算专题](../topics/distributed-computing.md)
- [数据仓库与 ETL 专题](../topics/data-warehouse-etl.md)

返回 [索引](../README.md)

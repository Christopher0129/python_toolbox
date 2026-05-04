# Spark 数据处理专题

这个专题关注用 Spark 在大规模数据上做 ETL、SQL 和分布式批处理，而不是只看单机 DataFrame。

## 适用场景

- 明显超出单机内存的数据清洗和聚合
- 对对象存储中的 Parquet / Delta 表做批处理
- 需要调度、回填和增量更新的数据平台任务

## 常见主题

- SparkSession 和 DataFrame API
- 分区与 shuffle 成本
- SQL 与 DataFrame 混用
- 任务提交和资源配置
- 与对象存储 / 数据湖结合

## 设计要点

- 先确认问题是否真的需要 Spark，避免把本可单机完成的任务复杂化
- 优先关注分区数、数据倾斜和不必要的宽依赖
- 把表格式、文件布局和任务调度一起看，而不是只调 Spark 参数
- 本地开发、测试数据和集群环境的差异要提前缩小

## 关联阅读

- [PySpark](../third_party/pyspark.md)
- [分布式计算专题](./distributed-computing.md)
- [数据湖存储专题](./data-lake-storage.md)
- [Delta Lake 专题](./delta-lake.md)
- [流处理专题](./stream-processing.md)

返回 [索引](../README.md)

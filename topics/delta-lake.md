# Delta Lake 专题

这个专题关注 Delta 表在数据湖上的事务、版本和增量更新能力。

## 适用场景

- 对象存储上的可回溯分析表
- 批流一体的数据落地与回放
- 需要 upsert、版本回看和 schema 演进的数据湖

## 常见主题

- ACID 事务
- schema enforcement / evolution
- merge / upsert
- time travel
- 与 Spark / lakehouse 集成

## 设计要点

- 分区策略要服务查询模式，而不是机械按日期切分
- 小文件治理和 compaction 会直接影响查询与写入成本
- schema evolution 不是随意放开字段变更，仍需契约约束
- 要区分原始落地区、标准化区和服务消费区

## 关联阅读

- [deltalake](../third_party/deltalake.md)
- [Spark 数据处理专题](./spark-data-processing.md)
- [Lakehouse 表格式专题](./table-formats-lakehouse.md)
- [数据湖存储专题](./data-lake-storage.md)

返回 [索引](../README.md)

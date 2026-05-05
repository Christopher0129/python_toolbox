# PostgreSQL 逻辑解码专题

这个专题关注 PostgreSQL 如何通过逻辑解码把 WAL 变更转成可消费的结构化数据流。

## 适用场景

- 需要 CDC 驱动搜索、缓存、数仓或事件平台
- 需要细粒度捕获表级变更
- 需要评估复制槽和 WAL 堆积风险

## 常见主题

- publication / subscription
- 逻辑复制槽
- 变更事件格式
- DDL 兼容与 schema 演进
- 下游幂等消费

## 设计要点

- 逻辑解码链路最怕的是消费停滞导致 WAL 无法回收。
- CDC 事件并不天然等同于业务事件，通常还需要语义转换层。
- 表结构变化、主键变化和删除语义要在链路设计早期明确。
- 回放、补数和重建索引都要有可重复执行的方案。

## 关联阅读

- [变更数据捕获专题](./change-data-capture.md)
- [PostgreSQL 复制与故障切换专题](./postgresql-replication-failover.md)
- [数据契约专题](./data-contracts.md)
- [Schema 演进专题](./schema-evolution.md)
- [事件驱动架构专题](./event-driven-architecture.md)

返回 [索引](../README.md)

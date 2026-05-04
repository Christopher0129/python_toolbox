# 变更数据捕获专题

这个专题关注如何把数据库中的插入、更新、删除变化稳定地转成事件流，用于同步下游系统。

## 适用场景

- 业务库到数仓 / Lakehouse 的增量同步
- 搜索索引、缓存、画像系统的异步刷新
- 事件驱动架构里的事实来源传播

## 常见主题

- binlog / WAL 捕获
- 全量初始化与增量衔接
- 主键、删除标记和乱序处理
- 下游幂等写入
- schema 变化传播

## 设计要点

- 明确数据库变更事件和业务领域事件不是同一层抽象
- CDC 链路要处理回放、断点续传和重新订阅
- 删除事件、软删除和快照补齐策略要提前定好
- 与 Schema Registry、数据契约联动，避免无通知破坏兼容

## 关联阅读

- [Schema Registry 专题](./schema-registry.md)
- [事件驱动架构专题](./event-driven-architecture.md)
- [数据仓库与 ETL 专题](./data-warehouse-etl.md)
- [流处理专题](./stream-processing.md)

返回 [索引](../README.md)

# 查询计划分析专题

这个专题关注慢 SQL 不该只靠猜，而要通过执行计划理解扫描、过滤、连接和排序成本。

## 适用场景

- 同一 SQL 在不同环境耗时差异大
- 明明有索引却仍然慢
- 复杂查询上线后 CPU 飙升

## 常见主题

- `EXPLAIN`
- 扫描行数与过滤比例
- join 顺序
- sort / aggregate 成本
- 统计信息与参数漂移

## 设计要点

- 先看扫描量，再看返回量，差距越大越值得优化
- 慢 SQL 优化应同时看 SQL 写法、索引设计和数据分布
- 测试环境和生产环境数据量差异会导致误判
- 计划变化要和版本、统计信息、参数一起记录

## 关联阅读

- [SQL 优化专题](./sql-optimization.md)
- [索引设计专题](./index-design.md)
- [PostgreSQL 开发专题](./postgresql-development.md)
- [MySQL 开发专题](./mysql-development.md)

返回 [索引](../README.md)

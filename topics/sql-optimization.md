# SQL 优化专题

这个专题关注 Python 项目里常见的数据库性能问题，不深入数据库内核，但强调应用层该怎么看。

## 常见风险

- N+1 查询
- 没有限制返回列和返回行数
- 缺索引导致全表扫描
- 事务范围过大

## 应用层建议

- 先看查询次数
- 再看单次查询耗时
- 只查需要的列
- 列表接口注意分页

## 关联阅读

- [SQLAlchemy 2.x 基础](../database/sqlalchemy.md)
- [数据库开发专题](./database-development.md)
- [索引设计专题](./index-design.md)
- [查询计划分析专题](./query-plan-analysis.md)
- [事务与隔离级别专题](./transaction-isolation.md)
- [性能与调试专题](./performance-debugging.md)

返回 [索引](../README.md)

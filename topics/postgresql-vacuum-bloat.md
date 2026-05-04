# PostgreSQL Vacuum 与膨胀专题

这个专题关注更新和删除频繁后，PostgreSQL 如何通过 vacuum、analyze 和表维护保持性能稳定。

## 适用场景

- 表越来越大但有效数据并没有增长太多
- 更新删除频繁后查询变慢
- Autovacuum 跟不上业务写入

## 常见主题

- autovacuum
- analyze
- 死元组
- 表膨胀与索引膨胀
- 维护窗口

## 设计要点

- vacuum 不是可有可无的“后台小事”，而是持续性能基础设施
- 高写入表应单独观察 autovacuum 行为
- 统计信息过旧会直接影响执行计划质量
- 维护操作要结合流量窗口和回滚策略

## 关联阅读

- [PostgreSQL 开发专题](./postgresql-development.md)
- [查询计划分析专题](./query-plan-analysis.md)
- [容量规划专题](./capacity-planning.md)
- [备份与归档专题](./backup-archiving.md)

返回 [索引](../README.md)

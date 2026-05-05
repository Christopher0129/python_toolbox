# PostgreSQL 统计与观测专题

这个专题关注 PostgreSQL 运行中应长期追踪哪些统计视图、关键指标和排障入口。

## 适用场景

- 数据库慢查询、锁等待或延迟波动频繁出现
- 需要把数据库纳入统一观测体系
- 团队想从“靠感觉调库”转向“基于指标调库”

## 常见主题

- `pg_stat_activity`
- `pg_stat_statements`
- `pg_stat_database`
- 锁等待与长事务
- autovacuum 与 checkpoint 指标

## 设计要点

- 数据库观测必须同时覆盖查询、事务、连接、复制和存储几个层面。
- 只看平均响应时间很容易错过尾延迟和等待链。
- 指标要和容量阈值、告警规则和 runbook 绑在一起。
- 慢 SQL 排查应结合执行计划、等待事件和业务变更时间线。

## 关联阅读

- [可观测性专题](./observability.md)
- [查询计划分析专题](./query-plan-analysis.md)
- [PostgreSQL 锁与并发专题](./postgresql-locking.md)
- [PostgreSQL VACUUM 与膨胀专题](./postgresql-vacuum-bloat.md)
- [PostgreSQL WAL 与 Checkpoint 专题](./postgresql-wal-checkpoint.md)

返回 [索引](../README.md)

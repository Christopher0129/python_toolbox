# PostgreSQL 租户隔离专题

这个专题关注多租户系统在 PostgreSQL 中如何设计数据隔离、资源隔离和权限边界。

## 适用场景

- SaaS 系统需要在同一集群承载多个租户
- 不同租户的数据体量和访问模式差异明显
- 团队需要在隔离强度和运维复杂度之间取舍

## 常见主题

- 共享库共享表
- 独立 schema
- 独立数据库
- 行级安全
- 噪声租户治理

## 设计要点

- 租户隔离方案要同时考虑权限边界、索引策略、备份恢复和迁移成本。
- 共享表模型要尽早把租户键纳入主键、唯一约束和核心索引设计。
- 强隔离需求常常不只来自安全，还来自容量和故障域控制。
- 行级安全可以增强约束，但不能替代应用层显式租户上下文校验。

## 关联阅读

- [分片与分区专题](./sharding-partitioning.md)
- [事务与隔离级别专题](./transaction-isolation.md)
- [数据脱敏专题](./data-masking.md)
- [PostgreSQL 分区维护专题](./postgresql-partition-maintenance.md)
- [认证与授权专题](./auth-authorization.md)

返回 [索引](../README.md)

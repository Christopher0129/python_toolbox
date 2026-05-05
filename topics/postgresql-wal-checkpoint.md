# PostgreSQL WAL 与 Checkpoint 专题

这个专题关注 PostgreSQL 写前日志、checkpoint 和恢复窗口对吞吐、延迟与磁盘压力的影响。

## 适用场景

- 写入高峰期出现抖动或 fsync 压力
- 主从复制链路依赖 WAL 保留
- 需要理解恢复时间目标与日志生成速度

## 常见主题

- WAL 生成速率
- checkpoint 周期
- 脏页刷盘
- WAL 保留与归档
- 崩溃恢复窗口

## 设计要点

- checkpoint 过于频繁会放大刷盘抖动，过于稀疏又会拉长恢复时间。
- WAL 压力要结合写入模式、批量事务和索引维护一起看。
- 复制、归档和 CDC 都会依赖 WAL 生命周期，不能只从单机视角调参。
- 监控不能只看 TPS，还要看 checkpoint、刷盘和归档延迟。

## 关联阅读

- [PostgreSQL 开发专题](./postgresql-development.md)
- [PostgreSQL 复制与故障切换专题](./postgresql-replication-failover.md)
- [PostgreSQL Vacuum 与膨胀专题](./postgresql-vacuum-bloat.md)
- [变更数据捕获专题](./change-data-capture.md)
- [备份与归档专题](./backup-archiving.md)

返回 [索引](../README.md)

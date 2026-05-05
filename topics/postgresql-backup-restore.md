# PostgreSQL 备份与恢复专题

这个专题关注 PostgreSQL 在物理备份、逻辑备份、时间点恢复和恢复演练上的实践。

## 适用场景

- 业务库需要明确 RPO / RTO
- 需要应对误删、误更新或集群故障
- 需要把备份从“有文件”推进到“可恢复”

## 常见主题

- 物理备份与逻辑备份
- 基础备份与 WAL 归档
- PITR
- 恢复演练
- 备份校验

## 设计要点

- 备份是否成功不取决于是否生成文件，而取决于能否按目标恢复。
- 逻辑备份更适合对象级恢复，物理备份更适合集群级恢复。
- 恢复演练必须覆盖权限、连接串、应用切换和数据校验，不只是数据库启动。
- 备份窗口和恢复窗口要和业务写入模式、WAL 量级一起评估。

## 关联阅读

- [备份与归档专题](./backup-archiving.md)
- [PostgreSQL 复制与故障切换专题](./postgresql-replication-failover.md)
- [PostgreSQL WAL 与 Checkpoint 专题](./postgresql-wal-checkpoint.md)
- [PostgreSQL 分区维护专题](./postgresql-partition-maintenance.md)
- [Runbook 与运维手册专题](./runbooks-and-ops.md)

返回 [索引](../README.md)

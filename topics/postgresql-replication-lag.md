# PostgreSQL 复制延迟专题

这个专题关注 PostgreSQL 主从复制中备库回放落后、读写分离不一致和只读副本观测问题。

## 适用场景

- 读写分离后用户偶发读不到刚写入的数据
- 备库查询高峰时 lag 明显上升
- 故障切换前难以判断副本追平程度

## 常见主题

- replay lag
- WAL 发送与回放
- 只读查询压力
- 长查询阻塞回放
- 应用侧读己写保障

## 设计要点

- 复制延迟不是单一数值，要区分发送、接收、写入和回放阶段。
- 只读副本承担报表或大查询时最容易拖慢回放。
- 读写分离必须明确哪些请求可以接受陈旧读。
- 切换和演练前要建立 lag 阈值和保护规则。

## 关联阅读

- [PostgreSQL 复制与故障切换专题](./postgresql-replication-failover.md)
- [PostgreSQL WAL 与 Checkpoint 专题](./postgresql-wal-checkpoint.md)
- [PostgreSQL 备份与恢复专题](./postgresql-backup-restore.md)
- [可观测性专题](./observability.md)
- [事故响应专题](./incident-response.md)

返回 [索引](../README.md)

# PostgreSQL 读写分离专题

这个专题关注主库写入、只读副本查询和应用路由之间的一致性、延迟与故障切换边界。

## 适用场景

- 在线业务需要把读流量从主库分流到副本
- 报表、检索和后台任务读取压力大
- 团队开始引入只读副本，但经常遇到“刚写完读不到”

## 常见主题

- 主从路由
- 复制延迟感知
- 事务内强制主库
- 读一致性等级
- 故障切换后的连接重建

## 设计要点

- 读写分离不是简单按 SQL 类型分流，还要考虑事务上下文和一致性要求。
- 刚写后立即读、幂等校验和状态轮询场景通常更适合走主库。
- 副本延迟监控应直接暴露给应用路由层或网关层。
- 连接池、服务发现和故障切换策略要一起设计，避免路由与实例状态脱节。

## 关联阅读

- [PostgreSQL 开发专题](./postgresql-development.md)
- [PostgreSQL 复制延迟专题](./postgresql-replication-lag.md)
- [PostgreSQL 复制与故障切换专题](./postgresql-replication-failover.md)
- [连接池专题](./connection-pooling.md)
- [运行时配置专题](./runtime-configuration.md)

返回 [索引](../README.md)

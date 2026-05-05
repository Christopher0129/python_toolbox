# PostgreSQL 连接耗尽专题

这个专题关注 PostgreSQL 在高并发服务、批处理和连接池配置不当时出现的连接数耗尽问题。

## 适用场景

- 峰值流量时频繁报 `too many connections`
- API 服务、worker 和脚本任务共同访问同一实例
- 应用连接池已经存在，但仍然出现排队和超时

## 常见主题

- `max_connections`
- 池大小与进程数乘积
- 空闲连接堆积
- 连接泄漏
- 连接代理与池化分层

## 设计要点

- 连接问题通常不是单个池参数问题，而是全系统并发模型问题。
- 池大小要按进程数、worker 数和只读副本分流一起估算。
- 短任务和批处理脚本最容易绕过统一池化策略。
- 连接耗尽排查要同时看等待时间、空闲连接、长事务和角色分布。

## 关联阅读

- [连接池专题](./connection-pooling.md)
- [PostgreSQL 开发专题](./postgresql-development.md)
- [PostgreSQL 复制与故障切换专题](./postgresql-replication-failover.md)
- [容量规划专题](./capacity-planning.md)
- [压测专题](./load-testing.md)

返回 [索引](../README.md)

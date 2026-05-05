# PostgreSQL 语句超时专题

这个专题关注慢查询、锁等待和批处理任务如何通过语句级超时约束来控制尾延迟与资源占用。

## 适用场景

- 线上偶发慢 SQL 拖垮连接池
- 锁等待经常把请求卡到应用超时
- 同一数据库同时承载在线请求和离线批处理

## 常见主题

- `statement_timeout`
- `lock_timeout`
- `idle_in_transaction_session_timeout`
- 取消查询
- 角色级和服务级超时策略

## 设计要点

- 数据库超时应早于上游网关和应用超时，避免无效占用连接。
- 在线请求与离线任务通常需要不同的超时预算和连接角色。
- 超时不是 SQL 优化替代品，超时后仍要定位慢点和锁争用根因。
- 应用侧要区分超时失败、锁冲突和网络失败，避免误重试。

## 关联阅读

- [SQL 优化专题](./sql-optimization.md)
- [查询计划分析专题](./query-plan-analysis.md)
- [PostgreSQL 锁与并发专题](./postgresql-locking.md)
- [PostgreSQL 统计与观测专题](./postgresql-stats-observability.md)
- [连接池专题](./connection-pooling.md)

返回 [索引](../README.md)

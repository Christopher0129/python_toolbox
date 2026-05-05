# PostgreSQL 幂等写入专题

这个专题关注接口重试、消息重复投递和补偿任务重放时，如何让 PostgreSQL 写入保持可重复执行而不产生重复副作用。

## 适用场景

- 支付、下单、发券等操作需要抗重试
- 消费者可能重复消费同一事件
- 批量回放和补数任务需要可安全重跑

## 常见主题

- 幂等键
- 唯一约束
- `INSERT ... ON CONFLICT`
- 去重表
- 业务状态机

## 设计要点

- 幂等不能只靠应用内缓存，最终仍要落到数据库约束或可校验状态。
- 幂等键要和业务语义绑定，而不是随手生成一次性 UUID。
- `ON CONFLICT DO NOTHING` 只能避免重复插入，不能自动保证业务状态正确。
- 幂等记录需要考虑过期清理、审计字段和重放追踪。

## 关联阅读

- [PostgreSQL 开发专题](./postgresql-development.md)
- [事务与隔离级别专题](./transaction-isolation.md)
- [幂等与重试专题](./idempotency-retries.md)
- [PostgreSQL 锁与并发专题](./postgresql-locking.md)
- [Outbox / Inbox 模式专题](./outbox-inbox-patterns.md)

返回 [索引](../README.md)

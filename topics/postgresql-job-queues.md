# PostgreSQL 任务队列专题

这个专题关注使用 PostgreSQL 表作为轻量任务队列时的建模、竞争控制和消费模式。

## 适用场景

- 中小规模后台任务不想立刻引入独立消息系统
- 任务和业务数据强一致绑定
- 需要简单可靠的延迟重试和失败审计

## 常见主题

- `FOR UPDATE SKIP LOCKED`
- 租约超时
- 失败重试
- 优先级队列
- 死信表

## 设计要点

- PostgreSQL 队列适合中低吞吐、强事务绑定场景，不适合无限膨胀的高吞吐流式系统。
- 消费表需要有清晰的状态机，例如 `pending`、`running`、`done`、`failed`。
- 抢任务 SQL 要避免全表扫描，否则任务越多越慢。
- 重试策略要和幂等执行一起设计，否则失败重放会放大副作用。

## 关联阅读

- [PostgreSQL 幂等写入专题](./postgresql-idempotent-writes.md)
- [事务与隔离级别专题](./transaction-isolation.md)
- [任务队列架构专题](./task-queue-architectures.md)
- [Worker 运行治理专题](./worker-runtime-operations.md)
- [PostgreSQL 锁与并发专题](./postgresql-locking.md)

返回 [索引](../README.md)

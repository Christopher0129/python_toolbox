# PostgreSQL Advisory Lock 专题

这个专题关注 PostgreSQL advisory lock 在分布式互斥、定时任务抢占和批处理去重中的使用边界。

## 适用场景

- 同一时间只允许一个实例执行某类任务
- 定时任务多副本部署，需要选主执行
- 需要轻量互斥而不想引入外部锁服务

## 常见主题

- `pg_advisory_lock`
- `pg_try_advisory_lock`
- 会话级锁
- 事务级锁
- 锁泄漏

## 设计要点

- advisory lock 不会自动表达业务语义，只提供互斥原语。
- 会话级锁要特别注意连接池复用，否则容易出现锁没释放但连接仍存活。
- 使用前要统一 key 编码规则，避免不同模块锁到同一把逻辑锁。
- 它适合控制“谁来做”，不适合替代行级一致性校验。

## 关联阅读

- [PostgreSQL 锁与并发专题](./postgresql-locking.md)
- [PostgreSQL 任务队列专题](./postgresql-job-queues.md)
- [连接池专题](./connection-pooling.md)
- [Worker 运行治理专题](./worker-runtime-operations.md)
- [事故响应专题](./incident-response.md)

返回 [索引](../README.md)

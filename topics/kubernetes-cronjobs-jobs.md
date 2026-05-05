# Kubernetes Job 与 CronJob 专题

这个专题关注批处理、定时任务和一次性任务在 Kubernetes 中的调度、重试和资源治理。

## 适用场景

- 数据回填、索引重建、定时报表、离线同步
- 需要用集群原生能力替代单机 crontab
- 任务经常因为超时、并发冲突或重试策略出问题

## 常见主题

- Job
- CronJob
- 并发策略
- 重试与超时
- 失败清理与历史保留

## 设计要点

- 定时任务最常见的问题不是“没跑”，而是重复跑、跑太久或和线上任务冲突。
- CronJob 要明确并发策略、截止时间和补跑行为。
- 大任务应拆阶段，并结合队列、锁或幂等设计避免重复副作用。
- 任务资源 requests 要单独评估，不能照搬在线服务配置。

## 关联阅读

- [任务调度专题](./task-scheduling.md)
- [Kubernetes 运维专题](./kubernetes-operations.md)
- [Schema 迁移与回填专题](./schema-migrations-backfill.md)
- [索引构建流水线专题](./indexing-pipelines.md)
- [Worker 运行治理专题](./worker-runtime-operations.md)

返回 [索引](../README.md)

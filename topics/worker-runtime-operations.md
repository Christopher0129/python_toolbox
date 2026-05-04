# Worker 运行治理专题

这个专题关注后台 worker、消费者和批处理进程上线后的运行、限流、隔离、观测和回收。

## 适用场景

- Celery / Dramatiq / arq / Kafka consumer 进程
- 大量异步任务和批作业长期运行
- 需要分队列、分资源池和分优先级治理的系统

## 常见主题

- 并发度和 worker 池划分
- 长任务与短任务隔离
- 优雅停机和任务回收
- 心跳、滞留、积压与死信监控
- 资源配额与自恢复

## 设计要点

- 不同任务类型要拆到不同 worker 进程组，避免相互抢占
- 重试策略要和业务幂等设计绑定
- 优雅停机不是附加项，直接关系到任务是否重复或丢失
- 运行治理要同时覆盖 broker、worker 和下游依赖

## 关联阅读

- [任务队列架构专题](./task-queue-architectures.md)
- [流处理专题](./stream-processing.md)
- [psutil](../third_party/psutil.md)
- [Dramatiq](../third_party/dramatiq.md)
- [arq](../third_party/arq.md)

返回 [索引](../README.md)

# 任务队列架构专题

这个专题关注后台任务不只是“异步执行”，而是如何设计任务边界、重试语义、可观测性和隔离策略。

## 适用场景

- 邮件、通知、批处理、导出、清洗等异步作业
- Web 请求降耗，把慢操作移出主链路
- 定时任务与消息驱动任务统一治理

## 常见主题

- actor / task 的粒度设计
- 重试、退避和幂等键
- 延时任务和定时投递
- broker 选择：Redis、RabbitMQ、Kafka
- worker 隔离、并发度和死信队列

## 设计要点

- 任务负载要可切片，避免一个任务包办整条流水线
- 失败告警、人工补跑和审计链路要提前设计
- CPU 重任务和 I/O 重任务应拆到不同 worker 池
- “可重试”必须建立在幂等和副作用控制之上

## 关联阅读

- [缓存与队列专题](./cache-queues.md)
- [消息系统专题](./message-systems.md)
- [Dramatiq](../third_party/dramatiq.md)
- [arq](../third_party/arq.md)
- [celery](../third_party/celery.md)

返回 [索引](../README.md)

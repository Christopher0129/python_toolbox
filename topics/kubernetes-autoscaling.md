# Kubernetes 自动伸缩专题

这个专题关注 Python 服务在 K8s 上如何根据 CPU、队列、请求量和延迟做自动伸缩。

## 适用场景

- 流量波动明显
- worker / consumer 积压会周期性出现
- 想减少人工扩缩容

## 常见主题

- HPA
- KEDA
- 队列驱动伸缩
- 冷启动
- 扩缩容抖动

## 设计要点

- 伸缩指标要和真正瓶颈一致，而不是只看 CPU
- 队列系统更适合看 lag、队列长度和处理时长
- 扩容速度、启动时间和连接池初始化会影响真实收益
- 自动伸缩必须和限流、熔断、容量规划一起看

## 关联阅读

- [Kubernetes 运维专题](./kubernetes-operations.md)
- [容量规划专题](./capacity-planning.md)
- [Consumer Group 运维专题](./consumer-group-operations.md)
- [Worker 运行治理专题](./worker-runtime-operations.md)

返回 [索引](../README.md)

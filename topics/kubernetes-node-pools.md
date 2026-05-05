# Kubernetes 节点池专题

这个专题关注如何为不同工作负载规划节点池、实例类型和隔离策略。

## 适用场景

- 在线服务、批处理、GPU 任务混跑互相影响
- 集群成本高但资源利用率不稳
- 需要把关键服务和普通任务分层承载

## 常见主题

- 节点池分层
- 实例规格选择
- spot / 按需混用
- 污点与容忍
- 扩缩容边界

## 设计要点

- 节点池不是越多越好，过度细分会带来调度碎片和运维复杂度。
- 关键链路服务要优先获得稳定节点和可预期资源。
- 批处理、回填和训练类工作负载更适合和在线服务隔离。
- 节点池策略要和 PDB、优先级、抢占和成本治理一起设计。

## 关联阅读

- [Kubernetes 资源治理专题](./kubernetes-resource-management.md)
- [Kubernetes 调度与亲和性专题](./kubernetes-scheduling-affinity.md)
- [Kubernetes 驱逐专题](./kubernetes-evictions.md)
- [Kubernetes 成本优化专题](./kubernetes-cost-optimization.md)
- [容量规划专题](./capacity-planning.md)

返回 [索引](../README.md)

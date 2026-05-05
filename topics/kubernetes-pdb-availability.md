# Kubernetes PDB 与可用性专题

这个专题关注 PodDisruptionBudget、节点维护和应用可用性之间的约束关系。

## 适用场景

- 节点升级或驱逐时服务可用性受影响
- 副本数较少但又需要平滑维护
- 发布、伸缩和集群运维会互相影响

## 常见主题

- `minAvailable`
- `maxUnavailable`
- voluntary disruption
- drain 行为
- 与 HPA / rollout 协同

## 设计要点

- PDB 保护的是可用副本下限，不是绝对不会中断。
- 副本数少时，PDB 配置错误会直接阻塞运维操作。
- API 服务、worker 和 stateful 组件的 PDB 策略不应完全相同。
- PDB 要和探针、滚动发布和容量冗余一起设计。

## 关联阅读

- [Kubernetes 运维专题](./kubernetes-operations.md)
- [Kubernetes 滚动交付专题](./kubernetes-rolling-delivery.md)
- [Kubernetes 探针与优雅停机专题](./kubernetes-probes-graceful-shutdown.md)
- [容量规划专题](./capacity-planning.md)
- [Runbook 与运维手册专题](./runbooks-and-ops.md)

返回 [索引](../README.md)

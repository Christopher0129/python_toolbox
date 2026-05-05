# Kubernetes 调度与亲和性专题

这个专题关注 Pod 调度、节点选择、亲和性和反亲和性对 Python 服务稳定性的影响。

## 适用场景

- 需要隔离高负载服务与批处理任务
- 需要把有状态组件或 GPU 任务调度到特定节点
- 需要避免单节点故障放大

## 常见主题

- nodeSelector
- node affinity
- pod affinity / anti-affinity
- taints / tolerations
- topology spread constraints

## 设计要点

- 调度约束越多，资源碎片和调度失败概率越高。
- 反亲和通常比“尽量平均”更适合保护高可用副本。
- 批处理、推理和在线 API 服务应分层定义调度策略。
- 调度策略要配合资源 requests 和 PDB 一起看，否则容易互相打架。

## 关联阅读

- [Kubernetes 运维专题](./kubernetes-operations.md)
- [Kubernetes 资源治理专题](./kubernetes-resource-management.md)
- [Kubernetes PDB 与可用性专题](./kubernetes-pdb-availability.md)
- [容量规划专题](./capacity-planning.md)
- [部署与运维专题](./deployment-operations.md)

返回 [索引](../README.md)

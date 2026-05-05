# Kubernetes Stateful 工作负载专题

这个专题关注数据库、消息代理、协调组件等有状态工作负载在 Kubernetes 中的部署与治理边界。

## 适用场景

- 需要运行数据库、队列或持久化服务
- 需要稳定网络标识、顺序启动和持久卷绑定
- 平台团队在评估哪些状态服务适合上 K8s

## 常见主题

- StatefulSet
- PVC / 存储类
- 有序启动与滚动
- 数据持久化
- 节点与存储约束

## 设计要点

- StatefulSet 解决的是身份和存储绑定，不自动解决备份、恢复和一致性问题。
- 有状态组件上 K8s 之前要明确恢复模型和运维职责。
- 存储性能、卷扩容和节点故障行为要先验证。
- Python 服务即使本身无状态，也常常依赖这些有状态底座。

## 关联阅读

- [Kubernetes 运维专题](./kubernetes-operations.md)
- [Kubernetes 调度与亲和性专题](./kubernetes-scheduling-affinity.md)
- [Kubernetes PDB 与可用性专题](./kubernetes-pdb-availability.md)
- [PostgreSQL 备份与恢复专题](./postgresql-backup-restore.md)
- [对象存储专题](./object-storage.md)

返回 [索引](../README.md)

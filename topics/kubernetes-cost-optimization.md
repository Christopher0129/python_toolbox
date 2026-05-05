# Kubernetes 成本优化专题

这个专题关注 Python 服务在 Kubernetes 中的资源浪费、过度冗余和平台层成本治理。

## 适用场景

- 集群账单增长明显但利用率不高
- requests 普遍过高，HPA 效果失真
- 在线服务、批处理和推理任务混部导致成本混乱

## 常见主题

- requests / limits 校正
- 节点利用率
- 自动扩缩容成本
- 混部策略
- 成本归因

## 设计要点

- 成本优化应先找空转资源，再谈架构级削减。
- 请求量、延迟目标和副本冗余共同决定可压缩空间。
- HPA、PDB 和 requests 三者配置不协调时，常常既贵又不稳。
- 成本治理需要落到服务、租户或任务级别归因。

## 关联阅读

- [成本治理专题](./cost-governance.md)
- [Kubernetes 资源治理专题](./kubernetes-resource-management.md)
- [Kubernetes 自动扩缩容专题](./kubernetes-autoscaling.md)
- [容量规划专题](./capacity-planning.md)
- [Worker 运行治理专题](./worker-runtime-operations.md)

返回 [索引](../README.md)

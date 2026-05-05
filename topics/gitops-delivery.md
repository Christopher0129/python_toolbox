# GitOps 交付专题

这个专题关注把部署期望状态放在 Git 中，通过自动同步机制驱动环境变化。

## 适用场景

- Kubernetes 多环境持续交付
- 需要审计、回滚和漂移检测的团队
- 应用配置与基础设施变更统一纳管

## 常见主题

- Git 作为真实来源
- 应用清单和基础设施清单分层
- 回滚与审计
- 环境漂移检测
- 与 Helm / Kustomize 结合

## 设计要点

- GitOps 的关键不只是“用 Git”，而是声明式期望状态和自动收敛
- 应用仓库、环境仓库和平台仓库的边界要清楚
- 自动同步要配合审批、冻结窗口和紧急变更机制
- 漂移修正要区分人为热修和异常越权修改

## 关联阅读

- [Helm 与 Chart 专题](./helm-charts.md)
- [Kubernetes 运维专题](./kubernetes-operations.md)
- [Kubernetes 多集群专题](./kubernetes-multi-cluster.md)
- [基础设施自动化专题](./infrastructure-automation.md)
- [供应链安全专题](./supply-chain-security.md)

返回 [索引](../README.md)

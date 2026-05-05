# Kubernetes 准入控制专题

这个专题关注在资源进入集群前，通过准入控制做策略校验、默认注入和安全防护。

## 适用场景

- 团队希望统一限制危险配置进入集群
- 需要强制要求标签、资源限制、安全上下文
- 平台治理依赖策略而不是人工代码审查

## 常见主题

- Validating Admission
- Mutating Admission
- 标签约束
- 安全基线
- 策略拒绝

## 设计要点

- 准入控制要优先保证错误信息清晰，否则研发会把它当成随机拦截器。
- 拒绝策略应先观察再收紧，避免一次性大面积阻断正常变更。
- 默认注入和强校验要分开管理，防止副作用难以预期。
- 准入控制不是运行时安全替代品，它解决的是“进门前校验”。

## 关联阅读

- [Kubernetes 运维专题](./kubernetes-operations.md)
- [Kubernetes ServiceAccount 与 RBAC 专题](./kubernetes-serviceaccount-rbac.md)
- [Kubernetes NetworkPolicy 专题](./kubernetes-network-policies.md)
- [策略引擎专题](./policy-engines.md)
- [安全基础专题](./security-basics.md)

返回 [索引](../README.md)

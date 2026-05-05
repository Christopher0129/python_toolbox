# Kubernetes 多集群专题

这个专题关注多环境、多地域或多租户场景下，Python 服务如何面对多集群交付与运行治理。

## 适用场景

- 跨地域部署或容灾
- 按业务线或租户拆集群
- 平台团队需要统一多集群交付与观测

## 常见主题

- 环境分层
- 流量切换
- 配置分发
- 多集群 GitOps
- 统一观测与审计

## 设计要点

- 多集群不是复制清单那么简单，关键在于边界、权限和变更传播策略。
- 跨集群服务发现、证书、镜像拉取和告警聚合都要提前规划。
- 同一应用在不同集群中的配置漂移要可见、可比和可回滚。
- 多集群容灾演练必须覆盖数据库、消息系统和外部依赖切换。

## 关联阅读

- [GitOps 交付专题](./gitops-delivery.md)
- [Kubernetes 运维专题](./kubernetes-operations.md)
- [服务发现专题](./service-discovery.md)
- [事故响应专题](./incident-response.md)
- [Runbook 与运维手册专题](./runbooks-and-ops.md)

返回 [索引](../README.md)

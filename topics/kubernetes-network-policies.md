# Kubernetes NetworkPolicy 专题

这个专题关注集群内服务东西向访问控制，以及 Python 服务如何在最小权限网络模型下运行。

## 适用场景

- 多租户或多业务线共用集群
- 需要限制服务只访问必要的数据库、消息系统和内部 API
- 合规或安全要求推动网络最小权限

## 常见主题

- ingress / egress 策略
- namespace 隔离
- 标签选择器
- DNS 与外部依赖放行
- 默认拒绝

## 设计要点

- NetworkPolicy 生效前要先确认底层 CNI 是否支持。
- 默认拒绝能显著提升边界清晰度，但上线前要梳理真实依赖图。
- 数据库、缓存和消息系统通常最值得优先加策略保护。
- 观测和排障链路也要纳入放行规则，否则会造成隐蔽故障。

## 关联阅读

- [安全基础专题](./security-basics.md)
- [Kubernetes 运维专题](./kubernetes-operations.md)
- [服务发现专题](./service-discovery.md)
- [代理与 Egress 治理专题](./proxy-and-egress.md)
- [服务网格专题](./service-mesh.md)

返回 [索引](../README.md)

# Kubernetes 工作负载身份专题

这个专题关注 Pod 如何以最小权限身份访问对象存储、数据库代理和云平台 API。

## 适用场景

- Pod 需要访问云 KMS、对象存储或消息系统
- 团队不希望在容器内分发长期静态密钥
- 平台侧需要审计哪个服务在调用外部资源

## 常见主题

- ServiceAccount
- token projection
- IAM 绑定
- 最小权限
- 身份审计

## 设计要点

- 工作负载身份要优先于静态 AK/SK 直塞环境变量的方案。
- ServiceAccount、RBAC 和云平台权限需要统一治理，避免权限漂移。
- 身份切换和权限回收要可自动化，不依赖人工改 Secret。
- 审计链路应能从外部资源调用追溯到具体命名空间、服务和版本。

## 关联阅读

- [Kubernetes Secret 分发专题](./kubernetes-secret-distribution.md)
- [密钥管理专题](./secrets-management.md)
- [服务间认证专题](./service-to-service-auth.md)
- [Kubernetes 运维专题](./kubernetes-operations.md)
- [RBAC 与 ABAC 专题](./rbac-abac.md)

返回 [索引](../README.md)

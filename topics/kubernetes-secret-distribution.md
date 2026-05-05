# Kubernetes Secret 分发专题

这个专题关注 Secret 在 Kubernetes 中的注入、轮换、最小暴露和与外部密钥系统的协同。

## 适用场景

- 数据库密码、API Key、证书需要统一分发
- 多环境密钥轮换频繁
- 需要把外部密钥管理系统接入集群

## 常见主题

- Secret 挂载与环境变量注入
- 密钥轮换
- 外部 Secret 同步
- 证书分发
- 最小权限访问

## 设计要点

- Secret 只是分发载体，不等于完整密钥治理方案。
- 环境变量注入方便，但会放大泄露面和重载成本。
- 密钥轮换要设计应用侧重连、热更新或滚动重启流程。
- 集群侧 Secret 管理要和审计、RBAC 及外部 KMS 联动。

## 关联阅读

- [密钥管理专题](./secrets-management.md)
- [运行时配置专题](./runtime-configuration.md)
- [Kubernetes 运维专题](./kubernetes-operations.md)
- [认证与授权专题](./auth-authorization.md)
- [供应链安全专题](./supply-chain-security.md)

返回 [索引](../README.md)

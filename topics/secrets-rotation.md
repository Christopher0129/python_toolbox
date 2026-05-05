# 密钥轮换专题

这个专题关注数据库密码、API Key、证书和签名密钥如何安全地换新而不中断业务。

## 适用场景

- 安全合规要求定期轮换凭证
- 密钥泄露后需要快速失效旧凭证
- 多环境、多服务共享同一凭证，变更影响面大

## 常见主题

- 双 key 过渡
- 新旧凭证并存
- 应用热更新
- 连接重建
- 审计与回滚

## 设计要点

- 轮换流程要先设计消费方如何感知新凭证，再设计凭证如何发布。
- 密钥轮换通常需要一个“旧新并存窗口”，避免同时切断所有调用方。
- 数据库、消息系统和第三方 API 的轮换机制不同，不应套用统一脚本。
- 轮换失败时要能快速定位是凭证分发、缓存、连接复用还是权限问题。

## 关联阅读

- [密钥管理专题](./secrets-management.md)
- [Kubernetes Secret 分发专题](./kubernetes-secret-distribution.md)
- [Kubernetes 工作负载身份专题](./kubernetes-workload-identity.md)
- [连接池专题](./connection-pooling.md)
- [API Key 治理专题](./api-key-management.md)

返回 [索引](../README.md)

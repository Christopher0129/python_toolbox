# 服务间认证专题

这个专题关注服务与服务之间如何建立身份、传递信任并收敛凭证治理复杂度。

## 适用场景

- 微服务之间存在大量内部调用
- 需要区分用户身份和服务身份
- 服务网格、网关或工作负载身份开始引入

## 常见主题

- mTLS
- JWT / service token
- ServiceAccount
- 调用方身份透传
- 权限最小化

## 设计要点

- 服务间认证要先明确“代表用户调用”还是“代表服务调用”。
- 长期共享密钥会把服务间边界变得脆弱，优先考虑短期凭证或工作负载身份。
- 身份校验、授权和审计不能只停留在入口网关，东西向调用也要保留链路信息。
- 失败重试、时钟漂移和证书轮换都是服务间认证的常见隐患。

## 关联阅读

- [认证与授权专题](./auth-authorization.md)
- [Token 认证专题](./token-authentication.md)
- [OAuth2 与 OpenID Connect 专题](./oauth2-oidc.md)
- [Kubernetes 工作负载身份专题](./kubernetes-workload-identity.md)
- [API Key 治理专题](./api-key-management.md)

返回 [索引](../README.md)

# JWKS 轮换专题

这个专题关注基于 JWKS 的公钥分发和轮换，确保 token 校验在不停机条件下平滑切换密钥。

## 适用场景

- 多服务依赖同一身份提供方签发 JWT
- 密钥需要定期轮换或紧急替换
- 服务端缓存旧公钥，担心轮换期间验签失败

## 常见主题

- `kid`
- JWKS 缓存
- 预热新公钥
- 双钥并存
- 失效切换

## 设计要点

- 轮换不是简单替换一把 key，而是旧新公钥并存一段时间。
- 服务缓存 JWKS 时要有刷新策略和失败回退策略。
- `kid` 缺失或冲突会让轮换变成高风险操作。
- 紧急撤销场景要和 token 生命周期、吊销策略联动设计。

## 关联阅读

- [Token 认证专题](./token-authentication.md)
- [Token 生命周期专题](./token-lifecycle.md)
- [Token 吊销专题](./token-revocation.md)
- [服务间认证专题](./service-to-service-auth.md)
- [密钥轮换专题](./secrets-rotation.md)

返回 [索引](../README.md)

# 会话管理专题

这个专题关注登录态、会话续期、设备踢出和服务端会话治理，不局限于 JWT。

## 适用场景

- 同时支持浏览器会话和 API token
- 需要支持主动登出、单点踢出和设备管理
- 安全要求比“只校验 token 过期时间”更高

## 常见主题

- 服务端 session
- refresh token
- 设备会话
- 续期策略
- 主动失效

## 设计要点

- token 和 session 不是二选一，很多系统是两层结构。
- 会话模型要明确是否支持多端登录、并发会话上限和风险设备隔离。
- 主动登出、密码修改、权限变化都应能触发会话失效。
- 安全治理要兼顾体验，不能只从“最严格”角度设计。

## 关联阅读

- [Token 认证专题](./token-authentication.md)
- [Token 生命周期专题](./token-lifecycle.md)
- [Token 吊销专题](./token-revocation.md)
- [认证与授权专题](./auth-authorization.md)
- [审计日志专题](./audit-logging.md)

返回 [索引](../README.md)

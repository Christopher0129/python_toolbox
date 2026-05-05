# 密钥管理专题

这个专题关注敏感信息如何脱离代码和普通配置文件，安全地进入应用运行时。

## 常见对象

| 对象 | 示例 |
| --- | --- |
| 数据库密码 | `DATABASE_URL` |
| API Key | 第三方服务访问密钥 |
| 签名密钥 | JWT、Webhook、加密用途 |
| 短期凭证 | 临时 token、动态数据库账号 |

## 推荐原则

- 密钥不进代码仓库
- 不在日志里打印明文密钥
- 区分普通配置与敏感配置
- 密钥轮换要有可执行流程
- 最小权限访问敏感配置源

## 常见方式

- 环境变量
- 部署平台 secret 管理
- Vault 类集中式密钥系统

## 关联阅读

- [hvac](../third_party/hvac.md)
- [配置管理专题](./config-management.md)
- [安全基础专题](./security-basics.md)
- [Token 认证专题](./token-authentication.md)
- [密钥轮换专题](./secrets-rotation.md)
- [Kubernetes Secret 分发专题](./kubernetes-secret-distribution.md)
- [Kubernetes 工作负载身份专题](./kubernetes-workload-identity.md)

返回 [索引](../README.md)

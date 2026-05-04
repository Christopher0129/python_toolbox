# PyJWT

`PyJWT` 适合在 Python 中编码和解码 JSON Web Token，常用于无状态认证和服务间令牌传递。

## 安装

```bash
pip install pyjwt
```

## 基本示例

```python
import jwt

token = jwt.encode({"sub": "user-1"}, "secret", algorithm="HS256")
payload = jwt.decode(token, "secret", algorithms=["HS256"])
print(payload)
```

## 常见场景

- 登录后访问令牌
- 服务间短期凭证
- 轻量声明式身份传递

## 注意事项

- 不要把 JWT 当成会话万能替代品
- 签名算法和密钥管理要明确
- 令牌过期、撤销和刷新策略要单独设计

## 关联阅读

- [认证与授权专题](../topics/auth-authorization.md)
- [安全基础专题](../topics/security-basics.md)

返回 [索引](../README.md)

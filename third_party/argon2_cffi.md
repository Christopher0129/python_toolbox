# argon2-cffi

`argon2-cffi` 适合做密码哈希和验证，比直接存储明文或可逆加密更符合安全实践。

## 安装

```bash
pip install argon2-cffi
```

## 基本示例

```python
from argon2 import PasswordHasher

ph = PasswordHasher()
hashed = ph.hash("secret-password")
ok = ph.verify(hashed, "secret-password")
```

## 关联阅读

- [密码安全专题](../topics/password-security.md)
- [安全基础专题](../topics/security-basics.md)
- [认证与授权专题](../topics/auth-authorization.md)

返回 [索引](../README.md)

# hvac

`hvac` 是 Python 访问 HashiCorp Vault 的常用客户端，适合做密钥、动态凭证和敏感配置读取。

## 安装

```bash
pip install hvac
```

## 基本示例

```python
import hvac

client = hvac.Client(url="http://127.0.0.1:8200", token="root-token")
secret = client.secrets.kv.v2.read_secret_version(path="demo/app")
print(secret["data"]["data"])
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `Client(...)` | 创建 Vault 客户端 |
| `is_authenticated()` | 确认鉴权状态 |
| `secrets.kv.v2.read_secret_version(...)` | 读取 KV secrets |

## 适用场景

- 服务启动时读取密钥
- 按环境隔离敏感配置
- 动态数据库凭证和短期 token 管理

## 关联阅读

- [密钥管理专题](../topics/secrets-management.md)
- [配置管理专题](../topics/config-management.md)
- [安全基础专题](../topics/security-basics.md)

返回 [索引](../README.md)

# secrets 与 base64

`secrets` 适合安全随机数、Token 和密码场景，`base64` 适合二进制与文本之间的可传输编码。

## `secrets` 常用 API

| API | 说明 |
| --- | --- |
| `token_hex(nbytes)` | 生成十六进制安全 token |
| `token_urlsafe(nbytes)` | 生成 URL 安全 token |
| `choice(seq)` | 安全随机选择元素 |

```python
import secrets

print(secrets.token_hex(16))
print(secrets.token_urlsafe(16))
```

## `base64` 常用 API

| API | 说明 |
| --- | --- |
| `b64encode(data)` | Base64 编码 |
| `b64decode(data)` | Base64 解码 |
| `urlsafe_b64encode(data)` | URL 安全编码 |

```python
import base64

raw = b"hello"
encoded = base64.b64encode(raw)
print(encoded)
print(base64.b64decode(encoded))
```

## 常见场景

- 密码重置 token
- API 签名材料封装
- 图片或文件内容的文本化传输

## 注意事项

- Base64 不是加密，只是编码
- 安全随机不要用 `random` 代替 `secrets`

## 关联阅读

- [hashlib](./hashlib.md)
- [json](./json.md)
- [安全基础专题](../topics/security-basics.md)
- [配置管理专题](../topics/config-management.md)

返回 [索引](../README.md)

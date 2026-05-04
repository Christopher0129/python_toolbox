# hashlib 模块

`hashlib` 用于生成哈希摘要，常见于文件校验、接口签名和内容去重。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `hashlib.md5(data)` | MD5 摘要 | `hashlib.md5(b"abc").hexdigest()` |
| `hashlib.sha1(data)` | SHA1 摘要 | `hashlib.sha1(b"abc").hexdigest()` |
| `hashlib.sha256(data)` | SHA256 摘要 | `hashlib.sha256(b"abc").hexdigest()` |
| `obj.update(data)` | 分块更新内容 | `hasher.update(chunk)` |
| `obj.hexdigest()` | 16 进制摘要字符串 | `hasher.hexdigest()` |
| `obj.digest()` | 原始字节摘要 | `hasher.digest()` |

## 示例

```python
import hashlib

text = "hello"
digest = hashlib.sha256(text.encode("utf-8")).hexdigest()
print(digest)
```

## 文件校验示例

```python
import hashlib

hasher = hashlib.sha256()
with open("big.zip", "rb") as f:
    for chunk in iter(lambda: f.read(8192), b""):
        hasher.update(chunk)

print(hasher.hexdigest())
```

## 提醒

- 密码存储不要直接用 `md5` 或裸 `sha256`，应使用 `bcrypt`、`scrypt`、`argon2`
- 大文件校验建议分块读取，不要一次性读入内存

返回 [索引](../README.md)

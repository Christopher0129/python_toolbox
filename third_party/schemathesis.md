# Schemathesis

`Schemathesis` 适合基于 OpenAPI / GraphQL schema 自动生成 API 测试，用来做契约测试、响应校验和接口 fuzzing。

## 安装

```bash
pip install schemathesis
```

## 基本示例

```python
from fastapi import FastAPI
import schemathesis

app = FastAPI()
schema = schemathesis.openapi.from_asgi("/openapi.json", app)
```

命令行也很常用：

```bash
st run openapi.yaml --url http://127.0.0.1:8000
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `schemathesis.openapi.from_asgi(...)` | 直接从 ASGI 应用加载 schema |
| `st run ...` | 按 schema 生成测试并执行 |
| `--mode all` | 同时覆盖正向和负向输入 |

## 适用场景

- API 契约测试
- OpenAPI 响应结构校验
- 基于 schema 的自动化接口 fuzzing

## 关联阅读

- [契约测试专题](../topics/contract-testing.md)
- [接口测试专题](../topics/api-testing.md)
- [API 版本治理专题](../topics/api-versioning.md)

返回 [索引](../README.md)

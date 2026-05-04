# Beanie

`Beanie` 适合在 MongoDB 场景下结合 `Pydantic` 使用文档模型，提供类似 ODM 的开发体验。

## 安装

```bash
pip install beanie motor
```

## 基本示例

```python
from beanie import Document


class User(Document):
    name: str
    age: int
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `Document` | 定义 Mongo 文档模型 |
| `find_one(...)` | 查询文档 |
| `insert()` | 保存文档 |

## 关联阅读

- [MongoDB 开发专题](../topics/mongodb-development.md)
- [pydantic](./pydantic.md)
- [FastAPI 入门](../frameworks/fastapi.md)

返回 [索引](../README.md)

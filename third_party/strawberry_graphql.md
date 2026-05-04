# Strawberry GraphQL

`Strawberry GraphQL` 适合在 Python 中用类型注解定义 GraphQL schema，和 FastAPI 集成体验较好。

## 安装

```bash
pip install strawberry-graphql
```

## 基本示例

```python
import strawberry


@strawberry.type
class Query:
    @strawberry.field
    def hello(self) -> str:
        return "world"
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `@strawberry.type` | 定义 GraphQL 类型 |
| `@strawberry.field` | 定义字段解析器 |
| `strawberry.Schema(...)` | 创建 schema |

## 关联阅读

- [GraphQL API 专题](../topics/graphql-apis.md)
- [FastAPI 入门](../frameworks/fastapi.md)
- [API 开发专题](../topics/api-development.md)

返回 [索引](../README.md)

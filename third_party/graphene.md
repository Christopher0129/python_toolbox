# Graphene

`Graphene` 适合在 Python 中定义 GraphQL schema、类型和查询字段。

## 安装

```bash
pip install graphene
```

## 基本示例

```python
import graphene


class Query(graphene.ObjectType):
    hello = graphene.String()

    def resolve_hello(root, info):
        return "world"
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `ObjectType` | 定义查询 / 变更类型 |
| `Schema(...)` | 创建 GraphQL schema |
| `Field(...)` | 声明嵌套字段 |

## 关联阅读

- [GraphQL API 专题](../topics/graphql-apis.md)
- [API 开发专题](../topics/api-development.md)
- [契约测试专题](../topics/contract-testing.md)

返回 [索引](../README.md)

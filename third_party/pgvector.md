# pgvector

`pgvector` 适合在 PostgreSQL 里直接存储向量、做相似度检索和混合查询，适合中小规模向量场景或想减少系统组件数量的团队。

## 安装

```bash
pip install pgvector
```

## 基本示例

```python
from pgvector.sqlalchemy import Vector
from sqlalchemy.orm import DeclarativeBase, Mapped, mapped_column


class Base(DeclarativeBase):
    pass


class Item(Base):
    __tablename__ = "items"

    id: Mapped[int] = mapped_column(primary_key=True)
    embedding: Mapped[list[float]] = mapped_column(Vector(3))
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `Vector(n)` | 声明向量列类型 |
| 相似度排序 | 在 SQL 中做向量距离排序 |
| 过滤 + 向量检索 | 结合业务字段筛选与向量召回 |

## 使用建议

- 适合先用已有 PostgreSQL 体系快速起步
- 向量检索与事务型负载混在一起时，要注意资源竞争
- 大规模、高并发检索场景仍要评估专用向量库

## 关联阅读

- [PostgreSQL 开发专题](../topics/postgresql-development.md)
- [向量检索专题](../topics/vector-retrieval.md)
- [混合检索专题](../topics/hybrid-retrieval.md)
- [pgvector 检索专题](../topics/pgvector-search.md)

返回 [索引](../README.md)

# SQLModel

`SQLModel` 适合把 `Pydantic` 模型和 SQLAlchemy 风格的表模型结合起来，常见于 FastAPI 场景。

## 安装

```bash
pip install sqlmodel
```

## 基本示例

```python
from sqlmodel import Field, SQLModel


class Hero(SQLModel, table=True):
    id: int | None = Field(default=None, primary_key=True)
    name: str
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `SQLModel` | 定义表模型和数据模型 |
| `Field(...)` | 声明主键、默认值等 |
| `Session(...)` | 执行数据库会话操作 |

## 关联阅读

- [PostgreSQL 开发专题](../topics/postgresql-development.md)
- [API 开发专题](../topics/api-development.md)
- [SQLAlchemy 2.x 基础](../database/sqlalchemy.md)

返回 [索引](../README.md)

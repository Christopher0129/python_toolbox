# SQLAlchemy 2.x 基础

`SQLAlchemy` 是 Python 最常用的 ORM 和 SQL 工具库之一，适合做数据库建模、查询和事务管理。

## 安装

```bash
pip install sqlalchemy
```

## 核心对象

| 对象 | 用途 |
| --- | --- |
| `create_engine()` | 创建数据库连接引擎 |
| `DeclarativeBase` | ORM 模型基类 |
| `mapped_column()` | 声明字段 |
| `Session()` | 会话和事务管理 |
| `select()` | 构造查询 |

## ORM 示例

```python
from sqlalchemy import String, create_engine, select
from sqlalchemy.orm import DeclarativeBase, Mapped, Session, mapped_column

engine = create_engine("sqlite:///demo.db", echo=False)

class Base(DeclarativeBase):
    pass

class User(Base):
    __tablename__ = "users"

    id: Mapped[int] = mapped_column(primary_key=True)
    name: Mapped[str] = mapped_column(String(50))

Base.metadata.create_all(engine)

with Session(engine) as session:
    session.add(User(name="Tom"))
    session.commit()

    users = session.scalars(select(User)).all()
    print(users)
```

## 常见流程

1. `create_engine()`
2. 定义 `Base` 和模型类
3. `Base.metadata.create_all(engine)`
4. 用 `Session` 增删改查

## 提醒

- 新项目建议按 SQLAlchemy 2.x 风格写法组织代码
- Web 项目里通常每次请求使用一次独立 `Session`

返回 [索引](../README.md)

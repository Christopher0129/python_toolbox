# databases

`databases` 适合在异步 Web 服务中以更轻量的方式执行 SQL，常和 SQLAlchemy Core 配合。

## 安装

```bash
pip install databases asyncpg
```

## 基本示例

```python
from databases import Database

database = Database("postgresql+asyncpg://user:pass@localhost/demo")
await database.connect()
rows = await database.fetch_all("select * from users")
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `Database(...)` | 创建异步数据库对象 |
| `connect()` / `disconnect()` | 管理连接生命周期 |
| `fetch_all(...)` | 拉取多行结果 |

## 关联阅读

- [异步数据库专题](../topics/async-database-access.md)
- [API 开发专题](../topics/api-development.md)
- [SQLAlchemy 进阶专题](../topics/sqlalchemy-advanced.md)

返回 [索引](../README.md)

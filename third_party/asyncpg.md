# asyncpg

`asyncpg` 适合在异步 Python 服务里直接访问 PostgreSQL，强调低开销和高性能。

## 安装

```bash
pip install asyncpg
```

## 基本示例

```python
import asyncpg

conn = await asyncpg.connect("postgresql://user:pass@localhost/demo")
rows = await conn.fetch("select * from users")
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `asyncpg.connect(...)` | 建立异步连接 |
| `conn.fetch(...)` | 查询多行结果 |
| `create_pool(...)` | 创建连接池 |

## 关联阅读

- [异步数据库专题](../topics/async-database-access.md)
- [PostgreSQL 开发专题](../topics/postgresql-development.md)
- [异步编程专题](../topics/async-programming.md)

返回 [索引](../README.md)

# psycopg

`psycopg` 是 PostgreSQL 的主流 Python 驱动，适合执行 SQL、事务控制和批量写入。

## 安装

```bash
pip install psycopg
```

## 基本示例

```python
import psycopg

with psycopg.connect("dbname=demo user=postgres") as conn:
    with conn.cursor() as cur:
        cur.execute("select 1")
        print(cur.fetchone())
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `connect(...)` | 建立 PostgreSQL 连接 |
| `cursor.execute(...)` | 执行 SQL |
| `executemany(...)` | 批量执行参数化语句 |

## 关联阅读

- [PostgreSQL 开发专题](../topics/postgresql-development.md)
- [数据库开发专题](../topics/database-development.md)
- [SQL 优化专题](../topics/sql-optimization.md)

返回 [索引](../README.md)

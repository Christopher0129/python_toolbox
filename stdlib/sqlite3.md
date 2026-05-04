# sqlite3 模块

`sqlite3` 是内置轻量数据库模块，适合本地工具、桌面程序、脚本数据缓存和小型项目。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `sqlite3.connect(path)` | 连接数据库文件 | `conn = sqlite3.connect("demo.db")` |
| `conn.cursor()` | 创建游标 | `cur = conn.cursor()` |
| `cursor.execute(sql, params)` | 执行 SQL | `cur.execute("select * from users where id=?", (1,))` |
| `cursor.executemany(sql, rows)` | 批量执行 | `cur.executemany(..., rows)` |
| `conn.commit()` | 提交事务 | `conn.commit()` |
| `conn.rollback()` | 回滚事务 | `conn.rollback()` |
| `cursor.fetchone()` / `fetchall()` | 获取结果 | `rows = cur.fetchall()` |
| `conn.close()` | 关闭连接 | `conn.close()` |

## 示例

```python
import sqlite3

conn = sqlite3.connect("demo.db")
cur = conn.cursor()

cur.execute("create table if not exists users (id integer primary key, name text)")
cur.execute("insert into users (name) values (?)", ("Tom",))
conn.commit()

cur.execute("select id, name from users")
print(cur.fetchall())
conn.close()
```

## 提醒

- SQL 参数要用 `?` 占位，不要拼接字符串
- 小项目直接用 `sqlite3` 很方便，模型复杂后可考虑 `SQLAlchemy`

返回 [索引](../README.md)

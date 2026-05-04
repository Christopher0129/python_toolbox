# PyMySQL

`PyMySQL` 适合从 Python 连接 MySQL / MariaDB，执行事务、查询和批量写入。

## 安装

```bash
pip install pymysql
```

## 基本示例

```python
import pymysql

conn = pymysql.connect(host="127.0.0.1", user="root", password="pwd", database="demo")
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `connect(...)` | 建立 MySQL 连接 |
| `cursor.execute(...)` | 执行 SQL |
| `commit()` | 提交事务 |

## 关联阅读

- [MySQL 开发专题](../topics/mysql-development.md)
- [数据库开发专题](../topics/database-development.md)
- [SQL 优化专题](../topics/sql-optimization.md)

返回 [索引](../README.md)

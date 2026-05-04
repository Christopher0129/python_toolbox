# asyncmy

`asyncmy` 适合在异步服务里访问 MySQL，常用于 FastAPI 或其他 asyncio 服务。

## 安装

```bash
pip install asyncmy
```

## 基本示例

```python
import asyncmy

conn = await asyncmy.connect(host="localhost", user="root", password="pw", db="demo")
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `asyncmy.connect(...)` | 建立异步 MySQL 连接 |
| `conn.cursor()` | 创建异步游标 |
| 连接池支持 | 管理并发数据库访问 |

## 关联阅读

- [异步数据库专题](../topics/async-database-access.md)
- [MySQL 开发专题](../topics/mysql-development.md)
- [异步编程专题](../topics/async-programming.md)

返回 [索引](../README.md)

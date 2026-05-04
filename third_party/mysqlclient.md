# mysqlclient

`mysqlclient` 是常见的 MySQL C 扩展驱动，适合追求兼容性和性能的 MySQL 访问场景。

## 安装

```bash
pip install mysqlclient
```

## 基本示例

```python
import MySQLdb

conn = MySQLdb.connect(host="127.0.0.1", user="root", passwd="pwd", db="demo")
```

## 关联阅读

- [MySQL 开发专题](../topics/mysql-development.md)
- [数据库开发专题](../topics/database-development.md)
- [SQLAlchemy 2.x 基础](../database/sqlalchemy.md)

返回 [索引](../README.md)

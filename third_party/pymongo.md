# PyMongo

`PyMongo` 是 Python 访问 MongoDB 的基础驱动，适合做同步式文档数据库读写。

## 安装

```bash
pip install pymongo
```

## 基本示例

```python
from pymongo import MongoClient

client = MongoClient("mongodb://127.0.0.1:27017")
doc = client.demo.users.find_one({"name": "Tom"})
print(doc)
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `MongoClient(...)` | 连接 MongoDB |
| `find_one(...)` | 查询单条文档 |
| `insert_one(...)` | 插入文档 |

## 关联阅读

- [MongoDB 开发专题](../topics/mongodb-development.md)
- [数据库开发专题](../topics/database-development.md)
- [NoSQL 数据建模](../topics/mongodb-development.md)

返回 [索引](../README.md)

# Motor

`Motor` 适合在异步 Python 服务中访问 MongoDB，常与 FastAPI、异步任务系统一起使用。

## 安装

```bash
pip install motor
```

## 基本示例

```python
from motor.motor_asyncio import AsyncIOMotorClient

client = AsyncIOMotorClient("mongodb://127.0.0.1:27017")
collection = client.demo.users
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `AsyncIOMotorClient(...)` | 创建异步 MongoDB 客户端 |
| `find_one(...)` | 异步查询单条文档 |
| `aggregate(...)` | 执行聚合管道 |

## 关联阅读

- [MongoDB 开发专题](../topics/mongodb-development.md)
- [异步编程专题](../topics/async-programming.md)
- [FastAPI 进阶专题](../topics/fastapi-advanced.md)

返回 [索引](../README.md)

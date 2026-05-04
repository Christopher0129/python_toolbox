# 异步数据库专题

这个专题关注在异步 Python 服务里如何安全地访问数据库，而不是把同步 ORM 直接塞进协程。

## 适用场景

- FastAPI / asyncio 服务里的数据库访问
- 高并发 I/O 密集型接口
- 需要连接池、事务和异步查询控制的系统

## 常见主题

- 异步驱动与同步驱动差异
- 连接池生命周期
- 协程中的事务边界
- SQLAlchemy AsyncSession
- 直接 SQL 与 ORM 取舍

## 设计要点

- 异步服务要尽量避免在主事件循环里执行阻塞数据库调用
- 连接池大小要结合数据库承载和并发模型调优
- 事务作用域应贴近单次请求或单个后台任务
- 异步数据库代码更要注意超时、取消和资源释放

## 关联阅读

- [asyncpg](../third_party/asyncpg.md)
- [databases](../third_party/databases.md)
- [SQLAlchemy 进阶专题](./sqlalchemy-advanced.md)
- [API 开发专题](./api-development.md)

返回 [索引](../README.md)

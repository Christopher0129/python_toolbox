# Redis OM

`Redis OM` 适合把 Redis 中的 JSON / Hash 文档模型化，简化索引和对象式访问。

## 安装

```bash
pip install redis-om
```

## 基本示例

```python
from redis_om import HashModel


class Customer(HashModel):
    name: str
    age: int
```

## 关联阅读

- [Redis 高级专题](../topics/redis-advanced.md)
- [缓存与队列专题](../topics/cache-queues.md)
- [搜索系统专题](../topics/search-systems.md)

返回 [索引](../README.md)

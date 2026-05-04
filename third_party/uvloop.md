# uvloop

`uvloop` 适合替换默认事件循环，在部分异步 I/O 场景中获得更好的吞吐和延迟表现。

## 安装

```bash
pip install uvloop
```

## 基本示例

```python
import uvloop

uvloop.install()
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `uvloop.install()` | 安装替代事件循环 |
| 与 `asyncio` 兼容 | 保持现有协程代码写法 |
| 性能优化入口 | 常用于高并发服务 |

## 关联阅读

- [异步编程专题](../topics/async-programming.md)
- [异步数据库专题](../topics/async-database-access.md)
- [推理优化专题](../topics/inference-optimization.md)

返回 [索引](../README.md)

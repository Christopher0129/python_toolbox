# 装饰器与上下文管理

装饰器适合给函数统一加能力，上下文管理适合管理资源生命周期。这两类写法在日志、权限、缓存、文件和数据库连接中很常见。

## 装饰器解决什么问题

当多个函数都需要“统计耗时、打印日志、做权限校验、重试”时，可以把重复逻辑提取到装饰器。

```python
from functools import wraps
import time


def timing(func):
    @wraps(func)
    def wrapper(*args, **kwargs):
        start = time.perf_counter()
        try:
            return func(*args, **kwargs)
        finally:
            cost = time.perf_counter() - start
            print(f"{func.__name__} took {cost:.4f}s")
    return wrapper


@timing
def slow_add(a, b):
    time.sleep(0.2)
    return a + b
```

## 装饰器的常见用途

- 记录日志
- 统计耗时
- 缓存结果
- 权限校验
- 重试包装

## 上下文管理解决什么问题

上下文管理适合“进入时初始化，退出时清理”的场景。

```python
with open("data.txt", "r", encoding="utf-8") as f:
    text = f.read()
```

除了文件，还常见于：

- 数据库连接
- 临时目录
- 锁
- 网络会话

## 自定义上下文管理

```python
from contextlib import contextmanager
import time


@contextmanager
def timer(label):
    start = time.perf_counter()
    try:
        yield
    finally:
        cost = time.perf_counter() - start
        print(f"{label}: {cost:.4f}s")


with timer("load"):
    sum(range(100000))
```

## 选择建议

| 场景 | 更适合的工具 |
| --- | --- |
| 给函数统一加行为 | 装饰器 |
| 管理资源打开与关闭 | 上下文管理 |
| 两者都需要 | 可以装饰器包一层、内部再用 `with` |

## 常见问题

- 自定义装饰器时忘记 `@wraps`，会丢失原函数名和文档
- 资源清理写在普通代码尾部，异常时可能不会执行
- 把太多业务逻辑塞进装饰器，调试会变难

## 关联阅读

- [time](../stdlib/time.md)
- [contextlib](../stdlib/contextlib.md)
- [logging](../stdlib/logging.md)
- [性能与调试专题](../topics/performance-debugging.md)

返回 [索引](../README.md)

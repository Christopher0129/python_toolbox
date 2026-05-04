# itertools 与 functools

`itertools` 处理高效迭代，`functools` 提供偏函数、缓存、装饰器辅助工具。

## `itertools` 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `chain(a, b)` | 连接多个迭代器 | `chain([1, 2], [3, 4])` |
| `product(a, b)` | 笛卡尔积 | `product([1, 2], ["a", "b"])` |
| `permutations(seq, r)` | 排列 | `permutations([1, 2, 3], 2)` |
| `combinations(seq, r)` | 组合 | `combinations([1, 2, 3], 2)` |
| `count(start=0, step=1)` | 无限计数器 | `count(10, 2)` |
| `cycle(seq)` | 无限循环序列 | `cycle(["A", "B"])` |

## `functools` 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `reduce(func, iterable)` | 归并计算 | `reduce(lambda a, b: a + b, nums)` |
| `partial(func, *args, **kwargs)` | 固定部分参数 | `partial(pow, 2)` |
| `lru_cache(maxsize=128)` | 缓存函数结果 | `@lru_cache(maxsize=None)` |
| `wraps(func)` | 保留装饰器元信息 | `@wraps(func)` |

## 示例

```python
from functools import lru_cache
from itertools import combinations

print(list(combinations([1, 2, 3], 2)))

@lru_cache(maxsize=None)
def fib(n):
    if n < 2:
        return n
    return fib(n - 1) + fib(n - 2)
```

## 提醒

- `count()`、`cycle()` 是无限迭代器，使用时要配合条件截断。
- `lru_cache()` 很适合纯函数，不适合依赖外部可变状态的函数。

返回 [索引](../README.md)

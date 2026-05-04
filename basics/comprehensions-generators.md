# 推导式与生成器

推导式适合简洁地构造新数据，生成器适合延迟计算和节省内存。这两类写法在数据处理、日志流、批量任务里非常常见。

## 三种常用推导式

| 写法 | 用途 | 示例 |
| --- | --- | --- |
| 列表推导式 | 生成新列表 | `[x * 2 for x in nums]` |
| 字典推导式 | 构造映射 | `{x: x * x for x in nums}` |
| 集合推导式 | 去重并转换 | `{name.lower() for name in names}` |

## 列表推导式示例

```python
nums = [1, 2, 3, 4, 5]
evens = [x for x in nums if x % 2 == 0]
squares = [x * x for x in evens]
print(squares)
```

## 生成器表达式

生成器表达式不会一次性把结果全部放进内存。

```python
nums = (x * x for x in range(1_000_000))
print(next(nums))
print(next(nums))
```

适合：

- 大文件逐行处理
- 批量网络结果流式消费
- 中间结果只遍历一次的场景

## `yield` 自定义生成器

```python
from pathlib import Path


def iter_log_files(root: Path):
    for path in root.rglob("*.log"):
        yield path
```

调用方可以边遍历边处理，不必先收集完整列表。

## 何时用推导式，何时不用

| 场景 | 建议 |
| --- | --- |
| 简单过滤、映射 | 优先推导式 |
| 多层复杂条件 | 可以改回普通 `for`，可读性更重要 |
| 数据量大且只遍历一次 | 优先生成器 |
| 需要多次复用结果 | 先转成列表或字典 |

## 常见组合

```python
from collections import Counter

words = ["Python", "python", "Rust", "python"]
counter = Counter(word.lower() for word in words)
print(counter)
```

## 常见问题

- 推导式里塞太多逻辑，会比普通循环更难读
- 生成器一旦消费完就不能直接再次使用
- 调试复杂推导式时，拆回普通循环通常更高效

## 关联阅读

- [常用内置函数](../builtins/common-builtins.md)
- [collections](../stdlib/collections.md)
- [itertools 与 functools](../stdlib/itertools_functools.md)
- [算法与数据结构专题](../topics/algorithms-data-structures.md)
- [数据清洗专题](../topics/data-cleaning.md)

返回 [索引](../README.md)

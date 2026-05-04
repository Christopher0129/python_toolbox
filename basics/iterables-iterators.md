# 可迭代对象与迭代器

理解 iterable 和 iterator 的区别后，很多 `for` 循环、生成器、流式处理代码都会更清楚。

## 核心区别

| 概念 | 说明 | 典型对象 |
| --- | --- | --- |
| 可迭代对象 | 可以被 `for` 遍历 | `list`、`tuple`、`dict`、文件对象 |
| 迭代器 | 可以不断产出下一个值 | `iter(list_obj)`、生成器 |

## `iter()` 和 `next()`

```python
items = [10, 20, 30]
it = iter(items)
print(next(it))
print(next(it))
```

当没有更多元素时，会抛 `StopIteration`。

## `for` 背后做了什么

```python
for item in [1, 2, 3]:
    print(item)
```

本质上是：

1. 先获取迭代器
2. 反复调用 `next()`
3. 捕获 `StopIteration` 后结束

## 生成器也是迭代器

```python
def count_up(limit):
    for i in range(limit):
        yield i

gen = count_up(3)
print(next(gen))
```

## 高价值场景

- 逐行读取大文件
- 流式消费网络响应
- 数据清洗中的延迟处理

## 常见工具

| 工具 | 用途 |
| --- | --- |
| `enumerate()` | 同时拿索引和值 |
| `zip()` | 并行遍历 |
| `map()` | 批量转换 |
| `filter()` | 批量过滤 |
| `iter()` / `next()` | 手动控制迭代 |

## 常见问题

- 迭代器一旦消耗完就不能直接重新遍历
- 调试生成器时，看不到完整结果是正常现象
- 多次复用数据时，常需要先转成 `list`

## 关联阅读

- [推导式与生成器](./comprehensions-generators.md)
- [控制流](./control-flow.md)
- [itertools 与 functools](../stdlib/itertools_functools.md)
- [异步编程专题](../topics/async-programming.md)

返回 [索引](../README.md)

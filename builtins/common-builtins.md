# 常用内置函数

内置函数不需要 `import`，是日常 Python 编码的第一优先级工具。

## 高频函数

| 函数 | 作用 | 示例 |
| --- | --- | --- |
| `len(obj)` | 长度、元素数量 | `len([1, 2, 3])` |
| `range(start, stop, step)` | 生成整数序列 | `for i in range(3): ...` |
| `enumerate(iterable, start=0)` | 拿到索引和值 | `for i, v in enumerate(items): ...` |
| `zip(a, b)` | 并行遍历多个序列 | `for x, y in zip(xs, ys): ...` |
| `sorted(iterable, key=None, reverse=False)` | 返回排序后的新列表 | `sorted(users, key=lambda x: x["age"])` |
| `sum(iterable)` | 求和 | `sum(scores)` |
| `max(iterable)` / `min(iterable)` | 最大值 / 最小值 | `max(nums)` |
| `any(iterable)` / `all(iterable)` | 任一为真 / 全部为真 | `all(flags)` |
| `map(func, iterable)` | 批量转换 | `list(map(str, nums))` |
| `filter(func, iterable)` | 批量过滤 | `list(filter(lambda x: x > 0, nums))` |
| `open(path, mode, encoding)` | 文件读写 | `open("a.txt", "r", encoding="utf-8")` |
| `type(obj)` | 查看类型 | `type(value)` |
| `isinstance(obj, cls)` | 类型判断 | `isinstance(x, int)` |
| `print(*args)` | 输出 | `print("hello")` |
| `abs(x)` / `round(x, n)` | 绝对值 / 四舍五入 | `round(3.14159, 2)` |

## 推荐写法

```python
names = ["Tom", "Amy", "Jack"]

for idx, name in enumerate(names, start=1):
    print(idx, name)

pairs = list(zip(["a", "b"], [1, 2]))
result = sorted(pairs, key=lambda item: item[1], reverse=True)
print(result)
```

## 文件读取模板

```python
with open("data.txt", "r", encoding="utf-8") as f:
    text = f.read()
```

## 常见提醒

- `sorted()` 返回新列表，`list.sort()` 是原地排序。
- `map()`、`filter()` 在 Python 3 返回迭代器，常配合 `list()` 使用。
- 文件操作优先使用 `with open(...)`，避免忘记关闭句柄。

返回 [索引](../README.md)

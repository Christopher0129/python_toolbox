# random 与 math

`random` 用于随机抽样、打乱；`math` 用于基础数学函数和常量。

## `random` 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `random.random()` | `[0, 1)` 浮点数 | `random.random()` |
| `random.randint(a, b)` | 闭区间随机整数 | `random.randint(1, 10)` |
| `random.uniform(a, b)` | 区间随机浮点数 | `random.uniform(1, 10)` |
| `random.choice(seq)` | 随机选一个元素 | `random.choice(names)` |
| `random.choices(seq, k=3)` | 可重复抽样多个元素 | `random.choices(names, k=3)` |
| `random.shuffle(seq)` | 原地打乱列表 | `random.shuffle(cards)` |

## `math` 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `math.sqrt(x)` | 开平方 | `math.sqrt(9)` |
| `math.ceil(x)` | 向上取整 | `math.ceil(3.2)` |
| `math.floor(x)` | 向下取整 | `math.floor(3.8)` |
| `math.fabs(x)` | 绝对值 | `math.fabs(-3.2)` |
| `math.log(x, base)` | 对数 | `math.log(8, 2)` |
| `math.sin(x)` / `math.cos(x)` | 三角函数 | `math.sin(math.pi / 2)` |
| `math.pi` / `math.e` | 常量 | `math.pi` |

## 示例

```python
import math
import random

nums = [1, 2, 3, 4, 5]
random.shuffle(nums)
print(nums)
print(math.sqrt(16), math.ceil(3.14))
```

## 提醒

- `shuffle()` 原地修改列表，没有返回新列表。
- 财务等精确计算不要依赖二进制浮点，可考虑 `decimal`。

返回 [索引](../README.md)

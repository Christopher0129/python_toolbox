# random 模块

`random` 用于随机整数、随机浮点数、抽样、打乱和种子控制。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `random.random()` | 生成 `[0, 1)` 浮点数 | `random.random()` |
| `random.randint(a, b)` | 闭区间随机整数 | `random.randint(1, 10)` |
| `random.randrange(start, stop, step)` | 类似 `range()` 的随机取值 | `random.randrange(0, 10, 2)` |
| `random.uniform(a, b)` | 区间随机浮点数 | `random.uniform(1, 10)` |
| `random.choice(seq)` | 随机取一个元素 | `random.choice(names)` |
| `random.sample(seq, k)` | 无重复抽样 | `random.sample(cards, 5)` |
| `random.choices(seq, k=3)` | 可重复抽样 | `random.choices(names, k=3)` |
| `random.shuffle(seq)` | 原地打乱列表 | `random.shuffle(nums)` |
| `random.seed(x)` | 固定随机种子 | `random.seed(42)` |

## 示例

```python
import random

random.seed(42)
names = ["Tom", "Amy", "Jack", "Lily"]
print(random.choice(names))
print(random.sample(names, 2))
```

## 提醒

- `shuffle()` 原地修改列表，没有返回新列表
- 安全相关随机数不要用 `random`，而应使用 `secrets`

返回 [索引](../README.md)

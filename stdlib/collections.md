# collections 模块

`collections` 提供比内置容器更适合特定场景的数据结构。

## 常用类型

| 类型 | 作用 | 示例 |
| --- | --- | --- |
| `Counter` | 计数器 | `Counter("aab")` |
| `defaultdict` | 自动提供默认值 | `defaultdict(list)` |
| `deque` | 双端队列 | `deque([1, 2, 3])` |
| `namedtuple` | 带字段名的元组 | `Point = namedtuple("Point", "x y")` |

## 示例

```python
from collections import Counter, defaultdict, deque

counter = Counter(["apple", "apple", "banana"])
groups = defaultdict(list)
groups["fruit"].append("apple")

queue = deque([1, 2, 3])
queue.appendleft(0)
queue.append(4)
```

## 高频方法

| 类型 | 方法 | 用途 |
| --- | --- | --- |
| `Counter` | `most_common(n)` | 取出现频率最高的项 |
| `defaultdict` | `d[key].append(v)` | 省掉是否存在的判断 |
| `deque` | `appendleft(x)` / `popleft()` | 队列两端操作 |

## 适用场景

- 统计词频、标签频次：`Counter`
- 按组收集数据：`defaultdict(list)`
- 任务队列、滑动窗口：`deque`

返回 [索引](../README.md)

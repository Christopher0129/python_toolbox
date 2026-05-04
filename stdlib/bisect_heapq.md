# bisect 与 heapq

`bisect` 适合维护有序序列中的插入与查找位置，`heapq` 适合最小堆、Top K、优先队列。

## `bisect` 常用 API

| API | 说明 |
| --- | --- |
| `bisect_left(a, x)` | 找到左侧插入位置 |
| `bisect_right(a, x)` | 找到右侧插入位置 |
| `insort(a, x)` | 在保持有序的前提下插入 |

```python
from bisect import bisect_left, insort

nums = [1, 3, 5]
print(bisect_left(nums, 4))
insort(nums, 4)
print(nums)
```

## `heapq` 常用 API

| API | 说明 |
| --- | --- |
| `heappush(heap, item)` | 入堆 |
| `heappop(heap)` | 弹出最小元素 |
| `heapify(seq)` | 原地转成堆 |
| `nlargest(n, items)` | 取最大的 n 个 |
| `nsmallest(n, items)` | 取最小的 n 个 |

```python
import heapq

heap = [3, 1, 5]
heapq.heapify(heap)
heapq.heappush(heap, 2)
print(heapq.heappop(heap))
```

## 适用场景

- 排名榜和 Top K
- 优先级任务调度
- 有序列表边界查找

## 实战建议

- `heapq` 默认是最小堆
- 需要最大堆时，常用负值技巧或元组排序
- `bisect` 只负责找位置，不会帮你自动排序整个列表

## 关联阅读

- [collections](./collections.md)
- [算法与数据结构专题](../topics/algorithms-data-structures.md)
- [性能与调试专题](../topics/performance-debugging.md)

返回 [索引](../README.md)

# 算法与数据结构专题

这个专题面向两类场景：一是写业务代码时选对数据结构，二是做题或面试时快速定位常见算法套路。

## 先掌握哪些数据结构

| 结构 | 适合场景 | 关键特点 |
| --- | --- | --- |
| `list` | 顺序存储、下标访问 | 追加快，头部插入慢 |
| `tuple` | 不可变序列 | 可做字典键，适合固定结构 |
| `dict` | 键值映射、索引查找 | 平均 `O(1)` 查找 |
| `set` | 去重、成员判断 | 平均 `O(1)` 判断是否存在 |
| `deque` | 队列、滑动窗口 | 两端增删快 |
| `Counter` | 计数、频率统计 | 词频题很常见 |
| `heapq` | Top K、最小堆 | 适合优先级问题 |

## 高频算法套路

### 双指针

适合：有序数组、区间压缩、原地去重

```python
def remove_duplicates(nums):
    if not nums:
        return 0
    slow = 0
    for fast in range(1, len(nums)):
        if nums[fast] != nums[slow]:
            slow += 1
            nums[slow] = nums[fast]
    return slow + 1
```

### 滑动窗口

适合：最长子串、固定窗口统计、子数组问题

```python
from collections import defaultdict

def longest_unique(s):
    seen = defaultdict(int)
    left = 0
    ans = 0
    for right, ch in enumerate(s):
        seen[ch] += 1
        while seen[ch] > 1:
            seen[s[left]] -= 1
            left += 1
        ans = max(ans, right - left + 1)
    return ans
```

### 哈希表

适合：两数之和、计数、去重、快速索引

```python
def two_sum(nums, target):
    index = {}
    for i, num in enumerate(nums):
        need = target - num
        if need in index:
            return [index[need], i]
        index[num] = i
```

### 栈和队列

适合：括号匹配、表达式处理、BFS 层序遍历

```python
from collections import deque

queue = deque([1, 2, 3])
queue.append(4)
print(queue.popleft())
```

### 递归与 DFS / BFS

适合：树、图、回溯、搜索

```python
def dfs(node):
    if not node:
        return
    dfs(node.left)
    dfs(node.right)
```

### 排序与二分

适合：有序数组查找、区间边界、插入位置

```python
def binary_search(nums, target):
    left, right = 0, len(nums) - 1
    while left <= right:
        mid = (left + right) // 2
        if nums[mid] == target:
            return mid
        if nums[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1
```

## Python 刷题高频工具

| 工具 | 用途 |
| --- | --- |
| `enumerate()` | 同时拿索引和值 |
| `zip()` | 并行遍历 |
| `sorted()` | 排序 |
| `collections.Counter` | 计数 |
| `collections.deque` | 队列和双端队列 |
| `itertools.combinations()` | 组合 |
| `heapq` | Top K、优先队列 |

## 复杂度速记

| 操作 | 典型复杂度 |
| --- | --- |
| `dict` / `set` 查找 | 平均 `O(1)` |
| `list.append()` | 摊还 `O(1)` |
| `list.pop(0)` | `O(n)` |
| 排序 | `O(n log n)` |
| 二分查找 | `O(log n)` |
| 全排列 / 回溯 | 常见指数级 |

## 练习建议

1. 先熟悉 `list`、`dict`、`set`、`deque`
2. 再练双指针、滑动窗口、哈希表
3. 然后补 DFS / BFS、堆、二分
4. 写题时先明确：数据结构选什么，时间复杂度目标是什么

## 关联阅读

- [collections](../stdlib/collections.md)
- [itertools 与 functools](../stdlib/itertools_functools.md)
- [常用内置函数](../builtins/common-builtins.md)
- [异常类型合集](../basics/exception-types.md)

返回 [索引](../README.md)

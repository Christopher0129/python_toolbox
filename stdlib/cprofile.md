# cProfile 模块

`cProfile` 适合找出脚本和函数的耗时热点。优化前先测量，通常比凭感觉改代码更可靠。

## 常用方式

| 方式 | 用途 |
| --- | --- |
| `python -m cProfile script.py` | 直接分析整个脚本 |
| `cProfile.run("main()")` | 快速分析一段调用 |
| `cProfile.Profile()` | 在代码里手动开始和停止分析 |
| `pstats.Stats` | 排序和查看结果 |

## 代码示例

```python
import cProfile
import pstats


def work():
    total = 0
    for i in range(100000):
        total += i * i
    return total


profiler = cProfile.Profile()
profiler.enable()
work()
profiler.disable()

stats = pstats.Stats(profiler)
stats.sort_stats("cumtime").print_stats(10)
```

## 常见分析指标

| 指标 | 含义 |
| --- | --- |
| `ncalls` | 调用次数 |
| `tottime` | 函数自身耗时 |
| `cumtime` | 包含子调用的累计耗时 |

## 排查流程

1. 先确认慢的是哪段任务
2. 用 `cProfile` 找热点函数
3. 再决定是改算法、减 I/O、做缓存，还是加并发
4. 修改后重新测量

## 实战建议

- 先用真实输入规模测，不要只看小样本
- 热点常常不在你以为的那一层
- 算法复杂度问题通常比语法级微优化更重要

## 关联阅读

- [time](./time.md)
- [算法与数据结构专题](../topics/algorithms-data-structures.md)
- [性能与调试专题](../topics/performance-debugging.md)

返回 [索引](../README.md)

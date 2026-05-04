# 性能与调试专题

这个专题把 Python 排查“慢”和“错”的常见工具串起来：计时、剖析、日志、断点、异常堆栈和测试复现。

## 先学哪些模块

| 模块 | 作用 | 推荐程度 |
| --- | --- | --- |
| `time` | 基础计时 | 必学 |
| `logging` | 记录运行过程 | 必学 |
| `pdb` | 断点调试 | 高频 |
| `traceback` | 格式化堆栈 | 高频 |
| `cProfile` | 性能热点分析 | 高频 |
| `pytest` | 复现和固化问题 | 高频 |

## 排查“慢”的常见流程

1. 先用 `time.perf_counter()` 做粗测
2. 确认慢在 I/O、算法还是外部依赖
3. 用 `cProfile` 找热点函数
4. 优化后重新测量

## 排查“错”的常见流程

1. 先复现错误
2. 加日志定位输入和状态
3. 必要时用 `pdb` 下断点
4. 记录完整堆栈
5. 最后补测试防回归

## 基础计时示例

```python
import time

start = time.perf_counter()
sum(range(1_000_000))
cost = time.perf_counter() - start
print(cost)
```

## 日志和堆栈示例

```python
import logging
import traceback

logging.basicConfig(level=logging.INFO)

try:
    1 / 0
except Exception:
    logging.error("failed\n%s", traceback.format_exc())
```

## 断点示例

```python
def calc(a, b):
    breakpoint()
    return a / b
```

## 实战建议

- 没有数据的优化通常不可靠
- 报错信息只看最后一行不够，要看完整调用链
- 修完 bug 后最好补自动化测试

## 关联阅读

- [time](../stdlib/time.md)
- [logging](../stdlib/logging.md)
- [traceback](../stdlib/traceback.md)
- [cProfile](../stdlib/cprofile.md)
- [pdb](../stdlib/pdb.md)
- [pytest](../third_party/pytest.md)

返回 [索引](../README.md)

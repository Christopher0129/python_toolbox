# time 模块

`time` 适合处理时间戳、休眠、简单格式化和性能计时，是 `datetime` 的底层补充。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `time.time()` | 当前 Unix 时间戳 | `time.time()` |
| `time.sleep(sec)` | 睡眠等待 | `time.sleep(1)` |
| `time.localtime(ts=None)` | 时间戳转本地时间结构 | `time.localtime()` |
| `time.strftime(fmt, t)` | 时间格式化 | `time.strftime("%Y-%m-%d %H:%M:%S")` |
| `time.perf_counter()` | 高精度性能计时 | `start = time.perf_counter()` |
| `time.monotonic()` | 单调时钟 | `time.monotonic()` |

## 示例

```python
import time

start = time.perf_counter()
time.sleep(0.5)
elapsed = time.perf_counter() - start

print(elapsed)
print(time.strftime("%Y-%m-%d %H:%M:%S", time.localtime()))
```

## 适用场景

- 测脚本耗时
- 简单重试等待
- 获取时间戳

## 提醒

- 需要日期计算时优先用 `datetime`
- 性能计时优先用 `perf_counter()`，不要直接用 `time.time()`

返回 [索引](../README.md)

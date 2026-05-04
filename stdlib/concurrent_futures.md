# concurrent.futures 模块

`concurrent.futures` 提供线程池和进程池的统一接口，适合快速并发执行任务。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `ThreadPoolExecutor(max_workers=n)` | 线程池 | `ThreadPoolExecutor(max_workers=4)` |
| `ProcessPoolExecutor(max_workers=n)` | 进程池 | `ProcessPoolExecutor(max_workers=4)` |
| `submit(fn, *args)` | 提交单个任务 | `future = pool.submit(work, 1)` |
| `map(fn, iterable)` | 批量任务映射 | `pool.map(square, nums)` |
| `as_completed(futures)` | 按完成顺序取结果 | `for f in as_completed(futures): ...` |
| `future.result()` | 获取任务结果 | `future.result()` |

## 线程池示例

```python
from concurrent.futures import ThreadPoolExecutor, as_completed

def work(x):
    return x * x

with ThreadPoolExecutor(max_workers=4) as pool:
    futures = [pool.submit(work, i) for i in range(5)]
    for future in as_completed(futures):
        print(future.result())
```

## 使用建议

- I/O 密集型任务优先 `ThreadPoolExecutor`
- CPU 密集型任务优先 `ProcessPoolExecutor`
- 想快速替代手写线程管理时，这个模块通常比直接用 `threading` 更省事

## 提醒

- 进程池在 Windows 下同样要注意 `if __name__ == "__main__":`
- 提交的大对象会增加序列化开销

返回 [索引](../README.md)

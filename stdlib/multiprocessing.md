# multiprocessing 模块

`multiprocessing` 适合 CPU 密集型任务并行，使用多个进程绕开 GIL 限制。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `Process(target=...)` | 创建子进程 | `Process(target=work)` |
| `process.start()` | 启动进程 | `p.start()` |
| `process.join()` | 等待结束 | `p.join()` |
| `Pool(processes=n)` | 进程池 | `Pool(processes=4)` |
| `pool.map(func, iterable)` | 并行映射 | `pool.map(square, nums)` |
| `Queue()` | 进程间通信 | `queue.put(data)` |
| `Lock()` | 进程锁 | `lock = Lock()` |
| `cpu_count()` | CPU 核心数 | `cpu_count()` |

## 示例

```python
from multiprocessing import Pool

def square(x):
    return x * x

if __name__ == "__main__":
    with Pool(processes=4) as pool:
        print(pool.map(square, [1, 2, 3, 4]))
```

## 关键提醒

- Windows 下必须写 `if __name__ == "__main__":`
- I/O 密集型任务通常优先考虑 `asyncio` 或 `threading`
- 进程间不能直接共享普通内存对象，通常要用 `Queue`、`Pipe` 或 `Manager`

返回 [索引](../README.md)

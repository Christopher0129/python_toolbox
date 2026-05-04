# asyncio 与 threading

`asyncio` 适合高并发 I/O，`threading` 适合简单线程并发或调用阻塞式库。

## `asyncio` 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `asyncio.run(coro)` | 启动异步程序入口 | `asyncio.run(main())` |
| `asyncio.create_task(coro)` | 创建任务 | `task = asyncio.create_task(fetch())` |
| `asyncio.gather(*tasks)` | 并发等待多个任务 | `await asyncio.gather(t1, t2)` |
| `asyncio.sleep(sec)` | 异步等待 | `await asyncio.sleep(1)` |

## `threading` 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `Thread(target=...)` | 创建线程 | `Thread(target=work)` |
| `thread.start()` | 启动线程 | `thread.start()` |
| `thread.join()` | 等待线程结束 | `thread.join()` |
| `Lock()` | 互斥锁 | `lock = Lock()` |
| `Event()` | 线程事件通知 | `event = Event()` |

## `asyncio` 示例

```python
import asyncio

async def work(name):
    await asyncio.sleep(1)
    return f"done: {name}"

async def main():
    results = await asyncio.gather(work("a"), work("b"))
    print(results)

asyncio.run(main())
```

## 使用建议

- 网络请求、数据库 I/O 密集时优先考虑 `asyncio`
- 需要兼容阻塞式库、任务量不大时可用 `threading`
- CPU 密集型任务通常应考虑 `multiprocessing`

返回 [索引](../README.md)

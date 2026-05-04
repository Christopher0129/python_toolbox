# asyncio 模块

`asyncio` 适合高并发 I/O，如大量 HTTP 请求、爬虫、异步数据库和 WebSocket。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `asyncio.run(coro)` | 启动异步程序 | `asyncio.run(main())` |
| `asyncio.create_task(coro)` | 创建异步任务 | `task = asyncio.create_task(fetch())` |
| `asyncio.gather(*tasks)` | 并发等待多个任务 | `await asyncio.gather(t1, t2)` |
| `asyncio.sleep(sec)` | 异步等待 | `await asyncio.sleep(1)` |
| `asyncio.wait_for(coro, timeout)` | 超时控制 | `await asyncio.wait_for(fetch(), 3)` |
| `asyncio.Queue()` | 异步队列 | `queue = asyncio.Queue()` |

## 示例

```python
import asyncio

async def work(name):
    await asyncio.sleep(1)
    return f"done: {name}"

async def main():
    tasks = [asyncio.create_task(work("a")), asyncio.create_task(work("b"))]
    print(await asyncio.gather(*tasks))

asyncio.run(main())
```

## 适用场景

- 大量 I/O 等待
- 高并发接口请求
- 异步消息消费

## 提醒

- `async def` 返回协程对象，需要 `await` 或交给事件循环执行
- 异步函数里不要直接调用阻塞式耗时函数

返回 [索引](../README.md)

# queue 模块

`queue` 提供线程安全队列，适合生产者消费者模型、后台任务分发和多线程之间传递数据。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `Queue(maxsize=0)` | 先进先出队列 | `q = Queue()` |
| `LifoQueue()` | 后进先出队列 | `q = LifoQueue()` |
| `PriorityQueue()` | 优先级队列 | `q = PriorityQueue()` |
| `put(item)` | 放入元素 | `q.put(task)` |
| `get()` | 取出元素 | `task = q.get()` |
| `task_done()` | 标记任务完成 | `q.task_done()` |
| `join()` | 等待全部任务完成 | `q.join()` |
| `empty()` / `full()` | 是否空 / 满 | `q.empty()` |

## 示例

```python
from queue import Queue
from threading import Thread

q = Queue()

def worker():
    while True:
        item = q.get()
        print("processing", item)
        q.task_done()

Thread(target=worker, daemon=True).start()

for i in range(3):
    q.put(i)

q.join()
```

## 适用场景

- 多线程任务调度
- 下载队列、爬虫任务队列
- 主线程和后台线程通信

## 提醒

- `queue.Queue` 主要用于线程，不是进程间通信
- 进程间通信优先使用 `multiprocessing.Queue`

返回 [索引](../README.md)

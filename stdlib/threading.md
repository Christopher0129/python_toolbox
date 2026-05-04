# threading 模块

`threading` 适合简单并发、阻塞式库并发调用和后台任务处理，但不适合 CPU 密集型并行提速。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `Thread(target=..., args=...)` | 创建线程 | `Thread(target=work, args=(1,))` |
| `thread.start()` | 启动线程 | `t.start()` |
| `thread.join()` | 等待线程结束 | `t.join()` |
| `Lock()` | 互斥锁 | `lock = Lock()` |
| `RLock()` | 可重入锁 | `rlock = RLock()` |
| `Event()` | 线程间通知 | `event.set()` |
| `Semaphore(n)` | 并发数量限制 | `Semaphore(3)` |
| `current_thread()` | 当前线程对象 | `current_thread().name` |

## 示例

```python
from threading import Lock, Thread

lock = Lock()
counter = 0

def work():
    global counter
    for _ in range(1000):
        with lock:
            counter += 1

threads = [Thread(target=work) for _ in range(4)]
for t in threads:
    t.start()
for t in threads:
    t.join()

print(counter)
```

## 适用场景

- 网络请求批量并发
- 文件 I/O 并发
- GUI、后台守护线程

## 提醒

- 共享变量修改要考虑加锁
- CPU 密集型任务优先考虑 `multiprocessing`

返回 [索引](../README.md)

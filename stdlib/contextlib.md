# contextlib 模块

`contextlib` 用来更方便地编写和组合上下文管理器，适合资源清理、异常抑制、可选资源和动态管理多个 `with`。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `@contextmanager` | 用生成器快速定义上下文管理器 | `@contextmanager` |
| `closing(obj)` | 把只有 `close()` 的对象包装成上下文管理器 | `with closing(client): ...` |
| `suppress(exc)` | 忽略指定异常 | `with suppress(FileNotFoundError): ...` |
| `nullcontext(value=None)` | 不做任何额外处理的空上下文 | `with nullcontext(session): ...` |
| `ExitStack()` | 动态管理多个上下文 | `with ExitStack() as stack: ...` |

## `contextmanager` 示例

```python
from contextlib import contextmanager
import time


@contextmanager
def timer(label):
    start = time.perf_counter()
    try:
        yield
    finally:
        print(label, time.perf_counter() - start)
```

## `suppress` 示例

```python
from contextlib import suppress
from pathlib import Path

with suppress(FileNotFoundError):
    Path("cache.json").unlink()
```

## `ExitStack` 适合什么场景

当你需要按运行时条件决定打开多少个文件、多少个连接时，`ExitStack` 比手写多层 `with` 更灵活。

```python
from contextlib import ExitStack

paths = ["a.txt", "b.txt"]
with ExitStack() as stack:
    files = [stack.enter_context(open(path, "r", encoding="utf-8")) for path in paths]
    texts = [f.read() for f in files]
```

## 实战建议

- “能不报错就算了”的场景才使用 `suppress`
- 动态资源数量不确定时优先考虑 `ExitStack`
- 如果只是普通文件读写，直接用 `with open(...)` 就够了

## 关联阅读

- [装饰器与上下文管理](../basics/decorators-context-managers.md)
- [tempfile](./tempfile.md)
- [threading](./threading.md)
- [文件处理专题](../topics/file-processing.md)

返回 [索引](../README.md)

# traceback 模块

`traceback` 用于提取、格式化和打印异常堆栈，适合写日志、后台任务错误收集和命令行排错。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `traceback.print_exc()` | 直接打印当前异常堆栈 | `traceback.print_exc()` |
| `traceback.format_exc()` | 以字符串形式返回当前异常堆栈 | `msg = traceback.format_exc()` |
| `traceback.format_exception(exc)` | 格式化指定异常对象 | `traceback.format_exception(exc)` |
| `traceback.extract_tb(tb)` | 提取回溯帧信息 | `traceback.extract_tb(exc.__traceback__)` |

## 基本示例

```python
import logging
import traceback

logging.basicConfig(level=logging.ERROR)

try:
    1 / 0
except Exception:
    logging.error("task failed\n%s", traceback.format_exc())
```

## 适用场景

- 后台线程异常汇总
- CLI 工具错误日志
- Web 接口内部诊断信息记录

## `logging.exception()` 和 `traceback` 的区别

- 只是在 `except` 内记录当前异常时，`logging.exception()` 更直接
- 需要把堆栈作为字符串保存、拼接、上传时，`traceback.format_exc()` 更方便

## 实战建议

- 用户可见错误信息不要直接暴露完整堆栈
- 完整堆栈保留在日志里，外层返回简短提示
- 线上系统要同时记录输入参数、任务 ID、环境信息

## 关联阅读

- [logging](./logging.md)
- [异常处理](../basics/exceptions.md)
- [pdb](./pdb.md)
- [性能与调试专题](../topics/performance-debugging.md)

返回 [索引](../README.md)

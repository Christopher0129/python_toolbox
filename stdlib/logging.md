# logging 模块

`logging` 是标准日志模块，适合替代 `print()` 输出运行信息、警告、错误和异常堆栈。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `logging.basicConfig(...)` | 初始化日志配置 | `logging.basicConfig(level=logging.INFO)` |
| `logging.getLogger(name)` | 获取日志器 | `logger = logging.getLogger(__name__)` |
| `logger.debug(msg)` | 调试日志 | `logger.debug("x=%s", x)` |
| `logger.info(msg)` | 普通信息 | `logger.info("start")` |
| `logger.warning(msg)` | 警告信息 | `logger.warning("bad input")` |
| `logger.error(msg)` | 错误信息 | `logger.error("failed")` |
| `logger.exception(msg)` | 记录异常堆栈 | `logger.exception("request failed")` |
| `logging.FileHandler(path)` | 输出到文件 | `logging.FileHandler("app.log")` |

## 示例

```python
import logging

logging.basicConfig(
    level=logging.INFO,
    format="%(asctime)s %(levelname)s %(name)s %(message)s",
)
logger = logging.getLogger(__name__)

logger.info("service started")
```

## 日志级别

| 级别 | 用途 |
| --- | --- |
| `DEBUG` | 调试细节 |
| `INFO` | 正常运行信息 |
| `WARNING` | 可恢复问题 |
| `ERROR` | 出错但未崩溃 |
| `CRITICAL` | 严重故障 |

## 提醒

- 日志内容优先参数化写法：`logger.info("user=%s", user_id)`
- 捕获异常后需要保留堆栈时优先用 `logger.exception()`

返回 [索引](../README.md)

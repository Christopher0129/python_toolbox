# logging 与 subprocess

`logging` 用于可控日志输出，`subprocess` 用于调用系统命令或外部程序。

## `logging` 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `logging.basicConfig(...)` | 初始化日志配置 | `logging.basicConfig(level=logging.INFO)` |
| `logging.getLogger(name)` | 获取日志器 | `logger = logging.getLogger(__name__)` |
| `logger.info(msg)` | 普通信息 | `logger.info("start")` |
| `logger.warning(msg)` | 警告 | `logger.warning("warn")` |
| `logger.error(msg)` | 错误 | `logger.error("error")` |
| `logger.exception(msg)` | 记录异常堆栈 | `logger.exception("failed")` |

## `subprocess` 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `subprocess.run(cmd, check=True, text=True)` | 执行命令并等待完成 | `subprocess.run(["python", "--version"], check=True, text=True)` |
| `capture_output=True` | 捕获标准输出和错误 | `subprocess.run(..., capture_output=True)` |
| `subprocess.Popen(...)` | 启动长时间运行子进程 | `subprocess.Popen(["ping", "127.0.0.1"])` |

## 示例

```python
import logging
import subprocess

logging.basicConfig(level=logging.INFO, format="%(levelname)s %(message)s")
logger = logging.getLogger(__name__)

result = subprocess.run(
    ["python", "--version"],
    check=True,
    text=True,
    capture_output=True,
)
logger.info("python version: %s", result.stdout.strip())
```

## 提醒

- 工程项目中优先用 `logging`，少直接散落 `print()`
- `subprocess.run()` 推荐传列表参数，不要自己拼接命令字符串

返回 [索引](../README.md)

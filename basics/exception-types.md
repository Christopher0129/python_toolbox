# 异常类型合集

这份文档把 Python 高频异常按场景归类，方便你看到报错名后快速定位问题。

## 参数、类型、值错误

| 异常 | 常见触发场景 | 示例 |
| --- | --- | --- |
| `TypeError` | 类型不对、参数个数不对 | `1 + "2"` |
| `ValueError` | 类型对但值非法 | `int("abc")` |
| `AssertionError` | 断言失败 | `assert x > 0` |
| `NotImplementedError` | 方法未实现 | `raise NotImplementedError` |

## 索引、键、名称错误

| 异常 | 常见触发场景 | 示例 |
| --- | --- | --- |
| `IndexError` | 列表下标越界 | `items[10]` |
| `KeyError` | 字典键不存在 | `data["name"]` |
| `AttributeError` | 对象没有该属性 | `obj.missing` |
| `NameError` | 变量未定义 | `print(x)` |

## 数学与状态错误

| 异常 | 常见触发场景 | 示例 |
| --- | --- | --- |
| `ZeroDivisionError` | 被零除 | `1 / 0` |
| `OverflowError` | 数值超出范围 | 极大数值运算 |
| `RuntimeError` | 一般运行期错误 | 框架运行状态异常 |
| `RecursionError` | 递归过深 | 无限递归 |

## 文件、导入、系统错误

| 异常 | 常见触发场景 | 示例 |
| --- | --- | --- |
| `FileNotFoundError` | 文件不存在 | `open("missing.txt")` |
| `PermissionError` | 权限不足 | 写受限目录 |
| `IsADirectoryError` | 把目录当文件打开 | `open("folder")` |
| `ImportError` | 导入失败 | `from pkg import bad_name` |
| `ModuleNotFoundError` | 模块不存在 | `import not_exist_module` |
| `OSError` | 操作系统层异常基类 | 路径、进程、网络底层错误 |

## 网络与 I/O 相关

| 异常 | 常见触发场景 |
| --- | --- |
| `TimeoutError` | 超时 |
| `ConnectionError` | 连接类异常基类 |
| `BrokenPipeError` | 管道或连接已断开 |
| `ConnectionRefusedError` | 目标端口拒绝连接 |
| `ConnectionResetError` | 对端重置连接 |

## 编码与文本错误

| 异常 | 常见触发场景 |
| --- | --- |
| `UnicodeEncodeError` | 编码失败 |
| `UnicodeDecodeError` | 解码失败 |
| `UnicodeError` | Unicode 相关异常基类 |

## 迭代与流程控制相关

| 异常 | 说明 |
| --- | --- |
| `StopIteration` | 迭代器结束 |
| `StopAsyncIteration` | 异步迭代结束 |
| `GeneratorExit` | 生成器关闭 |
| `KeyboardInterrupt` | 用户中断程序，常见于 `Ctrl+C` |
| `SystemExit` | 程序主动退出，常由 `sys.exit()` 触发 |

## 异常处理建议

- 优先捕获具体异常，不要直接裸 `except:`
- 需要记录完整堆栈时，配合 `logging.exception()`
- 文件、网络、数据库代码要明确处理 `FileNotFoundError`、`TimeoutError`、`ConnectionError`

## 自定义异常模板

```python
class AppError(Exception):
    """业务异常基类"""

class ConfigError(AppError):
    """配置错误"""

raise ConfigError("missing config file")
```

返回 [索引](../README.md)

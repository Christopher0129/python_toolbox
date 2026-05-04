# 异常处理

异常处理用于让程序在出错时有明确分支，而不是直接崩溃。

## 基本结构

```python
try:
    value = int("123")
except ValueError as e:
    print("转换失败", e)
else:
    print("成功", value)
finally:
    print("无论如何都会执行")
```

## 常见异常

| 异常 | 场景 |
| --- | --- |
| `ValueError` | 值格式不合法 |
| `TypeError` | 类型不匹配 |
| `KeyError` | 字典键不存在 |
| `IndexError` | 下标越界 |
| `FileNotFoundError` | 文件不存在 |
| `ZeroDivisionError` | 除零 |

## 主动抛异常

```python
def set_age(age):
    if age < 0:
        raise ValueError("age cannot be negative")
```

## 自定义异常

```python
class AppError(Exception):
    pass
```

## 建议

- 只捕获你能处理的异常类型，不要直接裸 `except:`
- 记录错误上下文时，工程代码优先配合 `logging.exception()`

返回 [索引](../README.md)

# doctest 模块

`doctest` 允许把示例直接写进文档字符串，再自动运行验证，适合小工具函数和教学型代码。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `doctest.testmod()` | 运行当前模块中的 doctest | `doctest.testmod()` |
| `doctest.testfile(path)` | 运行外部文本文件中的 doctest | `doctest.testfile("demo.txt")` |
| `doctest.run_docstring_examples(func, globals())` | 只跑某个对象的示例 | `doctest.run_docstring_examples(...)` |

## 示例

```python
def add(a, b):
    """
    >>> add(1, 2)
    3
    >>> add(-1, 1)
    0
    """
    return a + b

if __name__ == "__main__":
    import doctest
    doctest.testmod()
```

## 适用场景

- 小函数的输入输出示例
- 教学文档中的可执行代码
- 给简单工具函数加最小测试覆盖

## 提醒

- doctest 对输出格式敏感，空格和换行都要一致
- 复杂业务测试更适合 `unittest` 或 `pytest`

返回 [索引](../README.md)

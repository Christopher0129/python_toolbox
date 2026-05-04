# io 与 textwrap

`io` 适合处理内存文件对象，`textwrap` 适合文本折行、缩进和清理缩进。

## `io` 常用对象

| 对象 | 用途 |
| --- | --- |
| `StringIO` | 在内存中处理文本流 |
| `BytesIO` | 在内存中处理二进制流 |

```python
from io import StringIO

buf = StringIO()
buf.write("hello")
print(buf.getvalue())
```

## `textwrap` 常用 API

| API | 说明 |
| --- | --- |
| `fill(text, width=...)` | 按宽度折行 |
| `wrap(text, width=...)` | 返回折行后的列表 |
| `dedent(text)` | 去除公共缩进 |
| `indent(text, prefix)` | 添加缩进 |

```python
from textwrap import dedent, fill

text = dedent("""
    hello
    python
""").strip()

print(fill(text, width=10))
```

## 适用场景

- 构造测试输入输出
- 生成 CLI 帮助文本
- 处理中间文本内容

## 关联阅读

- [argparse](./argparse.md)
- [string](./string.md)
- [命令行自动化专题](../topics/automation-cli.md)

返回 [索引](../README.md)

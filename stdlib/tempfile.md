# tempfile 模块

`tempfile` 用于安全创建临时文件和临时目录，适合下载中转、测试隔离和短期缓存。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `TemporaryFile()` | 创建匿名临时文件 | `with tempfile.TemporaryFile() as f:` |
| `NamedTemporaryFile()` | 创建带文件名的临时文件 | `with tempfile.NamedTemporaryFile(suffix=".txt") as f:` |
| `TemporaryDirectory()` | 创建临时目录 | `with tempfile.TemporaryDirectory() as d:` |
| `mkstemp()` | 返回底层文件描述符和路径 | `fd, path = tempfile.mkstemp()` |
| `mkdtemp()` | 创建临时目录并返回路径 | `path = tempfile.mkdtemp()` |

## 示例

```python
import tempfile
from pathlib import Path

with tempfile.TemporaryDirectory() as temp_dir:
    p = Path(temp_dir) / "demo.txt"
    p.write_text("hello", encoding="utf-8")
    print(p.read_text(encoding="utf-8"))
```

## 适用场景

- 测试里放临时输出文件
- 下载压缩包后临时解压
- 调用外部命令时做中转文件

## 提醒

- `with` 结束后，临时目录和文件通常会自动清理
- Windows 下 `NamedTemporaryFile()` 被占用时可能无法再次打开，要注意打开方式

返回 [索引](../README.md)

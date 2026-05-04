# pathlib 模块

`pathlib` 是现代 Python 中推荐优先使用的路径处理方式，比 `os.path` 更直观。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `Path(path)` | 创建路径对象 | `p = Path("data")` |
| `p.exists()` | 是否存在 | `p.exists()` |
| `p.is_file()` / `p.is_dir()` | 文件 / 目录判断 | `p.is_dir()` |
| `p.mkdir(parents=True, exist_ok=True)` | 创建目录 | `p.mkdir(parents=True, exist_ok=True)` |
| `p.iterdir()` | 遍历子项 | `for child in p.iterdir(): ...` |
| `p.glob("*.py")` | 匹配文件 | `list(p.glob("*.md"))` |
| `p.rglob("*.py")` | 递归匹配文件 | `list(p.rglob("*.py"))` |
| `p.read_text(encoding="utf-8")` | 读文本 | `p.read_text(encoding="utf-8")` |
| `p.write_text(text, encoding="utf-8")` | 写文本 | `p.write_text("hello", encoding="utf-8")` |
| `p.resolve()` | 取绝对路径 | `p.resolve()` |

## 常用属性

| 属性 | 说明 |
| --- | --- |
| `p.name` | 文件名 |
| `p.stem` | 不带后缀的文件名 |
| `p.suffix` | 后缀 |
| `p.parent` | 父目录 |

## 示例

```python
from pathlib import Path

root = Path("project")
for file in root.rglob("*.py"):
    print(file.name, file.parent)
```

## 经验建议

- 涉及路径拼接时，可直接写 `root / "data" / "a.json"`
- 读写文件时，`Path` 往往比 `open()` 更简洁

返回 [索引](../README.md)

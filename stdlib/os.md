# os 模块

`os` 适合处理工作目录、环境变量、目录遍历、删除重命名等操作系统相关任务。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `os.getcwd()` | 当前工作目录 | `os.getcwd()` |
| `os.chdir(path)` | 切换工作目录 | `os.chdir("demo")` |
| `os.listdir(path=".")` | 列出目录项 | `os.listdir(".")` |
| `os.mkdir(path)` | 创建单级目录 | `os.mkdir("logs")` |
| `os.makedirs(path, exist_ok=True)` | 递归创建目录 | `os.makedirs("a/b/c", exist_ok=True)` |
| `os.remove(path)` | 删除文件 | `os.remove("a.txt")` |
| `os.rmdir(path)` | 删除空目录 | `os.rmdir("tmp")` |
| `os.rename(src, dst)` | 重命名 | `os.rename("a.txt", "b.txt")` |
| `os.walk(path)` | 递归遍历目录树 | `for root, dirs, files in os.walk(".")` |
| `os.environ.get("NAME")` | 读取环境变量 | `os.environ.get("PATH")` |

## `os.path` 常用方法

| API | 说明 |
| --- | --- |
| `os.path.join(a, b)` | 拼接路径 |
| `os.path.exists(path)` | 路径是否存在 |
| `os.path.isfile(path)` | 是否文件 |
| `os.path.isdir(path)` | 是否目录 |
| `os.path.basename(path)` | 文件名 |
| `os.path.dirname(path)` | 父目录 |

## 示例

```python
import os

for root, dirs, files in os.walk("project"):
    for name in files:
        if name.endswith(".py"):
            print(os.path.join(root, name))
```

## 何时优先用 `pathlib`

- 新代码里，路径处理建议优先用 `pathlib`
- 需要环境变量、进程级目录操作时，再用 `os`

返回 [索引](../README.md)

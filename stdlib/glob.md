# glob 模块

`glob` 用于按通配符批量匹配文件路径，常见于日志清理、批量导入和文件统计。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `glob.glob(pattern)` | 返回匹配到的路径列表 | `glob.glob("logs/*.txt")` |
| `glob.iglob(pattern)` | 返回惰性迭代器 | `glob.iglob("**/*.py", recursive=True)` |
| `recursive=True` | 支持 `**` 递归匹配 | `glob.glob("**/*.md", recursive=True)` |

## 示例

```python
import glob

for path in glob.glob("data/*.csv"):
    print(path)

for path in glob.iglob("project/**/*.py", recursive=True):
    print(path)
```

## 常见通配符

| 写法 | 含义 |
| --- | --- |
| `*` | 任意长度字符 |
| `?` | 单个字符 |
| `[abc]` | 集合内任一字符 |
| `**` | 递归匹配目录树 |

## 提醒

- 返回的是路径字符串，不是 `Path` 对象
- 新代码如果要继续做路径处理，常配合 `pathlib.Path` 一起使用

返回 [索引](../README.md)

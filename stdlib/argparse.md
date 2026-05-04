# argparse 模块

`argparse` 是标准库里的命令行参数解析器，适合写脚本工具、批处理程序和 CLI。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `ArgumentParser()` | 创建解析器 | `parser = argparse.ArgumentParser()` |
| `add_argument(name, ...)` | 添加参数 | `parser.add_argument("--port", type=int)` |
| `parse_args()` | 解析命令行参数 | `args = parser.parse_args()` |
| `choices=[...]` | 限定可选值 | `choices=["dev", "prod"]` |
| `action="store_true"` | 布尔开关参数 | `--verbose` |
| `nargs="+"` | 接收多个值 | `parser.add_argument("files", nargs="+")` |

## 示例

```python
import argparse

parser = argparse.ArgumentParser(description="Demo CLI")
parser.add_argument("name")
parser.add_argument("--port", type=int, default=8000)
parser.add_argument("--debug", action="store_true")
args = parser.parse_args()

print(args.name, args.port, args.debug)
```

## 常见模式

- 位置参数：必须提供，例如文件名
- 可选参数：带 `--` 前缀，例如 `--port`
- 开关参数：搭配 `store_true`

## 提醒

- 需要数字时记得加 `type=int`
- 参数多时可用 `parser.add_argument_group()` 分组提升帮助信息可读性

返回 [索引](../README.md)

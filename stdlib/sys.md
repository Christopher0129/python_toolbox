# sys 模块

`sys` 提供 Python 解释器运行时信息，常用于拿启动参数、退出程序、查看模块搜索路径和标准输入输出。

## 常用 API / 属性

| API / 属性 | 说明 | 示例 |
| --- | --- | --- |
| `sys.argv` | 命令行参数列表 | `print(sys.argv)` |
| `sys.path` | 模块搜索路径 | `print(sys.path)` |
| `sys.exit(code)` | 退出程序 | `sys.exit(1)` |
| `sys.platform` | 当前平台标识 | `sys.platform` |
| `sys.version` | Python 版本字符串 | `sys.version` |
| `sys.stdin` / `sys.stdout` / `sys.stderr` | 标准输入输出流 | `sys.stdout.write("ok")` |
| `sys.modules` | 已导入模块缓存 | `"json" in sys.modules` |

## 示例

```python
import sys

print("argv:", sys.argv)
print("python:", sys.version)

if len(sys.argv) < 2:
    print("usage: python app.py <name>")
    sys.exit(1)
```

## 常见用途

- 配合 `argparse` 处理命令行程序
- 临时追加 `sys.path` 调试模块导入
- 用 `sys.exit()` 返回明确退出码

## 提醒

- 生产代码里不要滥改 `sys.path`，更推荐整理项目结构
- 错误信息建议输出到 `sys.stderr`

返回 [索引](../README.md)

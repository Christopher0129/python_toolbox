# rich

`rich` 适合在终端输出更清晰的表格、树、进度条和高亮文本，尤其适合 CLI 工具和调试输出。

## 安装

```bash
pip install rich
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `print()` | 富文本终端输出 |
| `Table` | 打印表格 |
| `Progress` | 进度条 |
| `Tree` | 树形结构 |
| `Console` | 更细粒度控制输出 |

## 基本示例

```python
from rich import print
from rich.table import Table

table = Table(title="Users")
table.add_column("Name")
table.add_column("Age")
table.add_row("Tom", "18")

print(table)
```

## 适用场景

- 命令行工具
- 巡检脚本
- 调试复杂结构

## 关联阅读

- [argparse](../stdlib/argparse.md)
- [logging](../stdlib/logging.md)
- [命令行自动化专题](../topics/automation-cli.md)

返回 [索引](../README.md)

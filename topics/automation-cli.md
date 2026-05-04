# 命令行自动化专题

这个专题把 Python 写自动化脚本的常见链路串起来：参数解析、文件处理、日志记录、调用外部命令、配置读取和错误退出。

## 先学哪些模块

| 模块 | 作用 | 推荐程度 |
| --- | --- | --- |
| `argparse` | 解析命令行参数 | 必学 |
| `pathlib` | 路径处理和文件读写 | 必学 |
| `logging` | 输出运行日志 | 必学 |
| `subprocess` | 调用外部命令 | 高频 |
| `sys` | 退出码、标准输入输出 | 高频 |
| `json` / `csv` | 配置和数据交换 | 高频 |
| `tempfile` | 临时中转目录 | 常用 |

## 典型工作流

### 1. 解析命令参数

```python
import argparse

parser = argparse.ArgumentParser()
parser.add_argument("src")
parser.add_argument("--verbose", action="store_true")
args = parser.parse_args()
```

### 2. 读取输入并处理

```python
from pathlib import Path

text = Path(args.src).read_text(encoding="utf-8")
print(len(text.splitlines()))
```

### 3. 输出日志

```python
import logging

logging.basicConfig(level=logging.INFO)
logging.info("start processing")
```

### 4. 调外部命令

```python
import subprocess

result = subprocess.run(["python", "--version"], text=True, capture_output=True, check=True)
print(result.stdout.strip())
```

## 一个推荐脚本结构

```text
tool/
  app.py
  config.json
  logs/
```

代码层建议：

- `parse_args()`：只负责参数解析
- `main()`：组织主流程
- `run_xxx()`：拆业务步骤
- 独立函数不要直接依赖命令行对象

## 常见任务到模块映射

| 任务 | 模块组合 |
| --- | --- |
| 批量改名 | `argparse` + `pathlib` |
| 调命令并记录结果 | `subprocess` + `logging` |
| 导出清洗结果 | `json` / `csv` + `pathlib` |
| 临时下载再转换 | `tempfile` + `requests` |

## 实战建议

- CLI 脚本一定要给出清晰错误信息和退出码
- 路径参数尽量统一转成 `Path`
- 有副作用的批量操作先加“预览模式”或确认开关

## 关联阅读

- [argparse](../stdlib/argparse.md)
- [pathlib](../stdlib/pathlib.md)
- [logging](../stdlib/logging.md)
- [subprocess](../stdlib/subprocess.md)
- [常见 Python 实战脚本](../examples/common_cases.md)

返回 [索引](../README.md)

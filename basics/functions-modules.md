# 函数与模块组织

函数和模块组织决定代码是否容易复用、测试和维护。写脚本时能跑起来不难，难的是后面还能改得动。

## 函数设计的核心点

| 主题 | 建议 |
| --- | --- |
| 单一职责 | 一个函数尽量只做一件事 |
| 参数设计 | 优先显式参数，避免隐式依赖全局变量 |
| 返回值 | 用返回值传递结果，不要大量 `print()` 代替结果 |
| 异常处理 | 能处理再捕获，处理不了就向上抛 |
| 命名 | 用动词描述行为，如 `load_users()`、`save_report()` |

## 常见参数写法

```python
def greet(name, times=1, *, upper=False):
    text = f"hello, {name}"
    if upper:
        text = text.upper()
    return [text for _ in range(times)]
```

- 默认参数适合表达“通常情况”
- `*` 后面的参数只能用关键字传入，适合减少误用
- `*args` 适合接收额外位置参数，`**kwargs` 适合转发配置

## 模块拆分思路

当一个文件开始同时处理“数据读取、业务逻辑、命令行入口、日志输出”时，就该拆分模块了。

```text
project/
  app/
    __init__.py
    cli.py
    service.py
    storage.py
    models.py
  tests/
```

常见拆分方式：

- `cli.py`：命令行入口、参数解析
- `service.py`：业务逻辑
- `storage.py`：文件、数据库、外部接口访问
- `models.py`：数据结构、数据类、类型定义

## 导入写法建议

```python
from pathlib import Path
from collections import Counter

import json
import logging
```

- 标准库、第三方库、本地模块分组导入
- 优先导入“模块”或“明确对象”，避免 `from x import *`
- 循环导入通常说明模块职责拆分不合理

## 一个可维护的脚本结构

```python
import argparse
from pathlib import Path


def load_text(path: Path) -> str:
    return path.read_text(encoding="utf-8")


def count_lines(text: str) -> int:
    return len(text.splitlines())


def main() -> None:
    parser = argparse.ArgumentParser()
    parser.add_argument("path")
    args = parser.parse_args()

    text = load_text(Path(args.path))
    print(count_lines(text))


if __name__ == "__main__":
    main()
```

## 常见问题

- 函数过长：超过一个屏幕且混合多种职责时就该拆
- 全局状态太多：测试困难，复用困难
- 导入时执行副作用：模块一导入就发请求、读文件、写数据库，通常不合适

## 关联阅读

- [常用内置函数](../builtins/common-builtins.md)
- [异常处理](./exceptions.md)
- [typing 与 dataclasses](../stdlib/typing_dataclasses.md)
- [命令行自动化专题](../topics/automation-cli.md)
- [项目结构专题](../topics/project-structure.md)

返回 [索引](../README.md)

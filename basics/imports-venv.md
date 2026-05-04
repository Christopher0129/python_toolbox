# 导入、包与虚拟环境

Python 项目一旦从单文件脚本发展成多模块工程，就需要理解导入机制、包结构和虚拟环境。

## 常见导入方式

```python
import json
from pathlib import Path
from collections import Counter
```

建议：

- 优先导入明确模块或对象
- 避免 `from x import *`

## 模块与包

| 概念 | 说明 |
| --- | --- |
| 模块 | 一个 `.py` 文件 |
| 包 | 一个目录，通常包含 `__init__.py` |

```text
project/
  app/
    __init__.py
    service.py
```

## 相对导入和绝对导入

- 绝对导入：`from app.service import run`
- 相对导入：`from .service import run`

通常建议：

- 应用代码优先绝对导入
- 包内部少量场景可使用相对导入

## `sys.path` 是什么

Python 会按 `sys.path` 中的路径查找模块。

```python
import sys
print(sys.path)
```

常见问题：

- 当前工作目录不对
- 包结构不规范
- 直接改 `sys.path` 掩盖了真正结构问题

## 虚拟环境 `venv`

```bash
python -m venv .venv
```

作用：

- 隔离不同项目依赖
- 避免全局环境冲突

## 安装与冻结依赖

```bash
pip install requests
pip freeze > requirements.txt
```

更现代的项目也常用 `pyproject.toml` 管理依赖与构建。

## 常见问题

- `ModuleNotFoundError`：通常是没安装、环境不对或导入路径不对
- 本地能跑、别人机器不能跑：通常是依赖没固定

## 关联阅读

- [sys](../stdlib/sys.md)
- [项目结构专题](../topics/project-structure.md)
- [打包与发布专题](../topics/packaging-release.md)
- [配置管理专题](../topics/config-management.md)

返回 [索引](../README.md)

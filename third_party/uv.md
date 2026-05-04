# uv

`uv` 适合统一管理 Python 解释器、虚拟环境、依赖安装和脚本运行，强调快和简洁。

## 安装

```bash
pip install uv
```

## 基本示例

```bash
uv venv
uv pip install requests
uv run python app.py
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `uv venv` | 创建虚拟环境 |
| `uv pip install ...` | 安装依赖 |
| `uv run ...` | 在项目环境中运行命令 |

## 关联阅读

- [Python 包管理专题](../topics/python-package-management.md)
- [打包与发布专题](../topics/packaging-release.md)
- [项目结构专题](../topics/project-structure.md)

返回 [索引](../README.md)

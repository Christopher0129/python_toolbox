# Poetry

`Poetry` 适合用 `pyproject.toml` 管理依赖、锁文件、虚拟环境和发布流程，常见于中大型 Python 项目。

## 安装

```bash
pip install poetry
```

## 基本示例

```bash
poetry init
poetry add requests
poetry run pytest
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `poetry add ...` | 添加依赖 |
| `poetry lock` | 更新锁文件 |
| `poetry run ...` | 在项目环境中执行命令 |

## 关联阅读

- [Python 包管理专题](../topics/python-package-management.md)
- [依赖治理专题](../topics/dependency-governance.md)
- [打包与发布专题](../topics/packaging-release.md)

返回 [索引](../README.md)

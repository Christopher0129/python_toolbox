# PDM

`PDM` 适合围绕 `pyproject.toml` 做现代依赖管理，强调标准化、锁文件和多 Python 版本协作。

## 安装

```bash
pip install pdm
```

## 基本示例

```bash
pdm init
pdm add httpx
pdm run python app.py
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `pdm add ...` | 添加依赖 |
| `pdm lock` | 生成或更新锁文件 |
| `pdm run ...` | 在项目环境执行命令 |

## 关联阅读

- [Python 包管理专题](../topics/python-package-management.md)
- [依赖治理专题](../topics/dependency-governance.md)
- [Monorepo 与多包项目专题](../topics/monorepo-multipackage.md)

返回 [索引](../README.md)

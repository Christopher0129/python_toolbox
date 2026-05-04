# Hatch

`Hatch` 适合管理构建、环境矩阵和项目脚本，尤其适合需要多测试环境和发布流程的库项目。

## 安装

```bash
pip install hatch
```

## 基本示例

```bash
hatch new demo_pkg
hatch run test
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `hatch env create` | 创建环境 |
| `hatch run ...` | 运行脚本或测试 |
| `hatch build` | 构建分发包 |

## 关联阅读

- [Python 包管理专题](../topics/python-package-management.md)
- [打包与发布专题](../topics/packaging-release.md)
- [测试矩阵专题](../topics/test-matrix.md)

返回 [索引](../README.md)

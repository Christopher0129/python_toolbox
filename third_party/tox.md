# tox

`tox` 适合在多个 Python 版本、依赖组合和命令下统一执行测试、lint 和构建流程。

## 安装

```bash
pip install tox
```

## 基本示例

```bash
tox
tox -e py311
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `tox` | 运行默认测试矩阵 |
| `tox -e py311` | 只运行指定环境 |
| `tox -r` | 重新创建环境 |

## 关联阅读

- [测试矩阵专题](../topics/test-matrix.md)
- [CI/CD 专题](../topics/ci-cd.md)
- [多环境执行专题](../topics/multi-environment-execution.md)

返回 [索引](../README.md)

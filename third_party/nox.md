# nox

`nox` 适合用 Python 代码声明测试和构建任务，方便把多环境执行逻辑写成可复用脚本。

## 安装

```bash
pip install nox
```

## 基本示例

```bash
nox
nox -s tests
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `@nox.session` | 声明一个执行会话 |
| `session.install(...)` | 安装依赖 |
| `session.run(...)` | 运行测试或命令 |

## 关联阅读

- [测试矩阵专题](../topics/test-matrix.md)
- [多环境执行专题](../topics/multi-environment-execution.md)
- [CI/CD 专题](../topics/ci-cd.md)

返回 [索引](../README.md)

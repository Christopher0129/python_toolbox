# 打包与发布专题

这个专题关注 Python 项目如何从源码走向可分发包或可部署版本。

## 关键主题

| 主题 | 说明 |
| --- | --- |
| 依赖管理 | `requirements.txt` 或 `pyproject.toml` |
| 入口脚本 | CLI 或服务启动入口 |
| 版本信息 | 明确版本号和变更 |
| 发布检查 | 测试、说明文档、依赖锁定 |

## 常见文件

```text
project/
  pyproject.toml
  README.md
  app/
  tests/
```

## 常见流程

1. 整理项目结构
2. 固定依赖
3. 跑测试
4. 准备 README 和版本说明
5. 再发布或部署

## 关联阅读

- [导入、包与虚拟环境](../basics/imports-venv.md)
- [configparser 与 tomllib](../stdlib/configparser_tomllib.md)
- [pytest](../third_party/pytest.md)
- [项目结构专题](./project-structure.md)
- [Python 包管理专题](./python-package-management.md)
- [依赖治理专题](./dependency-governance.md)
- [uv](../third_party/uv.md)
- [Poetry](../third_party/poetry.md)

返回 [索引](../README.md)

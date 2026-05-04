# Python 包管理专题

这个专题关注 Python 项目如何管理解释器、虚拟环境、依赖声明、锁文件和运行入口。

## 适用场景

- 团队项目需要统一开发环境
- 本地、CI、生产环境要复现相同依赖
- 同时需要管理脚本、服务和库发布

## 常见主题

- `requirements.txt` 和 `pyproject.toml`
- 虚拟环境与解释器选择
- 锁文件和可复现安装
- 本地运行命令与脚本入口
- 构建后端与发布流程

## 设计要点

- 小项目可以从 `requirements.txt` 起步，但中大型项目更适合统一到 `pyproject.toml`
- 锁文件是协作和发布的一部分，不只是本地缓存
- 工具选择要考虑团队一致性，避免每个项目一套
- 依赖安装、测试运行和发布命令最好形成固定约定

## 关联阅读

- [uv](../third_party/uv.md)
- [Poetry](../third_party/poetry.md)
- [PDM](../third_party/pdm.md)
- [Hatch](../third_party/hatch.md)
- [打包与发布专题](./packaging-release.md)

返回 [索引](../README.md)

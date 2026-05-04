# 项目结构专题

会写单文件脚本之后，下一步通常是把代码整理成可维护项目。这个专题关注目录划分、配置文件、测试位置和依赖管理的基本思路。

## 一个常见的项目结构

```text
project/
  app/
    __init__.py
    main.py
    service.py
    models.py
    utils.py
  tests/
    test_main.py
  requirements.txt
  README.md
```

## 目录职责建议

| 目录 / 文件 | 作用 |
| --- | --- |
| `app/` | 核心业务代码 |
| `tests/` | 测试用例 |
| `README.md` | 项目说明、启动方式 |
| `requirements.txt` 或 `pyproject.toml` | 依赖管理 |
| `.env` / `config.json` | 配置来源 |

## 代码拆分建议

- `main.py`：入口层，接命令或请求
- `service.py`：业务逻辑
- `models.py`：数据结构和模型
- `utils.py`：复用性强的小工具
- `storage.py`：文件、数据库、外部接口访问

## 测试放哪里

推荐把测试与业务分离，放在 `tests/`。

```text
tests/
  test_service.py
  test_utils.py
```

## 配置管理建议

- 少量配置可先用 `json`、环境变量或 `.env`
- 不要把密钥硬编码进代码
- 配置读取逻辑集中到一处，避免到处散落

## 依赖管理建议

- 小项目可以先用 `requirements.txt`
- 项目变大后，可以转向 `pyproject.toml`
- 第三方库只引入当前确实需要的部分
- 多包项目要先定义共享边界，再扩目录层级

## 常见问题

- 把脚本、测试、数据文件都堆在根目录，后续会很快失控
- 工具函数到处复制，说明公共模块抽取不够
- 入口逻辑和业务逻辑写在一起，导致难测

## 关联阅读

- [函数与模块组织](../basics/functions-modules.md)
- [pytest](../third_party/pytest.md)
- [logging](../stdlib/logging.md)
- [Flask 入门](../frameworks/flask.md)
- [FastAPI 入门](../frameworks/fastapi.md)
- [Python 包管理专题](./python-package-management.md)
- [Monorepo 与多包项目专题](./monorepo-multipackage.md)
- [开发环境热重载专题](./dev-reload-workflows.md)

返回 [索引](../README.md)

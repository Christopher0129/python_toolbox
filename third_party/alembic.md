# Alembic

`Alembic` 是 SQLAlchemy 生态里的数据库迁移工具，适合管理表结构演进。

## 安装

```bash
pip install alembic sqlalchemy
```

## 它解决什么问题

当数据库结构会持续变化时，不能每次都手动改表。`Alembic` 用迁移脚本记录“这次改了什么”，方便多人协作和环境同步。

## 常见命令

| 命令 | 用途 |
| --- | --- |
| `alembic init migrations` | 初始化迁移目录 |
| `alembic revision -m "create user table"` | 创建迁移脚本 |
| `alembic upgrade head` | 升级到最新版本 |
| `alembic downgrade -1` | 回退一个版本 |

## 典型流程

1. 先定义或修改 SQLAlchemy 模型
2. 生成迁移脚本
3. 检查脚本是否正确
4. 执行 `upgrade`

## 使用建议

- 不要把迁移脚本当黑盒，生成后要检查
- 生产库升级前要先备份并评估影响
- 团队协作时，迁移文件要进入版本控制

## 关联阅读

- [SQLAlchemy 2.x 基础](../database/sqlalchemy.md)
- [sqlite3](../stdlib/sqlite3.md)
- [项目结构专题](../topics/project-structure.md)

返回 [索引](../README.md)

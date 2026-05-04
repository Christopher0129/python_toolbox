# 部署与运维专题

这个专题关注 Python 项目上线之后的基本运行保障：日志、配置、进程、目录、备份和故障排查。

## 核心关注点

| 主题 | 说明 |
| --- | --- |
| 配置 | 环境变量和配置文件分离 |
| 日志 | 结构清晰，可追踪错误 |
| 进程 | 服务启动、重启、退出码 |
| 文件 | 日志目录、数据目录、临时目录 |
| 备份 | 配置和数据的归档 |

## 常用模块

- `logging`
- `subprocess`
- `os`
- `pathlib`
- `tempfile`
- `shutil`

## 关联阅读

- [logging](../stdlib/logging.md)
- [subprocess](../stdlib/subprocess.md)
- [文件处理专题](./file-processing.md)
- [性能与调试专题](./performance-debugging.md)
- [备份与归档专题](./backup-archiving.md)

返回 [索引](../README.md)

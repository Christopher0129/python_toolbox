# watchfiles

`watchfiles` 适合监听文件变化并触发热重载、自动构建或开发态任务。

## 安装

```bash
pip install watchfiles
```

## 基本示例

```python
from watchfiles import watch

for changes in watch("app"):
    print(changes)
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `watch(...)` | 监听目录变化 |
| `run_process(...)` | 变化后重启进程 |
| `awatch(...)` | 异步监听文件变化 |

## 关联阅读

- [开发环境热重载专题](../topics/dev-reload-workflows.md)
- [命令行自动化专题](../topics/automation-cli.md)
- [项目结构专题](../topics/project-structure.md)

返回 [索引](../README.md)

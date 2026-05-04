# psutil

`psutil` 适合读取进程、CPU、内存、磁盘和网络信息，常用于 worker 运行观测和本机诊断。

## 安装

```bash
pip install psutil
```

## 基本示例

```python
import psutil

cpu = psutil.cpu_percent(interval=1)
mem = psutil.virtual_memory()
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `cpu_percent(...)` | 查看 CPU 使用率 |
| `virtual_memory()` | 查看内存信息 |
| `Process(...)` | 读取单个进程状态 |

## 关联阅读

- [Worker 运行治理专题](../topics/worker-runtime-operations.md)
- [部署与运维专题](../topics/deployment-operations.md)
- [性能与调试专题](../topics/performance-debugging.md)

返回 [索引](../README.md)

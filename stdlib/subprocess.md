# subprocess 模块

`subprocess` 用于启动系统命令和外部程序，是 Python 脚本与系统工具协作的核心模块。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `subprocess.run(args, ...)` | 执行命令并等待完成 | `subprocess.run(["python", "--version"])` |
| `check=True` | 非零退出码抛异常 | `subprocess.run(..., check=True)` |
| `capture_output=True` | 捕获标准输出和标准错误 | `subprocess.run(..., capture_output=True)` |
| `text=True` | 以文本方式处理输出 | `subprocess.run(..., text=True)` |
| `timeout=10` | 超时控制 | `subprocess.run(..., timeout=10)` |
| `subprocess.Popen(args, ...)` | 启动长时子进程 | `subprocess.Popen(["ping", "127.0.0.1"])` |
| `proc.communicate()` | 与子进程收发数据 | `stdout, stderr = proc.communicate()` |

## 示例

```python
import subprocess

result = subprocess.run(
    ["python", "--version"],
    check=True,
    text=True,
    capture_output=True,
)
print(result.stdout.strip())
```

## 推荐写法

- 参数优先传列表，不要手工拼命令字符串
- 外部命令常加 `check=True`
- 需要读取输出时加 `capture_output=True, text=True`

## 提醒

- `shell=True` 会增加安全风险，除非明确需要 shell 特性
- Windows 和 Linux 命令差异较大，跨平台脚本要注意兼容性

返回 [索引](../README.md)

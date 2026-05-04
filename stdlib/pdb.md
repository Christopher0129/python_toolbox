# pdb 模块

`pdb` 是标准库内置调试器，适合在命令行里断点、单步、查看变量和调用栈。

## 常用入口

| 入口 | 说明 | 示例 |
| --- | --- | --- |
| `breakpoint()` | Python 3.7+ 推荐断点写法 | `breakpoint()` |
| `pdb.set_trace()` | 手动进入调试器 | `pdb.set_trace()` |
| `python -m pdb app.py` | 直接用调试器启动脚本 | `python -m pdb app.py` |

## 常用命令

| 命令 | 说明 |
| --- | --- |
| `n` | 下一行 |
| `s` | 进入函数 |
| `c` | 继续运行 |
| `l` | 查看附近源码 |
| `p expr` | 打印表达式 |
| `pp expr` | 格式化打印 |
| `b 20` | 在第 20 行打断点 |
| `q` | 退出调试 |

## 示例

```python
import pdb

def divide(a, b):
    pdb.set_trace()
    return a / b

print(divide(10, 2))
```

## 提醒

- 临时代码调试结束后记得删除断点
- 新代码更推荐用 `breakpoint()`，可读性更好

返回 [索引](../README.md)

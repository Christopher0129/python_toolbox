# datetime 模块

`datetime` 处理时间戳、日期格式化、日期加减、字符串和时间对象互转。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `datetime.now()` | 当前本地时间 | `datetime.now()` |
| `datetime.today()` | 当前日期时间 | `datetime.today()` |
| `datetime.strptime(text, fmt)` | 字符串转时间 | `datetime.strptime("2026-05-04", "%Y-%m-%d")` |
| `dt.strftime(fmt)` | 时间转字符串 | `dt.strftime("%Y-%m-%d %H:%M:%S")` |
| `timedelta(days=1)` | 时间增减 | `dt + timedelta(days=7)` |
| `date.today()` | 当前日期 | `date.today()` |

## 示例

```python
from datetime import datetime, timedelta

now = datetime.now()
next_week = now + timedelta(days=7)

print(now.strftime("%Y-%m-%d %H:%M:%S"))
print(next_week.strftime("%Y-%m-%d"))
```

## 常见格式串

| 格式 | 含义 |
| --- | --- |
| `%Y` | 四位年份 |
| `%m` | 两位月份 |
| `%d` | 两位日期 |
| `%H` | 24 小时制小时 |
| `%M` | 分钟 |
| `%S` | 秒 |

## 提醒

- `datetime` 和 `date` 是不同类型。
- 做时间差计算时优先使用 `timedelta`，不要手工拆字符串。

返回 [索引](../README.md)

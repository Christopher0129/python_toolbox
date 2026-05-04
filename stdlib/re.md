# re 模块

`re` 用于文本搜索、提取、替换和格式校验。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `re.search(pattern, text)` | 搜索首个匹配 | `re.search(r"\\d+", text)` |
| `re.match(pattern, text)` | 从开头匹配 | `re.match(r"abc", text)` |
| `re.fullmatch(pattern, text)` | 完整匹配整串 | `re.fullmatch(r"\\d{11}", phone)` |
| `re.findall(pattern, text)` | 返回全部匹配结果 | `re.findall(r"\\d+", text)` |
| `re.finditer(pattern, text)` | 返回匹配迭代器 | `for m in re.finditer(...):` |
| `re.sub(pattern, repl, text)` | 替换文本 | `re.sub(r"\\s+", " ", text)` |
| `re.compile(pattern)` | 预编译正则 | `pat = re.compile(r"\\w+")` |

## 常见元字符

| 写法 | 含义 |
| --- | --- |
| `\\d` | 数字 |
| `\\w` | 字母数字下划线 |
| `\\s` | 空白字符 |
| `.` | 任意字符（默认不含换行） |
| `*` | 重复 0 次或多次 |
| `+` | 重复 1 次或多次 |
| `?` | 重复 0 次或 1 次 |
| `^` / `$` | 开头 / 结尾 |

## 示例

```python
import re

text = "订单号: A123, 金额: 99"
numbers = re.findall(r"\d+", text)
print(numbers)
```

## 提醒

- 复杂正则建议使用原始字符串：`r"\d+"`
- 校验整串时优先用 `fullmatch()`，比 `match()` 更稳

返回 [索引](../README.md)

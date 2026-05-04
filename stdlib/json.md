# json 模块

`json` 适合接口数据、配置文件和普通字典列表的序列化与反序列化。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `json.load(fp)` | 从文件读取 JSON | `data = json.load(f)` |
| `json.loads(text)` | 从字符串解析 JSON | `obj = json.loads(text)` |
| `json.dump(obj, fp, ensure_ascii=False, indent=2)` | 写入 JSON 文件 | `json.dump(data, f, ensure_ascii=False, indent=2)` |
| `json.dumps(obj, ensure_ascii=False)` | 转为 JSON 字符串 | `json.dumps(data, ensure_ascii=False)` |

## 示例

```python
import json

user = {"name": "Tom", "age": 18}

with open("user.json", "w", encoding="utf-8") as f:
    json.dump(user, f, ensure_ascii=False, indent=2)

text = '{"ok": true, "count": 3}'
data = json.loads(text)
print(data["count"])
```

## 常见参数

- `ensure_ascii=False`：保留中文，不转义成 `\uXXXX`
- `indent=2`：格式化输出，便于查看和版本管理
- `sort_keys=True`：按键排序，方便比较差异

## 提醒

- JSON 只支持基础数据类型，不支持直接存储自定义对象
- 处理日期时间对象时，通常需要先自行转成字符串

返回 [索引](../README.md)

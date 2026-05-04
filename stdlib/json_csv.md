# json 与 csv

`json` 适合接口数据、配置文件、对象序列化；`csv` 适合二维表格文本数据。

## `json` 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `json.load(fp)` | 从文件读取 JSON | `json.load(f)` |
| `json.loads(s)` | 从字符串解析 JSON | `json.loads(text)` |
| `json.dump(obj, fp, ensure_ascii=False, indent=2)` | 写入文件 | `json.dump(data, f, ensure_ascii=False, indent=2)` |
| `json.dumps(obj, ensure_ascii=False)` | 转成字符串 | `json.dumps(data, ensure_ascii=False)` |

## `csv` 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `csv.reader(fp)` | 逐行读列表 | `for row in csv.reader(f): ...` |
| `csv.DictReader(fp)` | 逐行读字典 | `for row in csv.DictReader(f): ...` |
| `csv.writer(fp)` | 逐行写列表 | `writer.writerow(["name", "age"])` |
| `csv.DictWriter(fp, fieldnames=...)` | 逐行写字典 | `writer.writerow({"name": "Tom", "age": 18})` |

## JSON 示例

```python
import json

data = {"name": "Tom", "age": 18}
with open("user.json", "w", encoding="utf-8") as f:
    json.dump(data, f, ensure_ascii=False, indent=2)
```

## CSV 示例

```python
import csv

with open("users.csv", "w", newline="", encoding="utf-8") as f:
    writer = csv.DictWriter(f, fieldnames=["name", "age"])
    writer.writeheader()
    writer.writerow({"name": "Tom", "age": 18})
```

## 易错点

- Windows 写 CSV 时建议带 `newline=""`
- 中文 JSON 输出建议 `ensure_ascii=False`

返回 [索引](../README.md)

# csv 模块

`csv` 用于读写逗号分隔表格数据，适合和 Excel、运营表、导出报表互相交换数据。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `csv.reader(fp)` | 按行读取列表 | `for row in csv.reader(f): ...` |
| `csv.DictReader(fp)` | 按行读取字典 | `for row in csv.DictReader(f): ...` |
| `csv.writer(fp)` | 按行写列表 | `writer.writerow(["name", "age"])` |
| `csv.DictWriter(fp, fieldnames=...)` | 按字段写字典 | `writer = csv.DictWriter(...)` |
| `writer.writerow(row)` | 写一行 | `writer.writerow(["Tom", 18])` |
| `writer.writerows(rows)` | 写多行 | `writer.writerows(data)` |

## 读取示例

```python
import csv

with open("users.csv", "r", encoding="utf-8") as f:
    for row in csv.DictReader(f):
        print(row["name"], row["age"])
```

## 写入示例

```python
import csv

with open("users.csv", "w", newline="", encoding="utf-8") as f:
    writer = csv.DictWriter(f, fieldnames=["name", "age"])
    writer.writeheader()
    writer.writerow({"name": "Tom", "age": 18})
```

## 提醒

- Windows 写 CSV 时建议加 `newline=""`
- 表头字段名不一致时，`DictWriter` 写入会出错，要先对齐列名

返回 [索引](../README.md)

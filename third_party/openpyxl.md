# openpyxl

`openpyxl` 用于读写 `.xlsx` Excel 文件，适合报表导出、表格清洗、批量改单元格和样式处理。

## 安装

```bash
pip install openpyxl
```

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `Workbook()` | 创建工作簿 | `wb = Workbook()` |
| `load_workbook(path)` | 打开已有 Excel | `wb = load_workbook("demo.xlsx")` |
| `wb.active` | 当前活动工作表 | `ws = wb.active` |
| `wb.create_sheet(name)` | 新建工作表 | `wb.create_sheet("Report")` |
| `ws["A1"] = value` | 写单元格 | `ws["A1"] = "name"` |
| `ws.cell(row, column)` | 按行列访问单元格 | `ws.cell(1, 1).value` |
| `ws.append(row)` | 追加一行 | `ws.append(["Tom", 18])` |
| `wb.save(path)` | 保存文件 | `wb.save("out.xlsx")` |

## 最小示例

```python
from openpyxl import Workbook

wb = Workbook()
ws = wb.active
ws.title = "Users"
ws.append(["name", "age"])
ws.append(["Tom", 18])
ws.append(["Amy", 20])
wb.save("users.xlsx")
```

## 读取示例

```python
from openpyxl import load_workbook

wb = load_workbook("users.xlsx")
ws = wb.active

for row in ws.iter_rows(values_only=True):
    print(row)
```

## 常见用途

- 导出 Excel 报表
- 读取运营表或名单表
- 修改指定单元格、工作表名称、样式

## 提醒

- `openpyxl` 主要处理 `.xlsx`，不适合旧 `.xls`
- 大数据量表格处理时，`pandas` 和 `openpyxl` 常配合使用

返回 [索引](../README.md)

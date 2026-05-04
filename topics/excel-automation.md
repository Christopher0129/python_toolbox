# Excel 自动化专题

这个专题把 Python 处理 Excel 的常见场景串起来：读写表格、批量填充、样式和数据清洗。

## 先学哪些库

| 库 | 作用 | 推荐程度 |
| --- | --- | --- |
| `openpyxl` | 读写 Excel 文件 | 必学 |
| `pandas` | 表格分析和导入导出 | 高频 |

## 常见任务

| 任务 | 常用组合 |
| --- | --- |
| 读取现有 Excel | `openpyxl.load_workbook()` |
| 清洗表格后再导出 | `pandas` + `to_excel()` |
| 批量填充工作表 | `openpyxl` |
| 生成报表 | `pandas` + `openpyxl` |

## 关联阅读

- [openpyxl](../third_party/openpyxl.md)
- [pandas](../third_party/pandas.md)
- [数据清洗专题](./data-cleaning.md)
- [数据可视化专题](./data-visualization.md)

返回 [索引](../README.md)

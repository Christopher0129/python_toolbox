# pandas

`pandas` 适合表格数据分析、清洗、筛选、聚合和导入导出。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `pd.read_csv(path)` | 读取 CSV | `pd.read_csv("users.csv")` |
| `pd.read_excel(path)` | 读取 Excel | `pd.read_excel("users.xlsx")` |
| `DataFrame.head(n)` | 查看前几行 | `df.head()` |
| `DataFrame.info()` | 查看字段概况 | `df.info()` |
| `DataFrame.describe()` | 数值统计摘要 | `df.describe()` |
| `DataFrame.loc[...]` | 按标签选取 | `df.loc[df["age"] > 18]` |
| `DataFrame.iloc[...]` | 按位置选取 | `df.iloc[:5, :2]` |
| `DataFrame.groupby(cols)` | 分组聚合 | `df.groupby("city")["salary"].mean()` |
| `pd.merge(left, right, on=...)` | 表连接 | `pd.merge(a, b, on="id")` |
| `DataFrame.fillna(value)` | 缺失值填充 | `df.fillna(0)` |

## 示例

```python
import pandas as pd

df = pd.read_csv("users.csv")
print(df.head())
adults = df.loc[df["age"] >= 18, ["name", "age"]]
print(adults)
```

## 常见工作流

1. `read_csv()` / `read_excel()`
2. `head()` / `info()` 了解数据
3. `loc[]` / `groupby()` / `merge()` 清洗和分析
4. `to_csv()` / `to_excel()` 导出结果

## 提醒

- 使用前安装：`pip install pandas`
- 处理大数据量时，要注意内存占用和字段类型

返回 [索引](../README.md)

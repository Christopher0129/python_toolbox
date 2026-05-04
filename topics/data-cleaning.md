# 数据清洗专题

这个专题关注日常数据处理链路：读取原始数据、识别脏数据、转换字段、去重、聚合和导出结果。

## 先学哪些模块和库

| 模块 / 库 | 作用 | 推荐程度 |
| --- | --- | --- |
| `pandas` | 表格数据清洗主力 | 必学 |
| `csv` | 轻量 CSV 读写 | 高频 |
| `json` | JSON 数据清洗和交换 | 高频 |
| `re` | 文本字段提取与替换 | 高频 |
| `datetime` | 时间字段解析 | 高频 |
| `collections.Counter` | 分类计数和频率统计 | 常用 |

## 典型工作流

### 1. 读取原始数据

```python
import pandas as pd

df = pd.read_csv("orders.csv")
print(df.head())
```

### 2. 处理缺失值和类型

```python
df["price"] = df["price"].fillna(0).astype(float)
df["created_at"] = pd.to_datetime(df["created_at"])
```

### 3. 去重和标准化

```python
df["city"] = df["city"].str.strip().str.lower()
df = df.drop_duplicates(subset=["order_id"])
```

### 4. 分组聚合

```python
summary = df.groupby("city")["price"].sum().reset_index()
print(summary)
```

### 5. 导出结果

```python
summary.to_csv("summary.csv", index=False)
```

## 常见脏数据问题

| 问题 | 常用处理方式 |
| --- | --- |
| 缺失值 | `fillna()`、删除、回填默认值 |
| 重复行 | `drop_duplicates()` |
| 空格和大小写不一致 | `str.strip()`、`str.lower()` |
| 日期格式混乱 | `pd.to_datetime()` |
| 金额字段是字符串 | 去符号后转数值 |

## 实战建议

- 先保留原始数据，再生成清洗结果
- 每一步清洗都要能说明规则
- 涉及金额、时间、主键字段时要重点检查

## 关联阅读

- [pandas](../third_party/pandas.md)
- [csv](../stdlib/csv.md)
- [json](../stdlib/json.md)
- [re](../stdlib/re.md)
- [数据可视化专题](./data-visualization.md)

返回 [索引](../README.md)

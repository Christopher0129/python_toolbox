# deltalake

`deltalake` 适合在 Python 中读写 Delta Lake 表，常见于数据湖和 lakehouse 场景。

## 安装

```bash
pip install deltalake
```

## 基本示例

```python
from deltalake import DeltaTable

dt = DeltaTable("data/delta/orders")
df = dt.to_pandas()
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `DeltaTable(...)` | 打开 Delta 表 |
| `to_pandas()` | 读取为 DataFrame |
| `write_deltalake(...)` | 写入 Delta 表 |

## 关联阅读

- [Delta Lake 专题](../topics/delta-lake.md)
- [数据湖存储专题](../topics/data-lake-storage.md)
- [Lakehouse 表格式专题](../topics/table-formats-lakehouse.md)

返回 [索引](../README.md)

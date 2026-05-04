# clickhouse-connect

`clickhouse-connect` 适合在 Python 中访问 ClickHouse，常用于分析型查询、日志查询和宽表聚合。

## 安装

```bash
pip install clickhouse-connect
```

## 基本示例

```python
import clickhouse_connect

client = clickhouse_connect.get_client(host="127.0.0.1", port=8123)
rows = client.query("select 1").result_rows
print(rows)
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `get_client(...)` | 创建 ClickHouse 客户端 |
| `query(...)` | 执行查询并获取结果 |
| `insert(...)` | 批量写入数据 |

## 关联阅读

- [ClickHouse 分析专题](../topics/clickhouse-analytics.md)
- [列式数据处理专题](../topics/columnar-data-processing.md)
- [分析工程专题](../topics/analytics-engineering.md)

返回 [索引](../README.md)

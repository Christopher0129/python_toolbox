# DuckDB

`DuckDB` 适合本地分析型 SQL、嵌入式 OLAP 和数据文件上的快速查询。

## 安装

```bash
pip install duckdb
```

## 基本示例

```python
import duckdb

duckdb.sql("SELECT 42").show()
```

## 持久化连接示例

```python
import duckdb

con = duckdb.connect("file.db")
con.sql("CREATE TABLE IF NOT EXISTS test (i INTEGER)")
con.sql("INSERT INTO test VALUES (42)")
print(con.sql("SELECT * FROM test").fetchall())
con.close()
```

## 适用场景

- 本地 SQL 分析
- CSV/Parquet 快速探索
- 与 Python 数据处理脚本组合

## 注意事项

- `duckdb.sql()` 使用全局内存连接
- 多线程场景优先每个线程单独连接

## 关联阅读

- [sqlite3](../stdlib/sqlite3.md)
- [Polars](./polars.md)
- [列式数据处理专题](../topics/columnar-data-processing.md)

返回 [索引](../README.md)

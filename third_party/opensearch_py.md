# opensearch-py

`opensearch-py` 适合连接 OpenSearch 集群，做日志检索、分析搜索和混合检索相关工作。

## 安装

```bash
pip install opensearch-py
```

## 基本示例

```python
from opensearchpy import OpenSearch

client = OpenSearch(hosts=[{"host": "127.0.0.1", "port": 9200}])
resp = client.search(index="logs-*", body={"query": {"match_all": {}}})
print(resp["hits"]["hits"])
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `OpenSearch(...)` | 创建客户端 |
| `search(...)` | 执行 DSL 查询 |
| `bulk(...)` | 批量写入索引 |

## 关联阅读

- [搜索系统专题](../topics/search-systems.md)
- [可观测性专题](../topics/observability.md)
- [遥测与链路追踪专题](../topics/telemetry-tracing.md)

返回 [索引](../README.md)

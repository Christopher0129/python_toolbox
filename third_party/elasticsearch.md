# Elasticsearch

`elasticsearch` 适合在 Python 中操作全文检索、倒排索引和聚合查询。

## 安装

```bash
pip install elasticsearch
```

## 基本示例

```python
from elasticsearch import Elasticsearch

es = Elasticsearch("http://127.0.0.1:9200")
resp = es.search(index="articles", query={"match": {"title": "python"}})
print(resp["hits"]["hits"])
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `Elasticsearch(...)` | 创建客户端 |
| `index(...)` | 写入文档 |
| `search(...)` | 执行查询和聚合 |

## 关联阅读

- [搜索系统专题](../topics/search-systems.md)
- [向量检索专题](../topics/vector-retrieval.md)
- [数据管道专题](../topics/data-pipelines.md)

返回 [索引](../README.md)

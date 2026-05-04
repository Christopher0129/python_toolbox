# sentence-transformers

`sentence-transformers` 适合生成文本向量、做相似度匹配、语义检索和重排，是向量检索应用的高频入口。

## 安装

```bash
pip install sentence-transformers
```

## 基本示例

```python
from sentence_transformers import SentenceTransformer

model = SentenceTransformer("BAAI/bge-small-zh-v1.5")
embeddings = model.encode(["Python 知识库", "向量检索"])
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `SentenceTransformer(...)` | 加载嵌入模型 |
| `model.encode(...)` | 生成向量 |
| `CrossEncoder(...)` | 做查询与候选重排 |

## 关联阅读

- [向量检索专题](../topics/vector-retrieval.md)
- [Embedding 与 Rerank 专题](../topics/embeddings-reranking.md)
- [RAG 流水线专题](../topics/rag-pipelines.md)

返回 [索引](../README.md)

# Embedding 与 Rerank 专题

这个专题关注向量检索里“先召回再重排”的核心链路，而不只是一句 `top_k` 查询。

## 适用场景

- 语义搜索和知识库问答
- 多路召回后的结果融合与排序
- 需要提升首屏命中率的检索增强应用

## 常见主题

- embedding 模型选型
- chunk 粒度和 overlap
- ANN 召回与过滤条件
- cross-encoder rerank
- 混合检索与特征融合

## 设计要点

- 先定义评测集，再决定召回和重排策略
- 相似度分数不可直接跨模型比较
- 元数据过滤和权限过滤要在召回链路中前置考虑
- 重排通常更贵，应控制候选集合规模

## 关联阅读

- [向量检索专题](./vector-retrieval.md)
- [RAG 流水线专题](./rag-pipelines.md)
- [sentence-transformers](../third_party/sentence_transformers.md)
- [qdrant-client](../third_party/qdrant_client.md)

返回 [索引](../README.md)

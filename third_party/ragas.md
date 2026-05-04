# Ragas

`Ragas` 适合评估 RAG 系统的检索质量、回答质量和上下文利用情况。

## 安装

```bash
pip install ragas
```

## 基本示例

```python
from ragas import evaluate


result = evaluate(dataset, metrics=[])
print(result)
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `evaluate(...)` | 对评测数据集执行评估 |
| retrieval / answer 指标 | 分别看召回和回答质量 |
| 数据集驱动评测 | 对比不同检索和 prompt 策略 |

## 使用建议

- 指标要和业务目标一起解释，不能只看综合分
- 评测集需要按真实问题分布构建，不要只放“好答”的样本
- 适合放在 prompt、检索、重排和模型版本变更前后做对比

## 关联阅读

- [RAG 评测专题](../topics/rag-evaluation.md)
- [RAG 流水线专题](../topics/rag-pipelines.md)
- [Embedding 与 Rerank 专题](../topics/embeddings-reranking.md)
- [模型评估专题](../topics/ml-evaluation.md)

返回 [索引](../README.md)

# unstructured

`unstructured` 适合把 PDF、HTML、Office 文档拆成更细的语义块，用于检索、RAG 和文档治理。

## 安装

```bash
pip install unstructured
```

## 基本示例

```python
from unstructured.partition.pdf import partition_pdf

elements = partition_pdf(filename="contract.pdf")
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `partition_pdf(...)` | 解析 PDF 为结构化元素 |
| `partition_html(...)` | 解析 HTML 文档 |
| `chunk_by_title(...)` | 按标题或结构切块 |

## 适用场景

- RAG 文档切分
- 文档版式与结构识别
- 多格式知识入库前处理

## 关联阅读

- [文档抽取专题](../topics/document-extraction.md)
- [RAG 流水线专题](../topics/rag-pipelines.md)
- [PDF 与 OCR 专题](../topics/pdf-ocr-processing.md)

返回 [索引](../README.md)

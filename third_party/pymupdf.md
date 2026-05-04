# PyMuPDF

`PyMuPDF` 适合读取 PDF、提取文本、渲染页面图片和做文档切片处理。

## 安装

```bash
pip install pymupdf
```

## 基本示例

```python
import fitz

doc = fitz.open("demo.pdf")
text = doc[0].get_text()
```

## 关联阅读

- [PDF 与 OCR 专题](../topics/pdf-ocr-processing.md)
- [文件处理专题](../topics/file-processing.md)
- [RAG 流水线专题](../topics/rag-pipelines.md)

返回 [索引](../README.md)

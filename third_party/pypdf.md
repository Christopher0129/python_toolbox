# pypdf

`pypdf` 适合做轻量 PDF 读取、合并、拆分和表单处理，依赖简单，适合作为原生文本 PDF 的基础入口。

## 安装

```bash
pip install pypdf
```

## 基本示例

```python
from pypdf import PdfReader

reader = PdfReader("report.pdf")
text = reader.pages[0].extract_text()
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `PdfReader(...)` | 读取 PDF 文档 |
| `page.extract_text()` | 提取页面文字 |
| `PdfWriter()` | 合并、拆分、导出 PDF |

## 关联阅读

- [PDF 与 OCR 专题](../topics/pdf-ocr-processing.md)
- [文档抽取专题](../topics/document-extraction.md)
- [文件处理专题](../topics/file-processing.md)

返回 [索引](../README.md)

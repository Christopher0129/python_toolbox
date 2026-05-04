# PDF 与 OCR 专题

这个专题关注如何从 PDF、扫描件和图片文档里提取可用文本和结构信息。

## 适用场景

- 合同、发票、招标书、报告等文档批量入库
- 扫描件转文本和结构化字段抽取
- RAG 与文档搜索的数据前处理

## 常见主题

- 原生文本 PDF 提取
- 扫描件 OCR
- 页面渲染成图片
- 区域裁切和预处理
- 文档切片与检索

## 设计要点

- 原生文本 PDF 优先直接抽取，不要无差别先 OCR
- OCR 前要做旋转、裁边、二值化等基础清洗
- 要保存页码、标题、坐标和来源元数据
- 低置信度结果应进入人工复核或补抽链路

## 关联阅读

- [PyMuPDF](../third_party/pymupdf.md)
- [pypdf](../third_party/pypdf.md)
- [pytesseract](../third_party/pytesseract.md)
- [计算机视觉专题](./computer-vision.md)
- [RAG 流水线专题](./rag-pipelines.md)
- [文档抽取专题](./document-extraction.md)

返回 [索引](../README.md)

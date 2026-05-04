# 文档抽取专题

这个专题关注把 PDF、网页、Office 文档和扫描件转成可搜索、可清洗、可入库的结构化内容。

## 适用场景

- 构建文档知识库和检索系统
- 合同、发票、报告等半结构化文本抽取
- RAG 入库前的切块、清洗和元数据提取

## 常见主题

- 原生文本抽取与版式保留
- OCR 与图像预处理
- 表格、标题、段落结构识别
- 文档切块与元数据标注
- 清洗、去噪和重复检测

## 设计要点

- 优先识别“原生文本 PDF”还是“扫描 PDF”，决定走提取还是 OCR
- 切块粒度要服务于检索和问答，不是越小越好
- 页面号、标题层级、来源 URL 等元数据要和正文一起保存
- 文档解析失败和低置信度页要能落审计队列

## 关联阅读

- [PDF 与 OCR 专题](./pdf-ocr-processing.md)
- [RAG 流水线专题](./rag-pipelines.md)
- [PyMuPDF](../third_party/pymupdf.md)
- [pypdf](../third_party/pypdf.md)
- [unstructured](../third_party/unstructured.md)

返回 [索引](../README.md)

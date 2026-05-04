# pytesseract

`pytesseract` 适合在 Python 中调用 Tesseract OCR，提取图片或扫描 PDF 中的文字。

## 安装

```bash
pip install pytesseract
```

## 基本示例

```python
import pytesseract
from PIL import Image

text = pytesseract.image_to_string(Image.open("scan.png"), lang="eng")
```

## 关联阅读

- [PDF 与 OCR 专题](../topics/pdf-ocr-processing.md)
- [计算机视觉专题](../topics/computer-vision.md)
- [图像处理专题](../topics/image-processing.md)

返回 [索引](../README.md)

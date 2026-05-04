# Pillow

`Pillow` 适合处理图片读写、缩放、裁剪、格式转换和简单绘制。

## 安装

```bash
pip install pillow
```

## 基本示例

```python
from PIL import Image

img = Image.open("demo.jpg")
img = img.resize((300, 200))
img.save("demo_small.jpg")
```

## 常见能力

| 能力 | 示例 |
| --- | --- |
| 打开图片 | `Image.open(path)` |
| 改尺寸 | `img.resize((w, h))` |
| 裁剪 | `img.crop((x1, y1, x2, y2))` |
| 格式转换 | `img.save("a.png")` |

## 适用场景

- 批量缩略图生成
- 图片格式转换
- 简单水印和拼接

## 关联阅读

- [pathlib](../stdlib/pathlib.md)
- [文件处理专题](../topics/file-processing.md)
- [图像处理专题](../topics/image-processing.md)

返回 [索引](../README.md)

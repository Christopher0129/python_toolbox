# OpenCV

`OpenCV` 适合图像读写、基础视觉处理、视频帧处理和几何变换。

## 安装

```bash
pip install opencv-python
```

## 基本示例

```python
import cv2

image = cv2.imread("demo.jpg")
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```

## 关联阅读

- [计算机视觉专题](../topics/computer-vision.md)
- [图像处理专题](../topics/image-processing.md)
- [媒体处理专题](../topics/media-processing.md)

返回 [索引](../README.md)

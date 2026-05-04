# ffmpeg-python

`ffmpeg-python` 适合在 Python 中构造音视频转码、裁剪、拼接和抽帧流程。

## 安装

```bash
pip install ffmpeg-python
```

## 基本示例

```python
import ffmpeg

(
    ffmpeg
    .input("input.mp4")
    .output("output.mp3")
    .run()
)
```

## 关联阅读

- [媒体处理专题](../topics/media-processing.md)
- [图像处理专题](../topics/image-processing.md)
- [文件处理专题](../topics/file-processing.md)

返回 [索引](../README.md)

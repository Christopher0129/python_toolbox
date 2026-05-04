# ONNX Runtime

`ONNX Runtime` 适合在 Python 中高效运行 ONNX 模型，常用于模型推理加速和跨框架部署。

## 安装

```bash
pip install onnxruntime
```

## 基本示例

```python
import onnxruntime as ort

session = ort.InferenceSession("model.onnx")
```

## 关联阅读

- [推理优化专题](../topics/inference-optimization.md)
- [模型服务专题](../topics/model-serving.md)
- [传统机器学习专题](../topics/classical-ml.md)

返回 [索引](../README.md)

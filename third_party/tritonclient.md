# tritonclient

`tritonclient` 适合和 NVIDIA Triton Inference Server 通信，统一管理多模型、多框架推理服务。

## 安装

```bash
pip install tritonclient[http]
```

## 基本示例

```python
import tritonclient.http as httpclient

client = httpclient.InferenceServerClient(url="localhost:8000")
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `InferenceServerClient(...)` | 创建 Triton 客户端 |
| `InferInput(...)` | 组装输入张量 |
| `client.infer(...)` | 发送推理请求 |

## 关联阅读

- [Triton 推理服务专题](../topics/triton-inference-serving.md)
- [模型服务专题](../topics/model-serving.md)
- [推理优化专题](../topics/inference-optimization.md)

返回 [索引](../README.md)

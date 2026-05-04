# 推理优化专题

这个专题关注模型上线后如何降低延迟、提高吞吐并控制资源成本。

## 适用场景

- 在线推理接口的延迟治理
- 批量推理任务的成本优化
- 同时运行多个模型和版本的服务平台

## 常见主题

- 批量推理与动态 batching
- 模型格式转换
- ONNX / runtime 优化
- CPU / GPU 资源权衡
- 冷启动和模型加载策略

## 设计要点

- 先拆清模型计算、预处理、后处理和网络开销
- 优化前应先建立基线和压测方法
- 动态 batch 会提升吞吐，但可能拉高尾延迟
- 模型压缩、量化和格式转换要验证精度回归

## 关联阅读

- [ONNX Runtime](../third_party/onnxruntime.md)
- [模型服务专题](./model-serving.md)
- [性能基准专题](./benchmarking.md)
- [容量规划专题](./capacity-planning.md)
- [成本治理专题](./cost-governance.md)
- [Triton 推理服务专题](./triton-inference-serving.md)

返回 [索引](../README.md)

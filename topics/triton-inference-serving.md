# Triton 推理服务专题

这个专题关注用统一推理服务托管多模型、多框架和多版本，而不是每个模型单独起一个 Python 服务。

## 适用场景

- GPU 推理资源共享
- 多模型部署与 A/B 版本切换
- 需要动态 batch、并发调度和集中监控的推理平台

## 常见主题

- 模型仓库与版本目录
- HTTP / gRPC 推理入口
- dynamic batching 与并发实例
- ensemble pipeline
- 监控、限流和冷启动治理

## 设计要点

- 模型前后处理是否放在 Triton 外部，要按复用度和延迟预算决定
- 模型输入输出协议要稳定，否则客户端成本会快速扩散
- 线上要区分模型加载失败、超时、显存不足和业务空结果
- Triton 适合统一推理平面，不一定替代全部业务 API 层

## 关联阅读

- [模型服务专题](./model-serving.md)
- [推理优化专题](./inference-optimization.md)
- [gRPC 进阶专题](./grpc-advanced.md)
- [tritonclient](../third_party/tritonclient.md)

返回 [索引](../README.md)

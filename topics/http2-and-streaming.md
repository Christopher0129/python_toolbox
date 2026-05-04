# HTTP/2 与流式响应专题

这个专题关注现代服务里的多路复用、长连接、流式返回和服务器推送式交互。

## 适用场景

- 长连接接口
- 流式生成或日志推送
- 高并发内部服务调用

## 常见主题

- HTTP/2 多路复用
- header 压缩
- chunked / streaming response
- backpressure
- 超时和取消传播

## 设计要点

- 流式接口重点不只是“能流”，而是中途失败、取消和资源释放
- 连接复用、并发窗口和代理兼容性要一起考虑
- 生产环境要明确哪些层负责超时、重试和截断
- 客户端 SDK 应暴露可消费的流接口，而不是强制一次性收完

## 关联阅读

- [网络编程专题](./network-programming.md)
- [实时通信专题](./realtime-communication.md)
- [gRPC 进阶专题](./grpc-advanced.md)
- [背压与流控专题](./backpressure-and-flow-control.md)

返回 [索引](../README.md)

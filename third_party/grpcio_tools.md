# grpcio-tools

`grpcio-tools` 适合从 `.proto` 文件生成 Python gRPC stub 和消息类型代码。

## 安装

```bash
pip install grpcio grpcio-tools
```

## 基本示例

```bash
python -m grpc_tools.protoc -I. --python_out=. --grpc_python_out=. hello.proto
```

## 关联阅读

- [gRPC 进阶专题](../topics/grpc-advanced.md)
- [grpcio](./grpc.md)
- [API 开发专题](../topics/api-development.md)

返回 [索引](../README.md)

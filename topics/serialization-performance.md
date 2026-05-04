# 序列化性能专题

这个专题关注如何在高吞吐场景下减少 JSON 和消息编解码成本。

## 常见选择

| 工具 | 特点 |
| --- | --- |
| `json` | 标准库，通用 |
| `orjson` | 更快的 JSON |
| `msgspec` | 高性能且可强类型 |

## 适用场景

- 高频 API
- 日志事件流
- 队列消息体

## 关联阅读

- [json](../stdlib/json.md)
- [orjson](../third_party/orjson.md)
- [msgspec](../third_party/msgspec.md)

返回 [索引](../README.md)

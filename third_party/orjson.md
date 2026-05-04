# orjson

`orjson` 适合更快的 JSON 编码和解码，常用于高吞吐接口和数据交换。

## 安装

```bash
pip install orjson
```

## 基本示例

```python
import orjson

data = {"name": "Tom", "age": 18}
raw = orjson.dumps(data)
obj = orjson.loads(raw)
print(obj)
```

## 适用场景

- 高吞吐 JSON 接口
- 大量 JSON 序列化任务
- 性能敏感的日志或数据管道

## 关联阅读

- [json](../stdlib/json.md)
- [msgspec](./msgspec.md)
- [序列化性能专题](../topics/serialization-performance.md)

返回 [索引](../README.md)

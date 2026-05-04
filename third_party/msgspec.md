# msgspec

`msgspec` 适合高性能结构化序列化与反序列化，也支持 `Struct` 风格的数据定义。

## 安装

```bash
pip install msgspec
```

## 基本示例

```python
import msgspec


class User(msgspec.Struct):
    name: str
    age: int


raw = msgspec.json.encode(User("Tom", 18))
user = msgspec.json.decode(raw, type=User)
print(user)
```

## 适用场景

- 高性能 JSON 编解码
- 强类型消息结构
- 性能敏感的数据通道

## 关联阅读

- [orjson](./orjson.md)
- [序列化性能专题](../topics/serialization-performance.md)
- [typing 与 dataclasses](../stdlib/typing_dataclasses.md)

返回 [索引](../README.md)

# pickle 模块

`pickle` 用于把 Python 对象序列化到本地文件或字节串，适合缓存、离线中间结果和快速保存复杂对象。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `pickle.dump(obj, fp)` | 把对象写入文件 | `pickle.dump(data, f)` |
| `pickle.load(fp)` | 从文件读取对象 | `data = pickle.load(f)` |
| `pickle.dumps(obj)` | 转为字节串 | `blob = pickle.dumps(data)` |
| `pickle.loads(data)` | 从字节串恢复对象 | `obj = pickle.loads(blob)` |

## 示例

```python
import pickle

data = {"name": "Tom", "scores": [90, 88, 95]}

with open("cache.pkl", "wb") as f:
    pickle.dump(data, f)

with open("cache.pkl", "rb") as f:
    loaded = pickle.load(f)

print(loaded)
```

## 适用场景

- 本地缓存 Python 对象
- 保存中间训练结果或爬虫断点
- 快速持久化复杂嵌套结构

## 提醒

- `pickle` 不是跨语言格式，也不适合作为公开交换格式
- 不要反序列化不可信来源的 `pickle` 数据，存在安全风险

返回 [索引](../README.md)

# copy 与 pprint

`copy` 适合处理对象复制，`pprint` 适合更清晰地打印复杂数据结构。

## `copy` 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `copy.copy(obj)` | 浅拷贝 | `copy.copy(data)` |
| `copy.deepcopy(obj)` | 深拷贝 | `copy.deepcopy(data)` |

## 浅拷贝与深拷贝

```python
import copy

data = {"nums": [1, 2]}
shallow = copy.copy(data)
deep = copy.deepcopy(data)

data["nums"].append(3)
print(shallow["nums"])  # [1, 2, 3]
print(deep["nums"])     # [1, 2]
```

## `pprint` 常用 API

| API | 说明 |
| --- | --- |
| `pprint(obj)` | 直接格式化输出 |
| `pformat(obj)` | 返回格式化后的字符串 |

```python
from pprint import pprint

users = [{"name": "Tom", "skills": ["python", "sql"]}]
pprint(users)
```

## 适用场景

- 调试嵌套字典和列表
- 复制配置模板后再局部修改
- 测试里构造复杂样例数据

## 实战建议

- 对嵌套可变对象，只用浅拷贝通常不够
- `pformat()` 适合和日志结合

## 关联阅读

- [typing 与 dataclasses](./typing_dataclasses.md)
- [logging](./logging.md)
- [traceback](./traceback.md)

返回 [索引](../README.md)

# typing 与 dataclasses

`typing` 提升可读性和静态检查能力，`dataclasses` 适合表达结构化数据对象。

## `typing` 常用类型

| 类型 | 说明 | 示例 |
| --- | --- | --- |
| `Any` | 任意类型 | `value: Any` |
| `Optional[T]` | 可能为 `None` | `name: Optional[str]` |
| `list[T]` / `dict[K, V]` | 泛型容器 | `users: list[str]` |
| `Iterable[T]` | 可迭代对象 | `items: Iterable[int]` |
| `Callable[[A], B]` | 可调用对象 | `func: Callable[[int], str]` |
| `Literal[...]` | 限定字面量值 | `mode: Literal["r", "w"]` |

## `dataclasses` 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `@dataclass` | 自动生成初始化和表示方法 | `@dataclass` |
| `field(default=...)` | 配置默认值 | `tags: list[str] = field(default_factory=list)` |
| `asdict(obj)` | 转换为字典 | `asdict(user)` |

## 示例

```python
from dataclasses import asdict, dataclass, field

@dataclass
class User:
    name: str
    age: int
    tags: list[str] = field(default_factory=list)

user = User(name="Tom", age=18)
print(asdict(user))
```

## 提醒

- Python 3.10+ 可直接写 `str | None`，等价于 `Optional[str]`
- 可变默认值不要直接写 `[]`，应使用 `field(default_factory=list)`

返回 [索引](../README.md)

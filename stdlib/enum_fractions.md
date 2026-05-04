# enum 与 fractions

`enum` 适合定义有限状态集合，`fractions` 适合精确表示有理数。

## `enum` 常用写法

```python
from enum import Enum


class Status(Enum):
    PENDING = "pending"
    DONE = "done"


print(Status.PENDING.value)
```

适合：

- 固定状态码
- 固定操作模式
- 避免到处散落魔法字符串

## `fractions` 常用 API

| API | 说明 |
| --- | --- |
| `Fraction(a, b)` | 创建分数 |
| `Fraction("3/4")` | 从字符串创建 |
| `limit_denominator()` | 求近似分数 |

```python
from fractions import Fraction

x = Fraction(1, 3)
y = Fraction(1, 6)
print(x + y)
```

## 适用场景

- 比率计算
- 精确分数运算
- 配置状态枚举化

## 实战建议

- 状态集合优先用 `Enum`，可读性明显更好
- 金额场景优先 `decimal`，不是 `fractions`

## 关联阅读

- [decimal](./decimal.md)
- [typing 与 dataclasses](./typing_dataclasses.md)
- [项目结构专题](../topics/project-structure.md)

返回 [索引](../README.md)

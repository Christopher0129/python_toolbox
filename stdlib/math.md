# math 模块

`math` 提供数学函数和常量，适合做数值计算、取整、对数、三角函数等操作。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `math.sqrt(x)` | 开平方 | `math.sqrt(16)` |
| `math.pow(x, y)` | 幂运算，返回浮点数 | `math.pow(2, 3)` |
| `math.ceil(x)` | 向上取整 | `math.ceil(3.2)` |
| `math.floor(x)` | 向下取整 | `math.floor(3.8)` |
| `math.fabs(x)` | 浮点绝对值 | `math.fabs(-3.14)` |
| `math.log(x, base)` | 对数 | `math.log(8, 2)` |
| `math.sin(x)` / `math.cos(x)` | 三角函数 | `math.sin(math.pi / 2)` |
| `math.isclose(a, b)` | 浮点近似比较 | `math.isclose(0.1 + 0.2, 0.3)` |

## 常用常量

| 常量 | 说明 |
| --- | --- |
| `math.pi` | 圆周率 |
| `math.e` | 自然常数 |
| `math.tau` | `2 * pi` |

## 示例

```python
import math

radius = 3
area = math.pi * radius ** 2
print(area)
print(math.ceil(3.14), math.floor(3.14))
print(math.isclose(0.1 + 0.2, 0.3))
```

## 提醒

- 幂运算通常也可直接写 `x ** y`
- 浮点数比较不要直接用 `==`，优先考虑 `math.isclose()`

返回 [索引](../README.md)

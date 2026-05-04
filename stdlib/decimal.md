# decimal 模块

`decimal` 适合金额、利率、计费等需要高精度十进制计算的场景，比二进制浮点更可靠。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `Decimal("1.23")` | 创建十进制数 | `Decimal("0.1")` |
| `quantize(exp)` | 按指定精度舍入 | `price.quantize(Decimal("0.01"))` |
| `getcontext()` | 读取或修改全局上下文 | `getcontext().prec = 28` |
| `ROUND_HALF_UP` | 常见四舍五入规则 | `quantize(..., rounding=ROUND_HALF_UP)` |

## 示例

```python
from decimal import Decimal, ROUND_HALF_UP

price = Decimal("10.235")
result = price.quantize(Decimal("0.01"), rounding=ROUND_HALF_UP)
print(result)
```

## 为什么不用浮点

```python
print(0.1 + 0.2)  # 0.30000000000000004
```

```python
from decimal import Decimal

print(Decimal("0.1") + Decimal("0.2"))  # 0.3
```

## 提醒

- 构造 `Decimal` 时优先传字符串，不要直接传浮点数
- 财务业务里要统一舍入规则

返回 [索引](../README.md)

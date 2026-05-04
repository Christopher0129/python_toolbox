# Hypothesis

`Hypothesis` 适合属性测试和自动生成测试数据，能帮助你发现边界条件和反例。

## 安装

```bash
pip install hypothesis
```

## 基本示例

```python
from hypothesis import given, strategies as st


@given(st.integers())
def test_is_integer(n):
    assert isinstance(n, int)
```

## 常见策略

| 策略 | 用途 |
| --- | --- |
| `st.integers()` | 整数 |
| `st.text()` | 文本 |
| `st.lists(...)` | 列表 |
| `st.sampled_from(...)` | 从给定候选中采样 |

## 适用场景

- 纯函数和算法测试
- 数据结构不变量验证
- 容易漏边界的转换逻辑

## 关联阅读

- [pytest](./pytest.md)
- [测试进阶专题](../topics/testing-advanced.md)
- [属性测试专题](../topics/property-based-testing.md)

返回 [索引](../README.md)

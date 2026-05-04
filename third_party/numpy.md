# numpy

`numpy` 是科学计算基础库，核心对象是多维数组 `ndarray`。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `np.array(data)` | 创建数组 | `np.array([1, 2, 3])` |
| `np.arange(start, stop, step)` | 连续数组 | `np.arange(0, 10, 2)` |
| `np.linspace(start, stop, num)` | 等分数组 | `np.linspace(0, 1, 5)` |
| `np.zeros(shape)` / `np.ones(shape)` | 全 0 / 全 1 数组 | `np.zeros((2, 3))` |
| `arr.reshape(shape)` | 改变形状 | `arr.reshape(2, 3)` |
| `arr.mean()` / `arr.sum()` | 均值 / 求和 | `arr.mean()` |
| `np.dot(a, b)` | 点积 | `np.dot(a, b)` |

## 高频属性

| 属性 | 说明 |
| --- | --- |
| `arr.shape` | 形状 |
| `arr.ndim` | 维度数 |
| `arr.dtype` | 数据类型 |

## 示例

```python
import numpy as np

arr = np.array([[1, 2], [3, 4]])
print(arr.shape)
print(arr.mean())
print(arr.reshape(4))
```

## 提醒

- 使用前安装：`pip install numpy`
- `numpy` 数组支持向量化运算，通常比 Python `for` 循环更高效

返回 [索引](../README.md)

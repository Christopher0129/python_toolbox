# statistics 模块

`statistics` 适合做基础统计计算，如均值、中位数、众数和标准差，适合小规模数据分析或脚本汇总。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `mean(data)` | 算术平均值 | `mean(scores)` |
| `median(data)` | 中位数 | `median(values)` |
| `mode(data)` | 众数 | `mode(labels)` |
| `stdev(data)` | 样本标准差 | `stdev(nums)` |
| `pstdev(data)` | 总体标准差 | `pstdev(nums)` |

## 示例

```python
from statistics import mean, median, stdev

nums = [10, 20, 20, 30]
print(mean(nums))
print(median(nums))
print(stdev(nums))
```

## 适用场景

- 报表脚本
- 简单实验数据分析
- 不想引入 `numpy` / `pandas` 的轻量计算

## 注意事项

- 数据为空时通常会报错
- 大规模数值计算和矩阵运算仍更适合 `numpy`

## 关联阅读

- [math](./math.md)
- [decimal](./decimal.md)
- [numpy](../third_party/numpy.md)
- [数据清洗专题](../topics/data-cleaning.md)

返回 [索引](../README.md)

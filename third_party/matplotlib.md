# matplotlib

`matplotlib` 是 Python 最常用的基础可视化库，适合画折线图、柱状图、散点图、直方图等。

## 安装

```bash
pip install matplotlib
```

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `plt.figure()` | 创建图对象 | `plt.figure(figsize=(8, 4))` |
| `plt.plot(x, y)` | 画折线图 | `plt.plot(x, y)` |
| `plt.bar(x, y)` | 画柱状图 | `plt.bar(names, scores)` |
| `plt.scatter(x, y)` | 画散点图 | `plt.scatter(x, y)` |
| `plt.hist(data)` | 画直方图 | `plt.hist(nums, bins=20)` |
| `plt.title(text)` | 标题 | `plt.title("Sales")` |
| `plt.xlabel(text)` / `plt.ylabel(text)` | 坐标轴标签 | `plt.xlabel("day")` |
| `plt.legend()` | 显示图例 | `plt.legend()` |
| `plt.show()` | 显示图形 | `plt.show()` |
| `plt.savefig(path)` | 保存图片 | `plt.savefig("chart.png")` |
| `plt.subplots()` | 创建子图 | `fig, ax = plt.subplots()` |

## 最小示例

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4]
y = [2, 4, 3, 5]

plt.plot(x, y, label="sales")
plt.title("Demo Chart")
plt.xlabel("day")
plt.ylabel("value")
plt.legend()
plt.show()
```

## 常见图表类型

| 图表 | 适用场景 |
| --- | --- |
| 折线图 `plot()` | 趋势变化 |
| 柱状图 `bar()` | 分类对比 |
| 散点图 `scatter()` | 相关性观察 |
| 直方图 `hist()` | 分布情况 |

## 提醒

- 和 `pandas` 配合很常见，先清洗数据再画图
- 批量导出图表时，常用 `savefig()` 而不是 `show()`
- 中文显示异常时，需要单独配置字体

返回 [索引](../README.md)

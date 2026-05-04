# seaborn

`seaborn` 建立在 `matplotlib` 之上，适合更快速地绘制统计图表。

## 安装

```bash
pip install seaborn
```

## 基本示例

```python
import seaborn as sns
import matplotlib.pyplot as plt

tips = sns.load_dataset("tips")
sns.barplot(data=tips, x="day", y="total_bill")
plt.show()
```

## 适合的图表

- 分类比较
- 分布图
- 箱线图
- 热力图

## 关联阅读

- [matplotlib](./matplotlib.md)
- [pandas](./pandas.md)
- [数据可视化专题](../topics/data-visualization.md)

返回 [索引](../README.md)

# plotly

`plotly` 适合交互式图表、网页嵌入图表和仪表盘展示。

## 安装

```bash
pip install plotly
```

## 基本示例

```python
import plotly.express as px

df = px.data.iris()
fig = px.scatter(df, x="sepal_width", y="sepal_length", color="species")
fig.show()
```

## 适用场景

- 交互式数据探索
- 仪表盘原型
- 导出 HTML 图表

## 关联阅读

- [matplotlib](./matplotlib.md)
- [pandas](./pandas.md)
- [streamlit](./streamlit.md)
- [数据可视化专题](../topics/data-visualization.md)

返回 [索引](../README.md)

# streamlit

`streamlit` 适合快速把 Python 数据脚本包装成交互式网页应用。

## 安装

```bash
pip install streamlit
```

## 最小示例

```python
import streamlit as st

st.title("Demo")
name = st.text_input("Name")
st.write("hello", name)
```

运行：

```bash
streamlit run app.py
```

## 适用场景

- 数据分析演示页
- 内部小工具
- 快速原型

## 关联阅读

- [pandas](./pandas.md)
- [plotly](./plotly.md)
- [项目结构专题](../topics/project-structure.md)

返回 [索引](../README.md)

# jinja2

`jinja2` 适合模板渲染，常用于 HTML 页面、配置文件生成和代码模板输出。

## 安装

```bash
pip install jinja2
```

## 基本示例

```python
from jinja2 import Template

tpl = Template("hello {{ name }}")
print(tpl.render(name="Tom"))
```

## 常见用途

- Web 模板渲染
- 生成配置文件
- 批量导出文本报告

## 常用语法

| 语法 | 用途 |
| --- | --- |
| `{{ var }}` | 输出变量 |
| `{% for x in xs %}` | 循环 |
| `{% if cond %}` | 条件判断 |

## 关联阅读

- [Flask 入门](../frameworks/flask.md)
- [string](../stdlib/string.md)
- [配置管理专题](../topics/config-management.md)

返回 [索引](../README.md)

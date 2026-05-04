# Flask 入门

`Flask` 是轻量级 Web 框架，适合小型接口、后台工具和快速原型。

## 安装

```bash
pip install flask
```

## 最小示例

```python
from flask import Flask, jsonify, request

app = Flask(__name__)

@app.route("/")
def home():
    return "hello flask"

@app.route("/api/echo", methods=["POST"])
def echo():
    data = request.get_json()
    return jsonify(data)

if __name__ == "__main__":
    app.run(debug=True)
```

## 高频对象

| 对象 / API | 用途 |
| --- | --- |
| `Flask(__name__)` | 创建应用 |
| `@app.route()` | 注册路由 |
| `request` | 获取请求参数、JSON、表单 |
| `jsonify()` | 返回 JSON 响应 |
| `render_template()` | 渲染模板 |

## 常见目录

```text
project/
  app.py
  templates/
  static/
```

## 适用场景

- 简单 REST API
- 内部管理工具
- 小型网站和原型验证

返回 [索引](../README.md)

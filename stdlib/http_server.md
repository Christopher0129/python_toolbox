# http.server 模块

`http.server` 适合快速启动一个本地静态文件服务，常用于临时共享目录、调试前端文件和局域网传文件。

## 最常用方式

```bash
python -m http.server 8000
```

默认会把当前目录作为站点根目录，访问 `http://127.0.0.1:8000/`。

## 常用类

| 类 / 方法 | 说明 |
| --- | --- |
| `HTTPServer(server_address, handler)` | 创建 HTTP 服务 |
| `SimpleHTTPRequestHandler` | 静态文件处理器 |
| `serve_forever()` | 持续运行服务 |

## 示例

```python
from http.server import HTTPServer, SimpleHTTPRequestHandler

server = HTTPServer(("127.0.0.1", 8000), SimpleHTTPRequestHandler)
server.serve_forever()
```

## 适用场景

- 临时共享一个文件目录
- 前端本地调试静态页面
- 局域网里快速下载测试文件

## 提醒

- 这是开发调试工具，不适合正式生产环境
- 对外开放端口时要注意目录暴露风险

返回 [索引](../README.md)

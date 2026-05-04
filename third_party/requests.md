# requests

`requests` 是最常用的 HTTP 客户端库之一，适合调用接口、下载资源、提交表单。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `requests.get(url, params=..., headers=..., timeout=...)` | GET 请求 | `requests.get(url, params={"q": "python"})` |
| `requests.post(url, json=..., data=..., timeout=...)` | POST 请求 | `requests.post(url, json=payload)` |
| `resp.json()` | 解析 JSON 响应 | `data = resp.json()` |
| `resp.text` | 文本响应 | `print(resp.text)` |
| `resp.raise_for_status()` | 非 2xx 抛异常 | `resp.raise_for_status()` |
| `requests.Session()` | 复用连接、保持 Cookie | `session = requests.Session()` |

## 示例

```python
import requests

resp = requests.get(
    "https://httpbin.org/get",
    params={"name": "Tom"},
    timeout=10,
)
resp.raise_for_status()
print(resp.json())
```

## 常用参数

- `params`：查询参数
- `json`：发送 JSON 请求体
- `data`：发送表单数据
- `headers`：自定义请求头
- `timeout`：超时设置，生产代码建议始终传

## 提醒

- 使用前安装：`pip install requests`
- 外部接口调用建议统一加 `timeout` 和 `raise_for_status()`

返回 [索引](../README.md)

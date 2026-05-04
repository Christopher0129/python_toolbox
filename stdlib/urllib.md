# urllib 模块

`urllib` 是标准库里的 URL 和基础 HTTP 工具集合，常用部分主要是 `urllib.request` 和 `urllib.parse`。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `urllib.request.urlopen(url)` | 发送基础 HTTP 请求 | `urlopen("https://example.com")` |
| `urllib.request.Request(url, headers=...)` | 构造请求对象 | `Request(url, headers={"User-Agent": "demo"})` |
| `urllib.parse.urlencode(params)` | 编码查询参数 | `urlencode({"q": "python"})` |
| `urllib.parse.quote(text)` | URL 编码 | `quote("中文")` |
| `urllib.parse.unquote(text)` | URL 解码 | `unquote(text)` |
| `urllib.parse.urlparse(url)` | 解析 URL | `urlparse("https://a.com/x?a=1")` |

## 请求示例

```python
from urllib.request import urlopen

with urlopen("https://example.com") as resp:
    print(resp.status)
    print(resp.read(100))
```

## URL 处理示例

```python
from urllib.parse import urlencode, urlparse

query = urlencode({"q": "python", "page": 1})
print(query)
print(urlparse("https://example.com/search?q=python"))
```

## 适用场景

- 不想安装第三方库时，做简单下载和 URL 处理
- 构造查询字符串、路径编码

## 提醒

- 复杂接口调用通常还是 `requests` 更顺手
- `urlopen()` 返回字节数据，常需自行解码

返回 [索引](../README.md)

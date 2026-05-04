# httpx

`httpx` 是现代化 HTTP 客户端库，接口风格接近 `requests`，同时支持同步和异步调用。

## 安装

```bash
pip install httpx
```

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `httpx.get()` | 同步 GET 请求 | `httpx.get(url, timeout=10)` |
| `httpx.post()` | 同步 POST 请求 | `httpx.post(url, json=data)` |
| `httpx.Client()` | 复用连接、统一配置 | `with httpx.Client() as client:` |
| `httpx.AsyncClient()` | 异步 HTTP 客户端 | `async with httpx.AsyncClient() as client:` |
| `resp.json()` | 解析 JSON 响应 | `data = resp.json()` |
| `resp.raise_for_status()` | 非 2xx 抛异常 | `resp.raise_for_status()` |

## 同步示例

```python
import httpx

with httpx.Client(timeout=10) as client:
    resp = client.get("https://httpbin.org/get", params={"q": "python"})
    resp.raise_for_status()
    print(resp.json())
```

## 异步示例

```python
import asyncio
import httpx


async def main():
    async with httpx.AsyncClient(timeout=10) as client:
        resp = await client.get("https://httpbin.org/get")
        resp.raise_for_status()
        print(resp.json())


asyncio.run(main())
```

## 和 `requests` 的区别

| 维度 | `requests` | `httpx` |
| --- | --- | --- |
| 同步支持 | 很成熟 | 支持 |
| 异步支持 | 不支持 | 支持 |
| HTTP/2 | 需额外方案 | 支持更自然 |
| 接口风格 | 经典 | 接近 `requests` |

## 使用建议

- 只做同步简单请求时，`requests` 依然很好用
- 需要同步和异步统一风格时，优先考虑 `httpx`
- 和 `asyncio` 结合时，不要混入阻塞式网络调用

## 关联阅读

- [requests](./requests.md)
- [aiohttp](./aiohttp.md)
- [asyncio](../stdlib/asyncio.md)
- [网络编程专题](../topics/network-programming.md)
- [Web 抓取专题](../topics/web-scraping.md)

返回 [索引](../README.md)

# aiohttp

`aiohttp` 是常见的异步 HTTP 库，适合高并发抓取、异步接口调用和轻量异步服务。

## 安装

```bash
pip install aiohttp
```

## 客户端常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `aiohttp.ClientSession()` | 创建异步会话 | `async with aiohttp.ClientSession() as session:` |
| `session.get()` | 异步 GET 请求 | `await session.get(url)` |
| `session.post()` | 异步 POST 请求 | `await session.post(url, json=data)` |
| `resp.text()` | 读取文本响应 | `await resp.text()` |
| `resp.json()` | 读取 JSON 响应 | `await resp.json()` |

## 基本示例

```python
import asyncio
import aiohttp


async def fetch(url):
    async with aiohttp.ClientSession() as session:
        async with session.get(url, timeout=10) as resp:
            return await resp.text()


async def main():
    html = await fetch("https://example.com")
    print(len(html))


asyncio.run(main())
```

## 并发抓取示例

```python
import asyncio
import aiohttp


async def fetch(session, url):
    async with session.get(url, timeout=10) as resp:
        return resp.status


async def main():
    urls = ["https://example.com"] * 5
    async with aiohttp.ClientSession() as session:
        tasks = [fetch(session, url) for url in urls]
        print(await asyncio.gather(*tasks))


asyncio.run(main())
```

## 使用建议

- 会话尽量复用，不要每个请求都新建 `ClientSession`
- 要控制并发量，避免把目标站点或本机资源打满
- 异步环境里不要混用阻塞式 `requests`

## 关联阅读

- [asyncio](../stdlib/asyncio.md)
- [httpx](./httpx.md)
- [网络编程专题](../topics/network-programming.md)
- [Web 抓取专题](../topics/web-scraping.md)

返回 [索引](../README.md)

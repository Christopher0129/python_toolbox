# Web 抓取专题

这个专题把网页抓取常见链路串起来：发请求、控制节奏、解析 HTML、抽取链接和落盘保存。

## 先学哪些模块和库

| 模块 / 库 | 作用 | 推荐程度 |
| --- | --- | --- |
| `requests` | 同步抓取页面 | 必学 |
| `httpx` | 现代同步 / 异步 HTTP | 高频 |
| `aiohttp` | 高并发异步抓取 | 进阶 |
| `BeautifulSoup` | HTML 解析 | 必学 |
| `re` | 简单文本提取 | 常用 |
| `pathlib` / `json` | 保存结果 | 高频 |

## 基础抓取流程

### 1. 请求页面

```python
import requests

resp = requests.get("https://example.com", timeout=10)
resp.raise_for_status()
html = resp.text
```

### 2. 解析 HTML

```python
from bs4 import BeautifulSoup

soup = BeautifulSoup(html, "html.parser")
titles = [a.get_text(strip=True) for a in soup.find_all("a")]
print(titles)
```

### 3. 保存结果

```python
import json
from pathlib import Path

Path("result.json").write_text(
    json.dumps(titles, ensure_ascii=False, indent=2),
    encoding="utf-8",
)
```

## 异步抓取适合什么场景

- 页面很多，单页逻辑简单
- 主要耗时在网络等待
- 能明确控制并发和失败重试

## 常见问题

| 问题 | 处理思路 |
| --- | --- |
| 频繁超时 | 调整超时、重试、降低并发 |
| 页面结构变化 | 重新检查选择器 |
| 数据乱码 | 确认响应编码 |
| JS 渲染页面 | 只靠静态 HTML 可能拿不到内容 |

## 实战建议

- 始终加 `timeout`
- 对目标站点保持克制，控制访问频率
- 把抓取、解析、保存拆成独立函数，便于测试

## 关联阅读

- [requests](../third_party/requests.md)
- [httpx](../third_party/httpx.md)
- [aiohttp](../third_party/aiohttp.md)
- [Beautiful Soup 4](../third_party/beautifulsoup4.md)
- [网络编程专题](./network-programming.md)

返回 [索引](../README.md)

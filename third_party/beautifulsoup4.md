# Beautiful Soup 4

`BeautifulSoup` 适合解析 HTML、提取标签内容和做轻量网页抓取。它不负责发请求，通常与 `requests`、`httpx` 或 `aiohttp` 配合使用。

## 安装

```bash
pip install beautifulsoup4
```

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `BeautifulSoup(html, "html.parser")` | 创建解析对象 | `soup = BeautifulSoup(html, "html.parser")` |
| `soup.find()` | 找第一个匹配标签 | `soup.find("h1")` |
| `soup.find_all()` | 找全部匹配标签 | `soup.find_all("a")` |
| `tag.get_text()` | 提取纯文本 | `title.get_text(strip=True)` |
| `tag.get("href")` | 读取属性 | `link.get("href")` |
| `soup.select()` | CSS 选择器查询 | `soup.select("div.item a")` |

## 基本示例

```python
import requests
from bs4 import BeautifulSoup

resp = requests.get("https://example.com", timeout=10)
resp.raise_for_status()

soup = BeautifulSoup(resp.text, "html.parser")
for link in soup.find_all("a"):
    print(link.get_text(strip=True), link.get("href"))
```

## CSS 选择器示例

```python
from bs4 import BeautifulSoup

html = """
<ul>
  <li class="item"><a href="/a">A</a></li>
  <li class="item"><a href="/b">B</a></li>
</ul>
"""

soup = BeautifulSoup(html, "html.parser")
for node in soup.select("li.item a"):
    print(node.get_text(strip=True), node["href"])
```

## 使用建议

- 解析结构稳定的静态页面时非常合适
- 页面依赖 JavaScript 渲染时，可能只靠它拿不到最终内容
- 提取前先观察 HTML 结构，不要盲目写复杂选择器

## 关联阅读

- [requests](./requests.md)
- [httpx](./httpx.md)
- [re](../stdlib/re.md)
- [Web 抓取专题](../topics/web-scraping.md)

返回 [索引](../README.md)

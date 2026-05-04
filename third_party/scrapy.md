# Scrapy

`Scrapy` 适合做结构化、可扩展的大规模爬取，而不是只写一次性的单脚本抓取。

## 安装

```bash
pip install scrapy
```

## 基本示例

```python
import scrapy


class QuoteSpider(scrapy.Spider):
    name = "quotes"
    start_urls = ["https://quotes.toscrape.com/"]

    def parse(self, response):
        for quote in response.css(".quote"):
            yield {"text": quote.css(".text::text").get()}
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `scrapy.Spider` | 定义爬虫入口 |
| `response.css(...)` | 用 CSS 选择器提取内容 |
| `CrawlerProcess(...)` | 在代码中启动抓取流程 |

## 关联阅读

- [Scrapy 爬取专题](../topics/scrapy-crawling.md)
- [Web 抓取专题](../topics/web-scraping.md)
- [数据管道专题](../topics/data-pipelines.md)

返回 [索引](../README.md)

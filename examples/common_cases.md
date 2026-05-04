# 常见 Python 实战脚本

下面整理几个高频实战场景，方便从模块知识跳到组合应用。

## 1. 批量重命名文件

涉及模块：`pathlib`、`os`

```python
from pathlib import Path

root = Path("photos")
for idx, file in enumerate(root.glob("*.jpg"), start=1):
    new_name = root / f"img_{idx:03d}.jpg"
    file.rename(new_name)
```

## 2. 读取 CSV 并导出 JSON

涉及模块：`csv`、`json`

```python
import csv
import json

rows = []
with open("users.csv", "r", encoding="utf-8") as f:
    for row in csv.DictReader(f):
        rows.append(row)

with open("users.json", "w", encoding="utf-8") as f:
    json.dump(rows, f, ensure_ascii=False, indent=2)
```

## 3. 命令行参数脚本

涉及模块：`argparse`、`sys`

```python
import argparse

parser = argparse.ArgumentParser()
parser.add_argument("name")
parser.add_argument("--times", type=int, default=1)
args = parser.parse_args()

for _ in range(args.times):
    print(f"hello, {args.name}")
```

## 4. 调用外部命令并记录日志

涉及模块：`subprocess`、`logging`

```python
import logging
import subprocess

logging.basicConfig(level=logging.INFO)
result = subprocess.run(
    ["python", "--version"],
    text=True,
    capture_output=True,
    check=True,
)
logging.info("version: %s", result.stdout.strip())
```

## 5. 简单单元测试

涉及模块：`unittest`

```python
import unittest

def multiply(a, b):
    return a * b

class TestMultiply(unittest.TestCase):
    def test_basic(self):
        self.assertEqual(multiply(2, 3), 6)

if __name__ == "__main__":
    unittest.main()
```

## 6. 抓取网页标题并保存 JSON

涉及模块 / 库：`requests`、`BeautifulSoup`、`json`、`pathlib`

```python
import json
from pathlib import Path

import requests
from bs4 import BeautifulSoup

resp = requests.get("https://example.com", timeout=10)
resp.raise_for_status()

soup = BeautifulSoup(resp.text, "html.parser")
titles = [a.get_text(strip=True) for a in soup.find_all("a")]

Path("titles.json").write_text(
    json.dumps(titles, ensure_ascii=False, indent=2),
    encoding="utf-8",
)
```

## 7. 简单异步并发请求

涉及模块 / 库：`asyncio`、`httpx`

```python
import asyncio
import httpx


async def fetch(client, url):
    resp = await client.get(url)
    return resp.status_code


async def main():
    urls = ["https://example.com"] * 3
    async with httpx.AsyncClient(timeout=10) as client:
        results = await asyncio.gather(*(fetch(client, url) for url in urls))
    print(results)


asyncio.run(main())
```

## 使用建议

- 先按需求定位模块，再回到对应模块文档看细节
- 把这些脚本模板复制后，根据你的目录和业务字段改动
- 需要更完整的练手方向时，继续看 [Python 小项目模板](./mini_projects.md)

返回 [索引](../README.md)

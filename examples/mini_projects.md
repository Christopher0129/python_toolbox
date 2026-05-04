# Python 小项目模板

这页整理几个比单段脚本更完整的小项目方向，适合把多个模块串起来练。

## 1. 批量文件整理工具

目标：

- 扫描目录
- 按扩展名分类
- 生成处理日志

推荐模块：

- `pathlib`
- `shutil`
- `logging`
- `argparse`

## 2. 接口巡检脚本

目标：

- 定时请求多个接口
- 记录状态码和耗时
- 输出汇总报告

推荐模块 / 库：

- `requests`
- `time`
- `logging`
- `csv` / `json`

## 3. 网页标题抓取器

目标：

- 抓取一组页面
- 提取标题和链接
- 保存为 JSON

推荐模块 / 库：

- `requests` 或 `httpx`
- `BeautifulSoup`
- `pathlib`
- `json`

## 4. SQLite 通讯录

目标：

- 增删改查联系人
- 支持命令行查询

推荐模块 / 库：

- `sqlite3`
- `argparse`
- `tabulate` 风格输出思路或纯文本输出

## 5. 异步批量探测工具

目标：

- 并发请求多个 URL
- 统计成功和失败数量

推荐模块 / 库：

- `asyncio`
- `httpx` 或 `aiohttp`
- `logging`

## 实战建议

- 每个小项目都补一个 `README`
- 每个项目至少写 3 到 5 个测试
- 优先把入口、业务和存储拆开

## 关联阅读

- [常见 Python 实战脚本](./common_cases.md)
- [命令行自动化专题](../topics/automation-cli.md)
- [Web 抓取专题](../topics/web-scraping.md)
- [数据库开发专题](../topics/database-development.md)
- [测试与质量专题](../topics/testing-quality.md)

返回 [索引](../README.md)

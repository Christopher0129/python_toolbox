# 数据管道专题

这个专题关注从原始数据到结果产出的整条链路：采集、清洗、转换、聚合、导出和调度。

## 基本阶段

1. 采集：文件、接口、数据库
2. 清洗：缺失值、格式、重复
3. 转换：字段拆分、类型转换
4. 聚合：汇总和统计
5. 导出：CSV、JSON、Excel、数据库

## 常用模块和库

- `pathlib`
- `json`
- `csv`
- `pandas`
- `requests`
- `sqlite3`
- `Airflow`
- `Great Expectations`
- `Prefect`
- `Dagster`

## 实战建议

- 保留原始数据和清洗结果分层
- 给每一步定义明确输入输出
- 长流程最好加日志和错误恢复点
- 对关键输出定义数据契约和 schema 演进策略

## 关联阅读

- [数据清洗专题](./data-cleaning.md)
- [文件处理专题](./file-processing.md)
- [数据库开发专题](./database-development.md)
- [命令行自动化专题](./automation-cli.md)
- [数据契约专题](./data-contracts.md)
- [Schema 演进专题](./schema-evolution.md)
- [工作流编排专题](./workflow-orchestration.md)

返回 [索引](../README.md)

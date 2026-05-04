# SQLGlot

`SQLGlot` 适合做 SQL 解析、改写、方言转换和血缘分析前处理。

## 安装

```bash
pip install sqlglot
```

## 基本示例

```python
import sqlglot


expr = sqlglot.parse_one("select a, b from t where a > 1")
print(expr.sql())
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `parse_one(...)` | 解析单条 SQL |
| `expr.sql(...)` | 输出目标方言 SQL |
| AST 遍历 | 分析表、列、条件和函数 |

## 使用建议

- 适合 SQL 质量检查、迁移工具和数据血缘工具
- 多方言环境里比字符串替换更可靠
- 复杂 SQL 改写前应先建立回归样例集

## 关联阅读

- [查询计划分析专题](../topics/query-plan-analysis.md)
- [数据血缘专题](../topics/data-lineage.md)
- [SQL 优化专题](../topics/sql-optimization.md)

返回 [索引](../README.md)

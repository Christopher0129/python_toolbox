# Schema 演进专题

这个专题关注结构定义在长期变化中的兼容问题，适用于 API、消息、表结构和分析模型。

## 常见变化

| 变化 | 风险 |
| --- | --- |
| 新增可选字段 | 风险较低 |
| 删除旧字段 | 可能影响旧消费者 |
| 字段重命名 | 容易造成双边不兼容 |
| 类型收紧 | 可能让旧数据无法通过校验 |
| 枚举值扩展 | 旧客户端可能无法识别 |

## 实战建议

- 先新增、再灰度、最后移除，不要直接破坏性替换
- 版本语义要落到 schema、文档和消费者测试上
- 为消费者保留过渡窗口，避免生产者先行破坏
- 对关键表和消息定义兼容性检查

## 关联阅读

- [数据契约专题](./data-contracts.md)
- [API 版本治理专题](./api-versioning.md)
- [Lakehouse 表格式专题](./table-formats-lakehouse.md)
- [pandera](../third_party/pandera.md)
- [Great Expectations](../third_party/great_expectations.md)
- [事件驱动架构专题](./event-driven-architecture.md)

返回 [索引](../README.md)

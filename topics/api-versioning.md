# API 版本治理专题

这个专题关注接口在长期演进中如何兼容，而不是只看当前版本能跑。

## 常见主题

- 路由级版本
- 字段新增和废弃
- 向后兼容策略
- 文档与客户端同步
- 契约测试与兼容验证

## 实战建议

- 破坏性变更要显式版本化
- 非破坏性新增也要说明默认行为
- 接口文档和 SDK 要同步演进
- 对关键消费者保留回归样例或 schema 测试

## 关联阅读

- [API 开发专题](./api-development.md)
- [FastAPI 进阶专题](./fastapi-advanced.md)
- [Schema 演进专题](./schema-evolution.md)
- [契约测试专题](./contract-testing.md)

返回 [索引](../README.md)

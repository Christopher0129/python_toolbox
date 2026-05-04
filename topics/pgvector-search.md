# pgvector 检索专题

这个专题关注在 PostgreSQL 中直接实现向量列、相似度排序和结构化过滤结合的检索方案。

## 适用场景

- 已经以 PostgreSQL 为核心数据库
- 想先用较少组件验证语义检索能力
- 需要把业务过滤条件和向量召回放在同一查询链路中

## 常见主题

- 向量列建模
- 相似度排序
- 结构化过滤
- 索引与资源竞争
- 事务型与检索型负载混布

## 设计要点

- 适合中小规模或平台简化优先的场景
- 与事务型业务混部时要重点观察 CPU、内存和锁竞争
- 召回质量与延迟要和专用向量库做过基线比较再定方案
- 迁移成本、备份策略和读副本能力也要纳入选型

## 关联阅读

- [pgvector](../third_party/pgvector.md)
- [PostgreSQL 开发专题](./postgresql-development.md)
- [向量检索专题](./vector-retrieval.md)
- [混合检索专题](./hybrid-retrieval.md)

返回 [索引](../README.md)

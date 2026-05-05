# 成本治理专题

这个专题关注系统成本不只是云账单，还是模型调用、存储、向量索引、带宽和批处理资源的持续消耗。

## 适用场景

- 模型调用量快速增长
- 数据平台与推理平台成本上涨
- 团队需要在质量和成本之间做权衡

## 常见主题

- token 成本
- 检索和重排成本
- 在线与离线任务分流
- 缓存命中率
- 成本归因

## 设计要点

- 成本治理必须落到请求级、任务级或租户级归因
- 不能只看均值，要看尾部大请求和异常放量
- 预算、限流、降级和缓存要一起设计
- 成本优化前应先建立质量基线，避免只省钱不保效果

## 关联阅读

- [tiktoken](../third_party/tiktoken.md)
- [模型路由专题](./model-routing.md)
- [LLM 网关专题](./llm-gateway.md)
- [容量规划专题](./capacity-planning.md)
- [搜索多租户隔离专题](./search-multitenancy.md)
- [Kubernetes 成本优化专题](./kubernetes-cost-optimization.md)

返回 [索引](../README.md)

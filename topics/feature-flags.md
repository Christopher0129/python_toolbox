# 特性开关专题

这个专题关注功能上线与代码部署解耦，让团队可以更细粒度地控制曝光范围和回滚路径。

## 常见用途

- 灰度发布
- A/B 实验
- 高风险功能开关
- 紧急熔断某条业务路径

## 使用建议

- 开关命名要表达业务意图
- 长期不用的开关要清理，避免配置债务
- 关键开关的开启状态要可观测
- 不要把开关判断散落到过多层次

## 关联阅读

- [Unleash](../third_party/unleash.md)
- [发布策略专题](./deployment-strategies.md)
- [实验跟踪专题](./experiment-tracking.md)
- [FastAPI 进阶专题](./fastapi-advanced.md)

返回 [索引](../README.md)

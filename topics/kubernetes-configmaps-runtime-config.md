# Kubernetes ConfigMap 与运行时配置专题

这个专题关注 Python 服务在 Kubernetes 中如何管理普通配置、动态刷新和配置回滚。

## 适用场景

- 服务大量依赖 ConfigMap 注入配置
- 发布后经常需要快速调整阈值或白名单
- 配置更新会影响滚动发布和故障范围

## 常见主题

- 环境变量注入
- 文件挂载
- 配置热更新
- 配置版本化
- 发布联动

## 设计要点

- ConfigMap 适合普通配置，不适合承载敏感密钥。
- 动态刷新要明确是应用内热加载、sidecar 通知还是滚动重启。
- 配置变更与镜像变更最好都能追踪版本号和生效时间。
- 配置项一旦变多，应抽象成领域配置而不是散落环境变量。

## 关联阅读

- [运行时配置专题](./runtime-configuration.md)
- [配置管理专题](./config-management.md)
- [Kubernetes 运维专题](./kubernetes-operations.md)
- [Kubernetes Secret 分发专题](./kubernetes-secret-distribution.md)
- [配置灰度与回滚专题](./config-rollout-strategies.md)

返回 [索引](../README.md)

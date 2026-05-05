# Kubernetes Pod 排障专题

这个专题关注 Pod 启动失败、频繁重启、就绪失败和节点漂移时的排障路径。

## 适用场景

- Pod 进入 `CrashLoopBackOff`
- 探针失败导致服务不稳定
- 配置变更后只有部分 Pod 异常

## 常见主题

- `describe` 与 events
- 容器日志
- 探针失败
- 资源限制
- 临时调试容器

## 设计要点

- Pod 排障要优先区分是调度问题、镜像问题、启动问题还是运行时问题。
- 事件、日志和最近一次发布记录应一起看，避免只盯单个 Pod。
- 对频繁重启场景，要同时审视探针阈值、依赖超时和资源限制。
- 有状态与无状态 Pod 的恢复优先级不同，排障手册也要分开维护。

## 关联阅读

- [Kubernetes 运维专题](./kubernetes-operations.md)
- [Kubernetes 探针与优雅停机专题](./kubernetes-probes-graceful-shutdown.md)
- [Kubernetes 镜像拉取故障专题](./kubernetes-image-pull-failures.md)
- [Kubernetes Stateful 工作负载专题](./kubernetes-stateful-workloads.md)
- [Runbook 与运维手册专题](./runbooks-and-ops.md)

返回 [索引](../README.md)

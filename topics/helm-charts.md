# Helm 与 Chart 专题

这个专题关注如何把 Kubernetes 部署清单模板化、参数化和版本化。

## 适用场景

- 多环境、多服务共享部署模板
- 应用版本和部署参数一起管理
- 需要可回滚、可审计的 K8s 发布流程

## 常见主题

- values.yaml 设计
- 模板变量与条件渲染
- 环境差异管理
- chart 复用
- 发布回滚

## 设计要点

- `values.yaml` 应体现环境差异，而不是堆所有可能开关
- chart 复用要控制层级，避免模板继承失控
- 渲染结果最好纳入审查和 CI 校验
- Helm 只解决模板和发布，不自动解决配置治理

## 关联阅读

- [Helm](../third_party/helm.md)
- [Kubernetes 运维专题](./kubernetes-operations.md)
- [发布策略专题](./deployment-strategies.md)
- [GitOps 交付专题](./gitops-delivery.md)

返回 [索引](../README.md)

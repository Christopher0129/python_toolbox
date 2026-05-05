# Kubernetes 镜像拉取故障专题

这个专题关注 `ImagePullBackOff`、镜像仓库鉴权失败和镜像发布链路不一致等问题。

## 适用场景

- 新版本发布后 Pod 长时间停在拉镜像阶段
- 私有仓库鉴权不稳定
- 使用 `latest` 或可变 tag 导致线上行为难以复现

## 常见主题

- `ImagePullBackOff`
- 私有仓库凭证
- tag 与 digest
- 节点网络连通性
- 发布链路校验

## 设计要点

- 生产环境应优先使用不可变 digest 或清晰版本 tag，而不是可变 tag。
- 镜像拉取问题要同时检查事件、节点网络、仓库配额和凭证有效期。
- 仓库鉴权失败往往不是单纯 Secret 问题，还可能是节点身份或代理配置问题。
- 镜像构建、扫描、推送和部署链路最好共享同一版本标识。

## 关联阅读

- [Kubernetes 运维专题](./kubernetes-operations.md)
- [部署与运维专题](./deployment-operations.md)
- [GitOps 交付专题](./gitops-delivery.md)
- [供应链安全专题](./supply-chain-security.md)
- [Kubernetes Pod 排障专题](./kubernetes-pod-debugging.md)

返回 [索引](../README.md)

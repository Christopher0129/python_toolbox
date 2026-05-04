# Helm

`Helm` 常用于管理 Kubernetes 应用模板、环境差异和发布版本，Python 项目部署到 K8s 时很常见。

## 安装

```bash
choco install kubernetes-helm
```

## 常见命令

| 命令 | 用途 |
| --- | --- |
| `helm lint` | 检查 chart |
| `helm template` | 渲染模板 |
| `helm upgrade --install` | 安装或升级发布 |

## 关联阅读

- [Helm 与 Chart 专题](../topics/helm-charts.md)
- [Kubernetes 运维专题](../topics/kubernetes-operations.md)
- [发布策略专题](../topics/deployment-strategies.md)

返回 [索引](../README.md)

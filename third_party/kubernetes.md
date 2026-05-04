# Kubernetes Python Client

`kubernetes` 适合在 Python 脚本或控制程序里访问 Kubernetes API，管理 Pod、Job、Deployment 等资源。

## 安装

```bash
pip install kubernetes
```

## 基本示例

```python
from kubernetes import client, config

config.load_kube_config()
v1 = client.CoreV1Api()
pods = v1.list_namespaced_pod("default")
```

## 关联阅读

- [Kubernetes 运维专题](../topics/kubernetes-operations.md)
- [部署与运维专题](../topics/deployment-operations.md)
- [发布策略专题](../topics/deployment-strategies.md)

返回 [索引](../README.md)

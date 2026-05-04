# python-terraform

`python-terraform` 适合在 Python 脚本中驱动 Terraform 命令，用来封装基础设施变更流程。

## 安装

```bash
pip install python-terraform
```

## 基本示例

```python
from python_terraform import Terraform

tf = Terraform(working_dir="infra")
code, out, err = tf.plan()
```

## 关联阅读

- [基础设施自动化专题](../topics/infrastructure-automation.md)
- [部署与运维专题](../topics/deployment-operations.md)
- [发布策略专题](../topics/deployment-strategies.md)

返回 [索引](../README.md)

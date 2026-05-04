# ansible-runner

`ansible-runner` 适合从 Python 中调用 Ansible playbook，用来做自动化运维和批量部署任务。

## 安装

```bash
pip install ansible-runner
```

## 基本示例

```python
import ansible_runner

r = ansible_runner.run(private_data_dir=".", playbook="site.yml")
print(r.status)
```

## 关联阅读

- [基础设施自动化专题](../topics/infrastructure-automation.md)
- [部署与运维专题](../topics/deployment-operations.md)
- [CI/CD 专题](../topics/ci-cd.md)

返回 [索引](../README.md)

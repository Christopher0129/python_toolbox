# Casbin

`Casbin` 适合把访问控制规则从业务代码里抽离出来，统一做策略判断。

## 安装

```bash
pip install pycasbin
```

## 基本示例

```python
import casbin

e = casbin.Enforcer("model.conf", "policy.csv")
allowed = e.enforce("alice", "data1", "read")
print(allowed)
```

## 适用场景

- 统一权限判断
- RBAC / ABAC 策略落地
- 多服务复用权限规则

## 关联阅读

- [RBAC 与 ABAC 专题](../topics/rbac-abac.md)
- [策略引擎专题](../topics/policy-engines.md)

返回 [索引](../README.md)

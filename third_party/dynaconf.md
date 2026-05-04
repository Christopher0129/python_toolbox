# dynaconf

`dynaconf` 适合管理多环境配置，支持环境变量覆盖、多个配置源和分环境 settings。

## 安装

```bash
pip install dynaconf
```

## 基本示例

```python
from dynaconf import Dynaconf

settings = Dynaconf(
    settings_files=["settings.toml", ".secrets.toml"],
)
print(settings.DEBUG)
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `Dynaconf(...)` | 加载多来源配置 |
| 环境切换 | 开发、测试、生产配置隔离 |
| 环境变量覆盖 | 运行时注入差异配置 |

## 适用场景

- 多环境项目配置组织
- 需要 TOML + 环境变量混合配置
- 希望把 secrets 与普通配置分层

## 关联阅读

- [配置管理专题](../topics/config-management.md)
- [密钥管理专题](../topics/secrets-management.md)
- [pydantic-settings](./pydantic_settings.md)

返回 [索引](../README.md)

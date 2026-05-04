# Faker

`Faker` 适合生成测试所需的姓名、地址、手机号、时间等伪造数据。

## 安装

```bash
pip install Faker
```

## 基本示例

```python
from faker import Faker

fake = Faker("zh_CN")
name = fake.name()
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `Faker(...)` | 创建数据生成器 |
| `fake.name()` | 生成姓名 |
| `fake.date_time()` | 生成时间数据 |

## 关联阅读

- [测试数据工厂专题](../topics/test-data-factories.md)
- [pytest](../third_party/pytest.md)
- [factory-boy](../third_party/factory_boy.md)

返回 [索引](../README.md)

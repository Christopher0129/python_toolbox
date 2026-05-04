# factory-boy

`factory-boy` 适合在测试中构造模型对象、数据库记录和复杂对象图，减少重复样板代码。

## 安装

```bash
pip install factory-boy
```

## 基本示例

```python
import factory

class UserFactory(factory.Factory):
    class Meta:
        model = dict

    name = "Tom"
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `factory.Factory` | 定义普通对象工厂 |
| `SubFactory(...)` | 组合关联对象 |
| `Sequence(...)` | 生成唯一序列值 |

## 关联阅读

- [测试数据工厂专题](../topics/test-data-factories.md)
- [Faker](../third_party/faker.md)
- [测试进阶专题](../topics/testing-advanced.md)

返回 [索引](../README.md)

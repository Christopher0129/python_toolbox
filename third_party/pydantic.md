# pydantic

`pydantic` 适合做数据校验、类型转换和配置建模，在 FastAPI、接口入参校验和配置读取中很常见。

## 安装

```bash
pip install pydantic
```

## 基本示例

```python
from pydantic import BaseModel, EmailStr


class User(BaseModel):
    name: str
    age: int
    email: EmailStr


user = User(name="Tom", age="18", email="tom@example.com")
print(user.age)
print(user.model_dump())
```

## 常用能力

| 能力 | 说明 |
| --- | --- |
| 类型校验 | 按声明的字段类型校验输入 |
| 自动转换 | 如把 `"18"` 转为 `18` |
| 默认值 | 字段可设置默认值 |
| 嵌套模型 | 一个模型里嵌套另一个模型 |
| 导出字典 | `model_dump()` |

## 字段约束示例

```python
from pydantic import BaseModel, Field


class Product(BaseModel):
    name: str = Field(min_length=1, max_length=50)
    price: float = Field(ge=0)
```

## 适用场景

- Web API 请求体校验
- 配置文件建模
- 外部 JSON 数据清洗

## 使用建议

- 输入边界层适合用它做校验
- 业务内部已经是可信对象时，不要到处重复建模
- 与 FastAPI 配合时能明显减少手写校验代码

## 关联阅读

- [FastAPI 入门](../frameworks/fastapi.md)
- [typing 与 dataclasses](../stdlib/typing_dataclasses.md)
- [json](../stdlib/json.md)
- [接口测试专题](../topics/api-testing.md)

返回 [索引](../README.md)

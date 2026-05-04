# 面向对象编程

Python 面向对象重点是 `类`、`实例`、`属性`、`方法`、`继承` 和常用魔术方法。

## 核心概念

| 概念 | 说明 |
| --- | --- |
| 类 `class` | 对对象的抽象定义 |
| 实例 `obj = Class()` | 类创建出的具体对象 |
| `self` | 实例方法的第一个参数，代表当前对象 |
| `__init__` | 初始化方法 |
| 继承 | 子类复用父类逻辑 |
| 多态 | 统一接口，不同实现 |

## 示例

```python
class Animal:
    def speak(self):
        raise NotImplementedError

class Dog(Animal):
    def __init__(self, name):
        self.name = name

    def speak(self):
        return f"{self.name}: wang"

dog = Dog("Lucky")
print(dog.speak())
```

## 高频写法

- 用 `@property` 封装只读或受控属性
- 用 `__repr__` 提升调试输出可读性
- 简单数据对象优先考虑 `@dataclass`

## 设计建议

- 先保证类职责单一，再考虑继承
- 公共行为优先抽象到父类或组合对象

返回 [索引](../README.md)

# 语法与数据类型

这页整理 Python 最基础但最常用的语法元素和数据类型，适合用来建立统一心智模型。

## 常见基础类型

| 类型 | 说明 | 示例 |
| --- | --- | --- |
| `int` | 整数 | `1`、`-3` |
| `float` | 浮点数 | `3.14` |
| `bool` | 布尔值 | `True`、`False` |
| `str` | 字符串 | `"python"` |
| `NoneType` | 空值 | `None` |
| `list` | 可变序列 | `[1, 2, 3]` |
| `tuple` | 不可变序列 | `(1, 2, 3)` |
| `dict` | 键值映射 | `{"name": "Tom"}` |
| `set` | 无序去重集合 | `{1, 2, 3}` |

## 可变与不可变

| 类型 | 是否可变 | 常见影响 |
| --- | --- | --- |
| `int` / `float` / `str` / `tuple` | 不可变 | 修改时会创建新对象 |
| `list` / `dict` / `set` | 可变 | 传参和复制时要注意共享问题 |

```python
a = [1, 2]
b = a
b.append(3)
print(a)  # [1, 2, 3]
```

## 常见字面量写法

```python
name = "Tom"
age = 18
score = 92.5
is_active = True
tags = ["python", "cli"]
user = {"name": "Tom", "age": 18}
```

## 类型转换

```python
print(int("123"))
print(float("3.14"))
print(str(100))
print(list("abc"))
```

常见风险：

- `int("abc")` 会抛 `ValueError`
- `list(dict_obj)` 得到的是键，不是键值对

## 真值规则

下面这些值在条件判断里通常视为假：

- `False`
- `None`
- `0`
- `0.0`
- `""`
- `[]`
- `{}`
- `set()`

```python
items = []
if not items:
    print("empty")
```

## 常见坑

- 把 `=` 和 `==` 混淆
- 以为字符串、元组可以原地修改
- 忽略浮点数精度问题
- 在多个变量之间无意共享同一个可变对象

## 关联阅读

- [常用内置函数](../builtins/common-builtins.md)
- [控制流](./control-flow.md)
- [函数与作用域](./functions-scope.md)
- [typing 与 dataclasses](../stdlib/typing_dataclasses.md)

返回 [索引](../README.md)

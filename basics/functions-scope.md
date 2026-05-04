# 函数与作用域

函数是 Python 代码组织的基础单位，作用域规则决定变量从哪里来、修改会影响哪里。

## 定义函数

```python
def add(a, b):
    return a + b
```

好函数的常见特征：

- 输入明确
- 返回值稳定
- 副作用尽量少

## 默认参数和关键字参数

```python
def connect(host, port=3306, *, timeout=10):
    return host, port, timeout
```

- 默认参数适合表达常用配置
- `*` 后参数必须用关键字传值

## `*args` 和 `**kwargs`

```python
def log_all(*args, **kwargs):
    print(args)
    print(kwargs)
```

适合：

- 包装函数
- 转发参数
- 接收不固定数量参数

## Lambda 适用场景

```python
users = [{"name": "Tom", "age": 20}, {"name": "Amy", "age": 18}]
users = sorted(users, key=lambda item: item["age"])
```

建议：

- 只在非常短小的场景使用
- 逻辑一复杂就改成普通 `def`

## LEGB 作用域规则

变量查找顺序通常是：

1. Local
2. Enclosing
3. Global
4. Built-in

```python
x = "global"

def outer():
    x = "outer"

    def inner():
        print(x)

    inner()
```

## `global` 和 `nonlocal`

```python
count = 0

def inc():
    global count
    count += 1
```

```python
def outer():
    value = 0

    def inner():
        nonlocal value
        value += 1
        return value

    return inner
```

建议：

- 工程代码里尽量少用 `global`
- 如果频繁需要跨层修改状态，通常说明设计可以再整理

## 常见问题

- 可变默认参数误共享
- 返回值和打印混用
- 作用域不清导致变量覆盖

## 关联阅读

- [函数与模块组织](./functions-modules.md)
- [语法与数据类型](./syntax-data-types.md)
- [装饰器与上下文管理](./decorators-context-managers.md)
- [项目结构专题](../topics/project-structure.md)

返回 [索引](../README.md)

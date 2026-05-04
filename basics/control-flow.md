# 控制流

控制流决定代码如何分支、循环和提前结束。基础语法不复杂，但很多 bug 都出在这里。

## 条件判断

```python
score = 85

if score >= 90:
    level = "A"
elif score >= 60:
    level = "B"
else:
    level = "C"
```

建议：

- 分支条件按“最具体到最宽泛”排列
- 不要把过多业务逻辑塞进单个 `if`

## `for` 循环

```python
for idx, name in enumerate(["Tom", "Amy"], start=1):
    print(idx, name)
```

高频搭配：

- `range()`
- `enumerate()`
- `zip()`

## `while` 循环

```python
count = 3
while count > 0:
    print(count)
    count -= 1
```

适合：

- 重试逻辑
- 消费队列
- 条件未知结束时间的任务

## `break`、`continue`、`pass`

| 语句 | 作用 |
| --- | --- |
| `break` | 提前结束当前循环 |
| `continue` | 跳过本次循环，进入下一次 |
| `pass` | 占位，不执行任何动作 |

## 循环 `else`

`for` / `while` 的 `else` 只会在循环没有被 `break` 打断时执行。

```python
for x in [1, 3, 5]:
    if x == 2:
        break
else:
    print("not found")
```

## `match` 模式匹配

Python 3.10+ 可以使用 `match` 表达更清晰的多分支匹配。

```python
status = 404

match status:
    case 200:
        print("ok")
    case 404:
        print("not found")
    case _:
        print("unknown")
```

## 常见问题

- 循环变量在外层被误用
- `while` 条件不变导致死循环
- 复杂分支没有及时提取成函数

## 关联阅读

- [语法与数据类型](./syntax-data-types.md)
- [常用内置函数](../builtins/common-builtins.md)
- [推导式与生成器](./comprehensions-generators.md)
- [算法与数据结构专题](../topics/algorithms-data-structures.md)

返回 [索引](../README.md)

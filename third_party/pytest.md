# pytest

`pytest` 是 Python 里最常用的测试框架之一，写法比 `unittest` 更简洁，夹具和参数化能力也更强。

## 安装

```bash
pip install pytest
```

## 最小示例

```python
def add(a, b):
    return a + b

def test_add():
    assert add(1, 2) == 3
```

运行：

```bash
pytest
```

## 常用 API / 写法

| API / 写法 | 说明 | 示例 |
| --- | --- | --- |
| `assert expr` | 断言 | `assert x == 3` |
| `pytest.raises(exc)` | 断言抛异常 | `with pytest.raises(ValueError): ...` |
| `@pytest.fixture` | 定义夹具 | `@pytest.fixture` |
| `@pytest.mark.parametrize(...)` | 参数化测试 | `@pytest.mark.parametrize("x", [1, 2])` |
| `pytest -q` | 简洁输出 | `pytest -q` |
| `pytest path::test_name` | 跑指定测试 | `pytest tests/test_user.py::test_login` |

## `raises` 示例

```python
import pytest

def divide(a, b):
    return a / b

def test_divide_zero():
    with pytest.raises(ZeroDivisionError):
        divide(1, 0)
```

## `fixture` 示例

```python
import pytest

@pytest.fixture
def user():
    return {"name": "Tom", "age": 18}

def test_user_name(user):
    assert user["name"] == "Tom"
```

## `parametrize` 示例

```python
import pytest

@pytest.mark.parametrize("a,b,expected", [
    (1, 2, 3),
    (2, 3, 5),
])
def test_add(a, b, expected):
    assert a + b == expected
```

## 提醒

- `pytest` 通常能直接运行 `unittest` 风格的测试
- 夹具适合统一准备测试数据、数据库连接、临时目录
- 和项目一起使用时，常加上 `pytest.ini` 或 `pyproject.toml` 配置

返回 [索引](../README.md)

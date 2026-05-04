# unittest 模块

`unittest` 是 Python 标准库的单元测试框架，适合组织测试类、断言和测试运行入口。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `unittest.TestCase` | 测试用例基类 | `class TestMath(unittest.TestCase):` |
| `setUp()` / `tearDown()` | 每条测试前后初始化和清理 | `def setUp(self): ...` |
| `assertEqual(a, b)` | 断言相等 | `self.assertEqual(add(1, 2), 3)` |
| `assertTrue(x)` / `assertFalse(x)` | 断言真假 | `self.assertTrue(ok)` |
| `assertRaises(exc)` | 断言抛出异常 | `with self.assertRaises(ValueError): ...` |
| `unittest.main()` | 直接运行测试 | `unittest.main()` |

## 示例

```python
import unittest

def add(a, b):
    return a + b

class TestAdd(unittest.TestCase):
    def test_add(self):
        self.assertEqual(add(1, 2), 3)

if __name__ == "__main__":
    unittest.main()
```

## 常见命令

```bash
python -m unittest
python -m unittest discover
python -m unittest tests.test_user
```

## 提醒

- 测试文件通常命名为 `test_*.py`
- 复杂 mock 场景常配合 `unittest.mock` 使用

返回 [索引](../README.md)

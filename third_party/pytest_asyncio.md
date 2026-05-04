# pytest-asyncio

`pytest-asyncio` 适合在 `pytest` 中直接编写和运行协程测试。

## 安装

```bash
pip install pytest-asyncio
```

## 基本示例

```python
import pytest

@pytest.mark.asyncio
async def test_ping():
    assert 1 + 1 == 2
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `@pytest.mark.asyncio` | 声明异步测试函数 |
| `event_loop` fixture | 自定义事件循环 |
| 异步 fixture | 管理协程资源生命周期 |

## 关联阅读

- [异步测试专题](../topics/async-testing.md)
- [异步编程专题](../topics/async-programming.md)
- [pytest](../third_party/pytest.md)

返回 [索引](../README.md)

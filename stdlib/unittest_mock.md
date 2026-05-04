# unittest.mock 模块

`unittest.mock` 适合在测试中替换外部依赖，例如 HTTP 请求、数据库调用、时间函数和文件操作。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `Mock()` | 基础模拟对象 | `mock = Mock()` |
| `MagicMock()` | 带更多魔术方法支持 | `obj = MagicMock()` |
| `patch(target)` | 临时替换目标对象 | `with patch("mod.func"):` |
| `patch.object(obj, name)` | 替换对象属性 | `patch.object(client, "get")` |
| `mock_open()` | 模拟 `open()` | `with patch("builtins.open", mock_open(...))` |
| `side_effect` | 指定异常或动态行为 | `mock.side_effect = TimeoutError` |
| `return_value` | 指定返回值 | `mock.return_value = {"ok": True}` |

## `patch` 示例

```python
from unittest.mock import Mock, patch


def fetch_user(user_id):
    import requests
    resp = requests.get(f"https://api.example.com/users/{user_id}", timeout=10)
    resp.raise_for_status()
    return resp.json()


def test_fetch_user():
    fake_resp = Mock()
    fake_resp.json.return_value = {"id": 1, "name": "Tom"}
    fake_resp.raise_for_status.return_value = None

    with patch("requests.get", return_value=fake_resp) as mock_get:
        data = fetch_user(1)

    mock_get.assert_called_once()
    assert data["name"] == "Tom"
```

## `mock_open` 示例

```python
from unittest.mock import mock_open, patch

with patch("builtins.open", mock_open(read_data="hello")) as mocked:
    with open("demo.txt", "r", encoding="utf-8") as f:
        assert f.read() == "hello"

mocked.assert_called_once()
```

## 什么时候适合用 mock

- 外部接口不稳定或不想真调用
- 测试异常分支
- 文件、时间、随机数需要可控

## 使用建议

- 优先 mock 边界依赖，不要把自己写的业务逻辑全 mock 掉
- `patch()` 的目标要写“被测模块里实际引用的位置”
- 复杂测试优先用真实小对象，mock 只保留在外部依赖边界

## 关联阅读

- [pytest](../third_party/pytest.md)
- [unittest](./unittest.md)
- [requests](../third_party/requests.md)
- [接口测试专题](../topics/api-testing.md)

返回 [索引](../README.md)

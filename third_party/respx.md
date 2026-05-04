# respx

`respx` 适合拦截 `httpx` 请求，在测试里模拟外部 HTTP 服务。

## 安装

```bash
pip install respx httpx
```

## 基本示例

```python
import httpx
import respx

@respx.mock
def test_client():
    respx.get("https://api.example.com/ping").mock(return_value=httpx.Response(200))
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `@respx.mock` | 打开请求拦截上下文 |
| `respx.get(...).mock(...)` | 声明路由返回值 |
| `route.called` | 断言请求是否被命中 |

## 关联阅读

- [HTTP Mock 与录制专题](../topics/http-mocking-recording.md)
- [接口测试专题](../topics/api-testing.md)
- [httpx](../third_party/httpx.md)

返回 [索引](../README.md)

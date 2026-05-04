# slowapi

`slowapi` 适合给 FastAPI / Starlette 服务增加请求限流能力，保护接口不被突发流量和滥用拖垮。

## 安装

```bash
pip install slowapi
```

## 基本示例

```python
from fastapi import FastAPI, Request
from slowapi import Limiter
from slowapi.util import get_remote_address

app = FastAPI()
limiter = Limiter(key_func=get_remote_address)


@app.get("/items")
@limiter.limit("10/minute")
async def list_items(request: Request):
    return {"items": []}
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `Limiter(...)` | 创建限流器 |
| `@limiter.limit("10/minute")` | 给路由加配额 |
| 默认 / 共享限流 | 对全局或一组接口统一限速 |

## 注意事项

- 处理函数需要显式接收 `request`
- 装饰器顺序要正确，通常先写路由装饰器，再写 `@limiter.limit(...)`
- 限流命中后要配合日志和指标一起观察

## 关联阅读

- [限流专题](../topics/rate-limiting.md)
- [FastAPI 进阶专题](../topics/fastapi-advanced.md)
- [健康检查与指标专题](../topics/health-metrics.md)

返回 [索引](../README.md)

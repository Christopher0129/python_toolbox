# nats-py

`nats-py` 适合连接 NATS 消息系统，常见于低延迟发布订阅、请求响应和轻量服务通信。

## 安装

```bash
pip install nats-py
```

## 基本示例

```python
import asyncio
from nats.aio.client import Client as NATS


async def main():
    nc = NATS()
    await nc.connect("nats://127.0.0.1:4222")
```

## 关联阅读

- [NATS 专题](../topics/nats-messaging.md)
- [消息系统专题](../topics/message-systems.md)
- [实时通信专题](../topics/realtime-communication.md)

返回 [索引](../README.md)

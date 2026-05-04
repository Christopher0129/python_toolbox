# socket 模块

`socket` 是网络编程基础模块，常用于 TCP/UDP 通信、端口监听、简单客户端和服务端开发。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `socket.socket(family, type)` | 创建套接字 | `socket.socket(socket.AF_INET, socket.SOCK_STREAM)` |
| `bind((host, port))` | 绑定地址 | `sock.bind(("127.0.0.1", 9000))` |
| `listen(backlog)` | 开始监听 | `sock.listen(5)` |
| `accept()` | 接收客户端连接 | `conn, addr = sock.accept()` |
| `connect((host, port))` | 连接服务端 | `sock.connect(("127.0.0.1", 9000))` |
| `sendall(data)` | 发送全部数据 | `sock.sendall(b"hello")` |
| `recv(size)` | 接收数据 | `sock.recv(1024)` |
| `settimeout(sec)` | 设置超时 | `sock.settimeout(5)` |
| `close()` | 关闭连接 | `sock.close()` |

## TCP 服务端示例

```python
import socket

server = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
server.bind(("127.0.0.1", 9000))
server.listen(1)

conn, addr = server.accept()
data = conn.recv(1024)
conn.sendall(b"ok")
conn.close()
server.close()
```

## 常见概念

- `AF_INET`：IPv4
- `SOCK_STREAM`：TCP
- `SOCK_DGRAM`：UDP

## 提醒

- 网络通信一定要处理超时和异常
- 真实项目通常会在 `socket` 之上再封装协议或改用更高层框架

返回 [索引](../README.md)

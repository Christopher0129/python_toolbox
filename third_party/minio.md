# MinIO

`minio` 适合在 Python 中访问兼容 S3 协议的对象存储，常见于私有化环境和本地开发。

## 安装

```bash
pip install minio
```

## 基本示例

```python
from minio import Minio

client = Minio(
    "127.0.0.1:9000",
    access_key="minioadmin",
    secret_key="minioadmin",
    secure=False,
)
client.fput_object("demo", "logs/app.log", "app.log")
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `Minio(...)` | 创建对象存储客户端 |
| `fput_object(...)` | 上传本地文件 |
| `get_object(...)` | 下载或流式读取对象 |

## 关联阅读

- [对象存储专题](../topics/object-storage.md)
- [数据湖存储专题](../topics/data-lake-storage.md)
- [文件处理专题](../topics/file-processing.md)

返回 [索引](../README.md)

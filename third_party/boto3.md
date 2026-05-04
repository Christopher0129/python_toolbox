# boto3

`boto3` 是 Python 访问 AWS 服务的主力 SDK，最常见的是操作 S3、SQS、SNS、DynamoDB 和 STS。

## 安装

```bash
pip install boto3
```

## 基本示例

```python
import boto3

s3 = boto3.client("s3")
s3.upload_file("report.csv", "demo-bucket", "reports/report.csv")
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `boto3.client("s3")` | 创建低层 S3 客户端 |
| `boto3.resource("dynamodb")` | 使用资源对象访问部分 AWS 服务 |
| `upload_file(...)` | 上传本地文件到对象存储 |

## 适用场景

- S3 文件上传下载
- 消息与事件服务接入
- 云资源自动化脚本

## 关联阅读

- [对象存储专题](../topics/object-storage.md)
- [数据湖存储专题](../topics/data-lake-storage.md)
- [备份与归档专题](../topics/backup-archiving.md)

返回 [索引](../README.md)

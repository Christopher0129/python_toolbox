# uuid 模块

`uuid` 用于生成全局唯一标识，常见于订单号、对象 ID、临时文件名和分布式系统主键。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `uuid.uuid4()` | 生成随机 UUID | `uuid.uuid4()` |
| `uuid.uuid1()` | 基于时间和网卡信息 | `uuid.uuid1()` |
| `str(u)` | UUID 转字符串 | `str(uuid.uuid4())` |
| `u.hex` | 无连接符的十六进制形式 | `uuid.uuid4().hex` |

## 示例

```python
import uuid

order_id = uuid.uuid4()
print(order_id)
print(order_id.hex)
```

## 提醒

- 一般业务主键更常用 `uuid4()`
- 需要短 ID 或有序 ID 时，可能要结合业务做二次封装

## 扩展场景

- 订单号、任务号、文件上传名：常用 `str(uuid.uuid4())`
- 去掉连字符的短一点写法：`uuid.uuid4().hex`
- 临时文件名防冲突：`f"{uuid.uuid4().hex}.tmp"`
- 数据库主键如果直接用 UUID，要先确认字段类型和索引策略

## 示例模板

```python
import uuid

task_id = uuid.uuid4().hex
filename = f"report_{task_id}.json"
print(task_id, filename)
```

返回 [索引](../README.md)

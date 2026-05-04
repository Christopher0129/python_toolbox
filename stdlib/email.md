# email 模块

`email` 用于构造邮件内容、正文、HTML 和附件，通常配合 `smtplib` 发送邮件。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `EmailMessage()` | 创建邮件对象 | `msg = EmailMessage()` |
| `msg["Subject"] = ...` | 设置主题 | `msg["Subject"] = "Report"` |
| `msg["From"] = ...` | 设置发件人 | `msg["From"] = "a@example.com"` |
| `msg["To"] = ...` | 设置收件人 | `msg["To"] = "b@example.com"` |
| `set_content(text)` | 设置纯文本正文 | `msg.set_content("hello")` |
| `add_alternative(html, subtype="html")` | 添加 HTML 正文 | `msg.add_alternative("<b>hi</b>", subtype="html")` |
| `add_attachment(data, maintype=..., subtype=..., filename=...)` | 添加附件 | `msg.add_attachment(...)` |
| `as_string()` | 转为完整邮件文本 | `msg.as_string()` |

## 示例

```python
from email.message import EmailMessage

msg = EmailMessage()
msg["Subject"] = "Demo"
msg["From"] = "sender@example.com"
msg["To"] = "receiver@example.com"
msg.set_content("This is a plain text mail.")
```

## 配合 `smtplib` 发送

```python
import smtplib

with smtplib.SMTP("smtp.example.com", 587) as server:
    server.starttls()
    server.login("user", "password")
    server.send_message(msg)
```

## 提醒

- 邮件正文构造用 `email`，发送过程常用 `smtplib`
- 附件要明确 `maintype` 和 `subtype`

返回 [索引](../README.md)

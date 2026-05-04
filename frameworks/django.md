# Django 入门

`Django` 是功能完整的 Web 框架，自带 ORM、管理后台、路由、模板系统，更适合中大型项目。

## 安装

```bash
pip install django
```

## 常见命令

```bash
django-admin startproject mysite
python manage.py startapp blog
python manage.py makemigrations
python manage.py migrate
python manage.py runserver
```

## 关键组件

| 组件 | 用途 |
| --- | --- |
| `models.py` | 数据模型 |
| `views.py` | 业务处理和响应 |
| `urls.py` | 路由配置 |
| `admin.py` | 管理后台注册 |
| `templates/` | HTML 模板 |

## 模型示例

```python
from django.db import models

class Article(models.Model):
    title = models.CharField(max_length=200)
    content = models.TextField()
    created_at = models.DateTimeField(auto_now_add=True)
```

## 路由示例

```python
from django.urls import path
from . import views

urlpatterns = [
    path("", views.index),
]
```

## 适用场景

- 管理后台类系统
- 业务模型复杂的内容平台
- 需要 ORM、认证、权限、后台一体化的项目

返回 [索引](../README.md)

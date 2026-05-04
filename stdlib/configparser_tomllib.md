# configparser 与 tomllib

`configparser` 适合 INI 配置，`tomllib` 适合读取 `pyproject.toml` 这类 TOML 配置文件。

## `configparser` 常用 API

```python
from configparser import ConfigParser

config = ConfigParser()
config.read("app.ini", encoding="utf-8")
host = config["db"]["host"]
```

适合：

- 老项目配置
- 分节结构明显的配置文件

## `tomllib` 常用 API

Python 3.11+ 可直接读取 TOML。

```python
import tomllib

with open("pyproject.toml", "rb") as f:
    data = tomllib.load(f)

print(data["project"]["name"])
```

## 选择建议

| 场景 | 更适合 |
| --- | --- |
| 兼容旧式运维配置 | `configparser` |
| 现代 Python 项目元数据 | `tomllib` |

## 注意事项

- `tomllib` 只负责读取，不负责写入
- 读取 TOML 时通常用二进制模式 `rb`

## 关联阅读

- [json](./json.md)
- [pathlib](./pathlib.md)
- [pydantic](../third_party/pydantic.md)
- [配置管理专题](../topics/config-management.md)
- [打包与发布专题](../topics/packaging-release.md)

返回 [索引](../README.md)

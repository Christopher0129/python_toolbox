# zipfile 与 tarfile

`zipfile` 和 `tarfile` 适合压缩包读写、归档、批量分发和备份。

## `zipfile` 常用 API

| API | 说明 |
| --- | --- |
| `ZipFile(path, mode)` | 打开 ZIP 文件 |
| `write(filename)` | 写入文件 |
| `extractall(path)` | 解压全部 |
| `namelist()` | 列出压缩包内容 |

```python
from zipfile import ZipFile

with ZipFile("demo.zip", "w") as zf:
    zf.write("README.md")
```

## `tarfile` 常用 API

| API | 说明 |
| --- | --- |
| `tarfile.open(path, mode)` | 打开 tar 包 |
| `add(path)` | 添加文件或目录 |
| `extractall(path)` | 解压全部 |

```python
import tarfile

with tarfile.open("demo.tar.gz", "w:gz") as tf:
    tf.add("project")
```

## 适用场景

- 项目归档
- 日志打包
- 备份和离线传输

## 注意事项

- 解压来源不可信的压缩包时要谨慎，避免路径穿越风险
- 简单目录压缩也可直接用 `shutil.make_archive()`

## 关联阅读

- [shutil](./shutil.md)
- [pathlib](./pathlib.md)
- [文件处理专题](../topics/file-processing.md)
- [备份与归档专题](../topics/backup-archiving.md)

返回 [索引](../README.md)

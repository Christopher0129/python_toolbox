# shutil 模块

`shutil` 主要解决文件复制、目录复制、移动、删除目录树、压缩归档。

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `shutil.copy(src, dst)` | 复制文件内容和权限 | `shutil.copy("a.txt", "backup/a.txt")` |
| `shutil.copy2(src, dst)` | 连元数据一并复制 | `shutil.copy2("a.txt", "backup/a.txt")` |
| `shutil.copytree(src, dst, dirs_exist_ok=True)` | 复制整个目录树 | `shutil.copytree("src", "dst", dirs_exist_ok=True)` |
| `shutil.move(src, dst)` | 移动或重命名 | `shutil.move("a.txt", "archive/a.txt")` |
| `shutil.rmtree(path)` | 删除目录树 | `shutil.rmtree("build")` |
| `shutil.make_archive(base_name, format, root_dir)` | 生成压缩包 | `shutil.make_archive("out", "zip", "dist")` |

## 示例

```python
import shutil

shutil.copytree("project", "project_backup", dirs_exist_ok=True)
shutil.make_archive("project_backup", "zip", "project_backup")
```

## 提醒

- `rmtree()` 会删除整个目录树，使用前确认路径。
- 仅处理路径字符串时常配合 `pathlib.Path` 一起使用。

返回 [索引](../README.md)

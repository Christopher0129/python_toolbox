# 备份与归档专题

这个专题关注文件和项目数据的复制、归档、压缩和校验。

## 常用模块

| 模块 | 作用 |
| --- | --- |
| `shutil` | 复制、移动、归档 |
| `zipfile` / `tarfile` | 压缩包处理 |
| `hashlib` | 校验文件完整性 |
| `pathlib` | 路径管理 |

## 典型流程

1. 扫描目标目录
2. 复制到备份目录
3. 压缩归档
4. 计算摘要
5. 记录日志

## 关联阅读

- [shutil](../stdlib/shutil.md)
- [zipfile 与 tarfile](../stdlib/zipfile_tarfile.md)
- [hashlib](../stdlib/hashlib.md)
- [文件处理专题](./file-processing.md)

返回 [索引](../README.md)

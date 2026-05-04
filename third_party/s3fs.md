# s3fs

`s3fs` 适合把 S3 或兼容对象存储当作文件系统来访问，方便与 `pandas`、`pyarrow`、`dask` 等生态打通。

## 安装

```bash
pip install s3fs
```

## 基本示例

```python
import s3fs

fs = s3fs.S3FileSystem(anon=False)
with fs.open("demo-bucket/path/data.json", "r") as f:
    print(f.read())
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `S3FileSystem(...)` | 创建对象存储文件系统 |
| `open(...)` | 按文件接口读写对象 |
| `ls(...)` | 列出路径下的对象 |

## 关联阅读

- [对象存储专题](../topics/object-storage.md)
- [数据湖存储专题](../topics/data-lake-storage.md)
- [列式数据处理专题](../topics/columnar-data-processing.md)

返回 [索引](../README.md)

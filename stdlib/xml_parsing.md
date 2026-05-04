# xml.etree.ElementTree

`xml.etree.ElementTree` 适合解析和生成结构相对简单的 XML。

## 常用 API

| API | 说明 |
| --- | --- |
| `ET.parse(path)` | 解析 XML 文件 |
| `ET.fromstring(text)` | 从字符串解析 |
| `root.find(path)` | 找第一个节点 |
| `root.findall(path)` | 找全部节点 |
| `ET.Element(tag)` | 创建节点 |
| `ET.SubElement(parent, tag)` | 创建子节点 |

## 解析示例

```python
import xml.etree.ElementTree as ET

xml_text = "<users><user name='Tom' /></users>"
root = ET.fromstring(xml_text)
for user in root.findall("user"):
    print(user.get("name"))
```

## 生成示例

```python
import xml.etree.ElementTree as ET

root = ET.Element("users")
user = ET.SubElement(root, "user")
user.set("name", "Tom")
print(ET.tostring(root, encoding="unicode"))
```

## 适用场景

- 读取旧系统配置
- 解析简单数据交换格式
- 生成小型 XML 文档

## 注意事项

- 结构复杂、命名空间重度使用时，解析会变麻烦
- XML 来源不可信时要关注安全边界

## 关联阅读

- [json](./json.md)
- [re](./re.md)
- [文件处理专题](../topics/file-processing.md)

返回 [索引](../README.md)

# string 模块

`string` 提供字符串相关常量、简单格式化工具和模板字符串，适合做字符集合判断、占位替换和文本标准化。

## 常用常量

| 常量 | 说明 | 示例 |
| --- | --- | --- |
| `string.ascii_lowercase` | 小写字母 `a-z` | `string.ascii_lowercase` |
| `string.ascii_uppercase` | 大写字母 `A-Z` | `string.ascii_uppercase` |
| `string.ascii_letters` | 全部英文字母 | `string.ascii_letters` |
| `string.digits` | 数字字符 `0-9` | `string.digits` |
| `string.hexdigits` | 十六进制字符 | `string.hexdigits` |
| `string.punctuation` | 常见标点 | `string.punctuation` |
| `string.whitespace` | 空白字符 | `string.whitespace` |

## 常用 API

| API | 说明 | 示例 |
| --- | --- | --- |
| `string.capwords(s, sep=None)` | 每个单词首字母大写 | `string.capwords("hello world")` |
| `Template(template)` | 创建模板字符串对象 | `Template("Hello, $name")` |
| `Template.substitute(mapping)` | 严格替换占位符 | `tpl.substitute(name="Tom")` |
| `Template.safe_substitute(mapping)` | 缺少变量时不报错 | `tpl.safe_substitute(name="Tom")` |

## 示例

```python
import string
from string import Template

allowed = set(string.ascii_letters + string.digits + "_")
print("A" in allowed)

tpl = Template("Hello, $name. Score: $score")
print(tpl.substitute(name="Tom", score=95))
print(string.capwords("python knowledge base"))
```

## 适用场景

- 需要字符白名单时，直接用 `ascii_letters`、`digits`
- 需要简单模板替换时，`Template` 比手工拼接更清晰
- 复杂文本格式化仍优先使用 `f-string`

返回 [索引](../README.md)

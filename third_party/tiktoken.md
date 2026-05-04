# tiktoken

`tiktoken` 适合做 token 计数、分词预算和上下文窗口控制，常用于 LLM 提示构建与成本估算。

## 安装

```bash
pip install tiktoken
```

## 基本示例

```python
import tiktoken

enc = tiktoken.encoding_for_model("gpt-4o-mini")
tokens = enc.encode("hello world")
print(len(tokens))
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `encoding_for_model(...)` | 为指定模型获取编码器 |
| `get_encoding(...)` | 按编码名称加载编码器 |
| `enc.encode(...)` | 把文本编码为 token 序列 |
| `enc.decode(...)` | 把 token 序列还原为文本 |

## 使用建议

- 预算控制应在拼 prompt 前做，而不是请求失败后补救
- 估算时要把 system、tools、history 和检索片段一起算进去
- 对多模型路由场景，应分别按目标模型编码方式计数

## 关联阅读

- [Prompt 工程专题](../topics/prompt-engineering.md)
- [上下文工程专题](../topics/context-engineering.md)
- [成本治理专题](../topics/cost-governance.md)
- [RAG 流水线专题](../topics/rag-pipelines.md)

返回 [索引](../README.md)

# LiteLLM

`LiteLLM` 适合统一不同大模型供应商的调用接口，也常用于模型路由、回退和代理层封装。

## 安装

```bash
pip install litellm
```

## 基本示例

```python
from litellm import completion


resp = completion(
    model="gpt-4o-mini",
    messages=[{"role": "user", "content": "hello"}],
)
print(resp)
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `completion(...)` | 统一聊天补全调用 |
| `Router(...)` | 做模型路由与回退 |
| proxy 模式 | 统一接入多供应商模型服务 |

## 使用建议

- 适合多模型、多供应商环境下统一调用层
- 路由策略要结合成本、延迟、质量与配额一起设计
- 代理层不能只做透传，还应补观测、审计和限流

## 关联阅读

- [模型路由专题](../topics/model-routing.md)
- [LLM 网关专题](../topics/llm-gateway.md)
- [成本治理专题](../topics/cost-governance.md)
- [Prompt 工程专题](../topics/prompt-engineering.md)

返回 [索引](../README.md)

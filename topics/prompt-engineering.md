# Prompt 工程专题

这个专题关注提示词不是一段文案，而是输入契约、约束条件和执行策略的一部分。

## 适用场景

- 对话系统、提取系统、生成系统
- 模型输出格式需要稳定
- 需要多轮上下文和工具调用

## 常见主题

- system / user / tool 角色分层
- 输出格式约束
- few-shot 示例
- 拒答与边界控制
- 提示版本化

## 设计要点

- 提示应围绕任务目标、输入结构和失败模式设计
- 输出格式越关键，越要减少歧义并补校验层
- few-shot 要代表真实问题分布，而不是只挑顺手样例
- Prompt 变更应配评测集和回归验证

## 关联阅读

- [tiktoken](../third_party/tiktoken.md)
- [RAG 评测专题](./rag-evaluation.md)
- [工具调用专题](./tool-calling.md)
- [上下文工程专题](./context-engineering.md)

返回 [索引](../README.md)

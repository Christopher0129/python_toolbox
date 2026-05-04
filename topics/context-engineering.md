# 上下文工程专题

这个专题关注在有限上下文窗口里，如何选择、裁剪、排序和组织信息。

## 适用场景

- 多轮会话
- RAG 检索拼装
- Agent 带工具历史和执行轨迹

## 常见主题

- 上下文预算
- 历史摘要
- 检索片段排序
- 去重与压缩
- 工具结果裁剪

## 设计要点

- 先预算 token，再决定历史、检索和工具结果各占多少
- 越靠近当前任务的上下文越应优先保留
- 摘要不只是缩短长度，还会改变语义重点
- 对长上下文系统要补可观测性，看模型到底看到了什么

## 关联阅读

- [tiktoken](../third_party/tiktoken.md)
- [RAG 流水线专题](./rag-pipelines.md)
- [Prompt 工程专题](./prompt-engineering.md)
- [Agent 编排专题](./agent-orchestration.md)

返回 [索引](../README.md)

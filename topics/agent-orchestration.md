# Agent 编排专题

这个专题关注多步骤、带状态、可分支和可恢复的 Agent 执行流程。

## 适用场景

- 任务需要规划、执行、验证、修正多个阶段
- 需要多工具协作
- 希望把 Agent 行为从黑盒变成可追踪流程

## 常见主题

- 状态机
- 图编排
- 规划与执行分离
- 失败恢复
- 人工接管点

## 设计要点

- 复杂 Agent 更像 workflow，而不是一次模型调用
- 编排层应负责状态、边界和恢复，而不是把一切压给 prompt
- 工具调用、重试和人工接入要在图中有明确位置
- 观测上至少要能看到节点、输入、输出和失败原因

## 关联阅读

- [LangGraph](../third_party/langgraph.md)
- [工具调用专题](./tool-calling.md)
- [工作流编排专题](./workflow-orchestration.md)
- [Prompt 工程专题](./prompt-engineering.md)

返回 [索引](../README.md)

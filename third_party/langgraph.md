# LangGraph

`LangGraph` 适合组织多步骤 Agent / workflow，把状态、节点、条件分支和工具调用编排成明确图结构。

## 安装

```bash
pip install langgraph
```

## 基本示例

```python
from typing import TypedDict
from langgraph.graph import StateGraph


class State(TypedDict):
    text: str


def step(state: State):
    return {"text": state["text"] + "!"}


graph = StateGraph(State)
graph.add_node("step", step)
graph.set_entry_point("step")
graph.set_finish_point("step")
app = graph.compile()
print(app.invoke({"text": "hi"}))
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `StateGraph(...)` | 定义基于状态的执行图 |
| `add_node(...)` | 注册处理节点 |
| `add_edge(...)` | 连接执行路径 |
| `compile()` | 生成可运行图对象 |

## 使用建议

- 更适合需要显式状态和分支控制的 Agent 流程
- 先定义状态结构，再设计节点职责，会比先写节点再拼流程更稳
- 对长流程要补观测、重试边界和人工接管点

## 关联阅读

- [Agent 编排专题](../topics/agent-orchestration.md)
- [工具调用专题](../topics/tool-calling.md)
- [上下文工程专题](../topics/context-engineering.md)
- [工作流编排专题](../topics/workflow-orchestration.md)

返回 [索引](../README.md)

# Prefect

`Prefect` 适合用 Python 直接组织任务流、重试、调度和状态跟踪，偏向现代数据工作流编排。

## 安装

```bash
pip install prefect
```

## 基本示例

```python
from prefect import flow, task


@task
def add(a: int, b: int) -> int:
    return a + b


@flow
def demo():
    return add(1, 2)
```

## 关联阅读

- [工作流编排专题](../topics/workflow-orchestration.md)
- [数据管道专题](../topics/data-pipelines.md)
- [任务调度专题](../topics/task-scheduling.md)

返回 [索引](../README.md)

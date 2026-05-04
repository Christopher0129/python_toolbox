# Ray

`Ray` 适合把 Python 函数和对象扩展到分布式执行，也常见于模型训练、推理和任务并行。

## 安装

```bash
pip install ray
```

## 基本示例

```python
import ray

ray.init()


@ray.remote
def f(x):
    return x * 2
```

## 关联阅读

- [分布式计算专题](../topics/distributed-computing.md)
- [模型服务专题](../topics/model-serving.md)
- [异步编程专题](../topics/async-programming.md)

返回 [索引](../README.md)

# pytest-xdist

`pytest-xdist` 适合并行运行测试，提高大型测试集的反馈速度。

## 安装

```bash
pip install pytest-xdist
```

## 基本用法

```bash
pytest -n auto
```

## 常见能力

| 能力 | 说明 |
| --- | --- |
| `-n auto` | 自动按 CPU 并行 |
| `worker_id` fixture | 获取当前 worker 标识 |
| `--looponfail` | 文件变更后自动重跑失败测试 |

## 注意事项

- 并行测试要求用例之间不要共享脏状态
- `-s/--capture=no` 与 xdist 有限制
- session 级 fixture 在多 worker 下要特别设计

## 关联阅读

- [pytest](./pytest.md)
- [测试进阶专题](../topics/testing-advanced.md)
- [并行测试专题](../topics/parallel-testing.md)

返回 [索引](../README.md)

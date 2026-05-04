# typer

`typer` 适合快速构建现代 CLI，基于类型标注生成参数解析和帮助信息。

## 安装

```bash
pip install typer
```

## 最小示例

```python
import typer

app = typer.Typer()


@app.command()
def hello(name: str, times: int = 1):
    for _ in range(times):
        print(f"hello, {name}")


if __name__ == "__main__":
    app()
```

## 适用场景

- 多命令 CLI 工具
- 内部自动化平台脚本
- 希望比 `argparse` 更少样板代码的项目

## 使用建议

- 小脚本继续用 `argparse` 没问题
- 命令越来越多时，`typer` 会更清晰

## 关联阅读

- [argparse](../stdlib/argparse.md)
- [rich](./rich.md)
- [命令行自动化专题](../topics/automation-cli.md)

返回 [索引](../README.md)

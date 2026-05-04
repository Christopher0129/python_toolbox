# 安全基础专题

这个专题不是安全大全，而是帮助 Python 日常开发避开最常见的安全误区。

## 常见风险点

| 风险点 | 说明 |
| --- | --- |
| 密钥硬编码 | Token、密码直接写进代码 |
| 不安全随机数 | 用 `random` 生成安全 token |
| 反序列化风险 | 不可信输入直接 `pickle.load()` |
| 路径问题 | 拼接用户输入路径后直接操作 |
| 外部命令注入 | 不安全拼接 shell 命令 |

## 推荐做法

- 安全 token 用 `secrets`
- 校验文件路径和来源
- 外部命令优先传参数列表，不拼字符串
- 不信任外部 `pickle`

## 关联阅读

- [secrets 与 base64](../stdlib/secrets_base64.md)
- [subprocess](../stdlib/subprocess.md)
- [pickle](../stdlib/pickle.md)
- [文件处理专题](./file-processing.md)
- [配置管理专题](./config-management.md)

返回 [索引](../README.md)

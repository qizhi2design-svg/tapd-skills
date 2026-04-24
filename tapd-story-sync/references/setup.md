# TAPD 安装说明

## 触发条件

当 `tapd info` 命令本身无法执行时，说明 TAPD CLI 还没有全局安装。

## 未安装时的处理

如果没有安装，先执行：

```bash
npm install -g @huangqz/tapd-cli
```

## 常见问题

- 如果命令不存在，优先检查是否执行过 `npm install -g @huangqz/tapd-cli`
- 安装后优先重新执行 `tapd info`，不要直接跳过状态检查

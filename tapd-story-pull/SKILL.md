---
name: tapd-story-pull
description: 当用户希望通过 tapd CLI 将 TAPD 需求拉取到本地 Markdown 文件时使用。
---

# TAPD 需求拉取

将 TAPD 需求拉取为本地 Markdown 文件。

## 使用场景

- 用户提供了 TAPD 需求 ID
- 用户要求拉取、下载或同步 TAPD 需求到本地

## 交互命令提示

- 如果识别为交互命令场景，或不确定参数、子命令、输入方式，先执行对应帮助命令
- 根命令可用 `tapd -h`
- 子命令也支持 `-h`，例如：
  - `tapd story -h`
  - `tapd story pull -h`

## 执行步骤

1. 先执行：

```bash
tapd info
```

2. 如果 `tapd info` 命令无法执行，读取：
   - `references/setup.md`
3. 如果 `tapd info` 显示未授权，读取：
   - `references/auth.md`
4. 如果 `tapd info` 显示已授权但当前空间或默认创建人未设置，读取：
   - `references/init.md`
5. 获取 TAPD 需求 ID。
6. 执行：

```bash
tapd story pull <story-id>
```

7. 如果用户希望输出到指定路径，执行：

```bash
tapd story pull <story-id> <output-file>
```

8. 验证：
   - Markdown 文件已生成
   - 图片已下载到 `assets/` 目录

## 注意事项

- CLI 会把 TAPD HTML 转成 Markdown
- 图片链接会被改写为本地相对路径

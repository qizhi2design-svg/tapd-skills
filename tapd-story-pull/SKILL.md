---
name: tapd-story-pull
description: 当用户希望通过 tapd CLI 将 TAPD 需求拉取到本地 Markdown 文件时使用。
---

# TAPD 需求拉取

将 TAPD 需求拉取为本地 Markdown 文件。

## 使用场景

- 用户提供了 TAPD 需求 ID
- 用户要求拉取、下载或同步 TAPD 需求到本地

## 执行步骤

1. 获取 TAPD 需求 ID。
2. 执行：

```bash
tapd story pull <story-id>
```

3. 如果用户希望输出到指定路径，执行：

```bash
tapd story pull <story-id> <output-file>
```

4. 验证：
   - Markdown 文件已生成
   - 图片已下载到 `assets/` 目录

## 注意事项

- CLI 会把 TAPD HTML 转成 Markdown
- 图片链接会被改写为本地相对路径

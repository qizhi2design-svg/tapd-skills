---
name: tapd-story-create
description: 当用户希望通过 tapd CLI 从本地 Markdown 文件创建新的 TAPD 需求时使用。
---

# TAPD 需求创建

从本地 Markdown 文件创建 TAPD 需求。

## 使用场景

- 用户要求创建 TAPD 需求
- 用户希望把新的 Markdown 需求上传到 TAPD
- Markdown 文件里还没有 `tapd_id`

## 执行步骤

1. 读取目标 Markdown 文件。
2. 确认这是新需求：
   - frontmatter 中没有 `tapd_id`
3. 执行：

```bash
tapd story create <markdown-file>
```

4. 验证：
   - 命令执行成功
   - `tapd_id` 已写回文件

## 注意事项

- CLI 支持本地图片和 Mermaid 自动上传
- 缺少 `iteration_id` 或 `creator` 时可能会触发交互选择

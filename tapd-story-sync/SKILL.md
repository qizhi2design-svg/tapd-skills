---
name: tapd-story-sync
description: 当用户希望通过 tapd CLI 将本地 Markdown 需求同步回 TAPD，包括更新已存在的需求时使用。
---

# TAPD 需求同步

将本地 Markdown 需求同步到 TAPD。

## 使用场景

- 用户要求同步、更新、推送修改，或重新提交需求
- Markdown 文件里已经有 `tapd_id`
- 目标是让 TAPD 和本地 Markdown 保持一致

## 执行步骤

1. 读取 Markdown 文件。
2. 确认 frontmatter 中存在 `tapd_id`。
3. 执行：

```bash
tapd story update <markdown-file>
```

4. 验证：
   - 更新执行成功
   - `updated_at` 已写回本地文件

## 注意事项

- 如果原来的 `tapd_id` 在 TAPD 中不存在，CLI 会自动重新创建需求
- 同步过程中会处理本地图片和 Mermaid 图表

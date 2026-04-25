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

## 交互命令提示

- 如果识别为交互命令场景，或不确定参数、子命令、输入方式，先执行对应帮助命令
- 根命令可用 `tapd -h`
- 子命令也支持 `-h`，例如：
  - `tapd story -h`
  - `tapd story update -h`

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
5. 读取 Markdown 文件。
6. 确认 frontmatter 中存在 `tapd_id`。
7. 执行：

```bash
tapd story update <markdown-file>
```

8. 验证：
   - 更新执行成功
   - `updated_at` 已写回本地文件

## 注意事项

- 如果原来的 `tapd_id` 在 TAPD 中不存在，CLI 会自动重新创建需求
- 同步过程中会处理本地图片和 Mermaid 图表

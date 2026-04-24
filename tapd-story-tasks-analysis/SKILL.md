---
name: tapd-story-tasks-analysis
description: 当用户希望分析某个 TAPD 需求下的任务排期、人员分布、工时和风险情况时使用。
---

# TAPD 需求任务分析

分析指定 TAPD 需求下的任务情况。

## 使用场景

- 用户要求分析某个需求的任务排期
- 用户想判断需求推进是否正常
- 用户希望从任务角度识别延期风险、负责人分布或测试缺口

## 执行步骤

1. 先执行：

```bash
tapd info
```

2. 如果 `tapd info` 命令无法执行，读取：
   - `references/setup.md`
3. 如果 `tapd info` 显示未授权，读取：
   - `references/auth.md`
4. 如果 `tapd info` 显示已授权但当前空间未设置，读取：
   - `references/init.md`
5. 再确认分析对象：
   - 用户直接给了 `story_id`，直接使用
   - 用户给的是本地 Markdown 文件，先读取 frontmatter 中的 `tapd_id`
6. 执行：

```bash
tapd story get <story-id>
tapd story tasks <story-id> --all
```

7. 读取：
   - `references/analysis-output.md`
8. 按规范输出：
   - 分析对象
   - 总览
   - 关键汇总
   - 风险与问题
   - 建议动作
   - 明细

## 分析重点

- 进行中任务是否过少，导致整体推进偏慢
- 未开始任务是否大量堆积在后段排期
- 测试任务是否明显晚于开发任务
- 是否存在负责人过于集中或无人负责的情况
- 工时、时间窗口、任务状态是否匹配

## 注意事项

- 不要直接复制原始命令输出
- 明细默认按 `进行中 / 未开始 / 已完成` 分组
- 如果任务数量很多，只保留关键任务和异常任务

---
name: tapd-iteration-analysis
description: 当用户希望分析某个 TAPD 迭代的整体推进情况，包括需求分布、任务状态、时间窗口和风险时使用。
---

# TAPD 迭代分析

分析指定 TAPD 迭代的整体情况。

## 使用场景

- 用户要求分析某个迭代的健康度
- 用户希望查看迭代下需求和任务的整体推进情况
- 用户需要输出迭代周报、评审摘要或项目推进结论

## 交互命令提示

- 如果识别为交互命令场景，或不确定参数、子命令、输入方式，先执行对应帮助命令
- 根命令可用 `tapd -h`
- 子命令也支持 `-h`，例如：
  - `tapd iteration -h`
  - `tapd iteration tasks -h`
  - `tapd iteration get -h`

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
5. 获取迭代 ID：
   - 用户明确提供时直接使用
   - 用户没有提供时，可先执行 `tapd iteration list` 辅助确认
6. 执行：

```bash
tapd iteration get <iteration-id>
tapd iteration tasks <iteration-id> --all
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

- 迭代时间窗口与任务排期是否匹配
- 需求状态是否集中卡在某个阶段
- 已完成、进行中、未开始任务的比例是否健康
- 是否存在测试滞后、临近截止仍未开始的任务
- 研发人员分布是否过度集中

## 注意事项

- 这是整体迭代分析，不只看需求，也要结合任务情况
- 如果用户只想看迭代下的需求分析，优先使用 `tapd-iteration-stories-analysis`
- 不用表格，直接给结论和分组清单

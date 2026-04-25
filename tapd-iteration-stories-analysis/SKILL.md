---
name: tapd-iteration-stories-analysis
description: 当用户希望分析某个 TAPD 迭代下的需求分布、需求状态和推进重点时使用。
---

# TAPD 迭代下需求分析

分析指定迭代中的需求情况。

## 使用场景

- 用户要求查看某个迭代下有哪些需求
- 用户希望分析迭代下需求状态分布
- 用户想识别哪些需求需要优先跟进或继续下钻任务

## 交互命令提示

- 如果识别为交互命令场景，或不确定参数、子命令、输入方式，先执行对应帮助命令
- 根命令可用 `tapd -h`
- 子命令也支持 `-h`，例如：
  - `tapd iteration -h`
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
   - 用户没有提供时，可先执行 `tapd iteration list`
6. 执行：

```bash
tapd iteration get <iteration-id>
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

- 需求总量是否与迭代容量匹配
- 需求状态分布是否合理
- 是否有需求长期停留在前置阶段
- 哪些需求应继续查看任务详情

## 注意事项

- 这个 skill 只聚焦迭代下的需求，不展开任务排期
- 如果用户需要任务维度分析，继续调用 `tapd-iteration-analysis` 或 `tapd-story-tasks-analysis`
- 明细默认按需求状态分组

# TAPD Skills

这个目录按独立 skills 仓库的方式组织，可直接供 skills 安装器扫描。

## 目录结构

```text
skills/
  README.md
  index.json
  tapd-login/
    SKILL.md
  tapd-story-create/
    SKILL.md
  tapd-story-pull/
    SKILL.md
  tapd-story-sync/
    SKILL.md
  tapd-story-tasks-analysis/
    SKILL.md
    references/
      analysis-output.md
  tapd-iteration-analysis/
    SKILL.md
    references/
      analysis-output.md
  tapd-iteration-stories-analysis/
    SKILL.md
    references/
      analysis-output.md
```

## 已包含的 skills

- `tapd-login`：登录 TAPD CLI，或清理本地认证信息
- `tapd-story-create`：从本地 Markdown 创建 TAPD 需求
- `tapd-story-pull`：把 TAPD 需求拉取到本地 Markdown
- `tapd-story-sync`：将本地 Markdown 需求同步回 TAPD
- `tapd-story-tasks-analysis`：分析单个需求下的任务情况
- `tapd-iteration-analysis`：分析单个迭代的整体推进情况
- `tapd-iteration-stories-analysis`：分析单个迭代下的需求分布与状态

## 输出规范

分析类 skill 各自内置 `references/analysis-output.md`，安装单个 skill 时也能正常工作。

## 安装约定

该目录按下面的扫描规则组织：

```text
skills/*/SKILL.md
```

如果后续要把它拆成独立 GitHub 仓库，保持这个结构不变即可。

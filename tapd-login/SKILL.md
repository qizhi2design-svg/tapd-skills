---
name: tapd-login
description: 当用户需要登录本地 TAPD CLI、获取 TAPD 个人令牌或应用凭证、配置认证，或通过 logout 清理本地认证信息时使用。
---

# TAPD 登录

当用户需要为本地 TAPD CLI 配置或清理认证信息时使用此 skill。

## 使用场景

- 首次配置 TAPD CLI
- `tapd` 出现认证错误
- 用户要求登录、配置 token、绑定凭证或退出登录

## 推荐认证方式

优先引导用户使用 **TAPD 个人令牌**，只有在用户明确需要开放应用接入时，再引导走应用凭证流程。

## 个人令牌获取流程（推荐）

当用户没有 `TAPD_ACCESS_TOKEN` 时，引导用户按下面步骤获取：

1. 打开 TAPD 个人令牌页面：

```text
https://www.tapd.cn/personal_settings/index?tab=personal_token
```

2. 点击 **“创建个人访问令牌”**
3. 按需要填写名称或用途说明
4. 创建后复制令牌

重要提醒：

- 令牌通常只显示一次
- 必须让用户当场保存好
- 后续若丢失，只能重新创建

拿到令牌后，再继续执行登录命令。

## 应用凭证获取流程（备选）

如果用户明确要使用开放应用模式，引导用户：

1. 在 TAPD 开放平台中创建一个应用
2. 获取以下信息：
   - `client_id`
   - `client_secret`
   - `company_id`
3. 确认这些值可用于 CLI 登录后，再继续执行登录命令

如果用户并不确定该选哪种方式，默认回到个人令牌方案，不要优先推荐应用凭证。

## 执行步骤

1. 先确认用户是否已经拿到凭证：
   - 个人令牌模式：需要 `TAPD_ACCESS_TOKEN` 和一个 `workspace_id`
   - 应用凭证模式：需要 `client_id`、`client_secret`、`company_id`
2. 如果用户还没有凭证，先引导其完成上面的获取流程，不要急着发起需求创建或同步。
3. 如果用户需要登录，执行：

```bash
tapd login
```

4. 如果用户已经提供了参数，优先使用非交互方式：

```bash
tapd login --mode personal --personal-token <token> --workspace-id <workspace-id>
tapd login --mode app --client-id <id> --client-secret <secret> --company-id <company-id>
```

5. 如果用户要清理本地认证信息，执行：

```bash
tapd logout
```

## 注意事项

- `tapd login` 会把凭证写入 `.tapd/credentials.json`
- 个人令牌模式会同时验证一个 workspace
- `tapd logout` 会删除本地认证文件
- 用户没有凭证时，先引导获取凭证，再继续创建需求、同步需求或拉取需求

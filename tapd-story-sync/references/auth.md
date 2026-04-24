# TAPD 认证说明

## 触发条件

当 `tapd info` 显示“当前未授权”时，进入这个文档。

## 未认证时的处理

如果还没有认证，先执行：

```bash
tapd login
```

## 个人令牌获取

如果用户没有 TAPD 个人令牌，先引导用户到下面页面创建：

```text
https://www.tapd.cn/personal_settings/index?tab=personal_token
```

重点提醒：

- 个人令牌通常只展示一次
- 需要当场保存

## 常见问题

- 如果出现认证失败，优先引导用户重新执行 `tapd login`
- 登录后优先重新执行 `tapd info`，确认状态已变为“当前已授权”

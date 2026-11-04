# 烟草网络学院 · 必修截止日日历

给手机日历订阅用的 iCalendar 文件，由 `tobacco-mooc-study` 生成。

## 多用户：每人一个地址

订阅地址按用户名区分，互不覆盖：

```
https://gandli.github.io/mooc-calendar/mooc-<用户名>.ics
```

已有：

| 用户 | 订阅地址 |
| --- | --- |
| gandli | https://gandli.github.io/mooc-calendar/mooc-gandli.ics |
| demo | https://gandli.github.io/mooc-calendar/mooc-demo.ics |

两种隔离方式：

1. **同一个仓库多文件**（家人/同事共用一个站点）：
   `CAL_USER=alice scripts/publish_calendar.sh` → `…/mooc-alice.ics`
2. **各自 fork 仓库**（不同 GitHub 账号，完全隔离，推荐）：
   把本仓库 fork 到自己账号，然后
   `CAL_REPO=<你的账号>/mooc-calendar scripts/publish_calendar.sh`
   → 地址自动变成 `https://<你的账号>.github.io/mooc-calendar/mooc-<用户名>.ics`

## 订阅

手机日历 →「添加日历订阅 / 添加账户 → 其他 → 添加已订阅的日历」，填上表对应地址。
iOS 用 `webcal://gandli.github.io/mooc-calendar/mooc-gandli.ics` 也会自动识别。

## 内容

只包含**必修任务的截止日**：一条全天事件 + 提前 3 天提醒，摘要形如
`【截止】必修 · 必修任务 #1（还差 7 天）`。默认对课程名脱敏（公开仓库），
本地生成时可用 `MASK_TITLES=0` 保留真实课程名。

## 这里没有凭据

文件由本地脚本生成后推送，**不包含** access_token、密码或会话文件。
生成脚本在 `tobacco-mooc-study` 仓库（私有）。

## 刷新

截止日与剩余天数会变，需定期重新生成并推送；主仓库的
`scripts/publish_calendar.sh` 会做「生成 → 推送 → 等 Pages 发布」。

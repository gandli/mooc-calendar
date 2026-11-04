# 烟草网络学院 · 必修截止日日历

给手机日历订阅用的 iCalendar 文件，由 `tobacco-mooc-study` 生成。

## 订阅地址

```
https://gandli.github.io/mooc-calendar/mooc.ics
```

手机日历里选「添加日历订阅 / 添加账户 → 其他 → 添加已订阅的日历」，填上面的地址即可。
iOS 用 `webcal://gandli.github.io/mooc-calendar/mooc.ics` 也会自动识别。

## 内容

只包含**必修任务的截止日**：一条全天事件 + 提前 3 天提醒。
事件摘要形如 `【截止】必修 · 课程名（还差 7 天）`。

## 这里没有凭据

文件由本地脚本生成后推送，**不包含** access_token、密码或会话文件。
生成脚本在 `tobacco-mooc-study` 仓库（私有）。

## 刷新

截止日与剩余天数会变，需定期重新生成并推送；主仓库的
`scripts/publish_calendar.sh` 会做「生成 → 推送 → 等 Pages 发布」。

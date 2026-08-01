# 初始化与数据边界

只在首次运行或用户要求重新配置时读取本文件。

具体提问顺序必须读取并执行 [onboarding.md](onboarding.md)。不要只创建空模板后直接进入正常运行。

## 导航

- [初始化覆盖范围](#初始化覆盖范围)
- [settings.md](#settingsmd)
- [routines.md](#routinesmd)
- [goals.md](#goalsmd)
- [xp.md](#xpmd)
- [目录安全](#目录安全)
- [完成初始化](#完成初始化)

## 初始化覆盖范围

通过固定七问补齐：

- 起床、睡觉、不可安排任务的生活时间和固定承诺、时区
- 北极星、理想生活与目标列表
- 1～3 个活跃目标及完成证据
- 日常固定项和晚间惯例
- iPhone 日历是否已同步 Codex 可访问的账号、使用哪个日历及可选分类颜色
- 日报归档位置：本地或 Obsidian
- XP 默认值确认与最终启用

运行目录默认 `~/.lifeos/`；日报详略、签名语气等偏好使用默认值，用户后续可修改。

不要求填写姓名、地址、收入、健康、关系或账号标识。涉及敏感目标时允许使用范围、模糊描述或“未记录”。

## settings.md

创建：

```markdown
---
onboarding_complete: false
onboarding_step: question_1
onboarding_question_total: 7
tutorial_seen: false
profile_status: partial
pending_fields: []
timezone: <IANA timezone>
wake_time: <HH:MM 或未记录>
sleep_time: <HH:MM 或未记录>
protected_time_blocks:
  - <吃饭、通勤、照护、休息或其他不可排任务时间>
calendar_required_for_full_mode: true
calendar_enabled: false
calendar_status: pending
calendar_id: primary
daily_review_dir: daily-reviews
daily_report_destination: local
obsidian_vault: <未配置>
obsidian_archive_dir: <未配置>
routine_xp: 10
evening_routine_xp: 10
goal_progress_xp: 20
goal_result_xp: 30
goal_breakthrough_xp: 40-50
challenge_xp: 5
completion_emoji: 🎉
incomplete_emoji: ❌
report_detail: standard
quote_enabled: true
quote_tone: constructive
sensitive_detail_mode: minimal
---

# Life OS 设置

## 日历 颜色

未配置。保留事件原色。

## 可选功能

- Obsidian 归档：关闭
- 练习记录：关闭
- 目标进度总览：开启
```

不要把密码、Token、Cookie 或连接凭据写进此文件。

## routines.md

创建：

```markdown
# 我的惯例

## 日常固定项

- [ ] <固定项 1>
- [ ] <固定项 2>
- [ ] <固定项 3>

## 晚间惯例

- [ ] <晚间项 1>
- [ ] <晚间项 2>

## 可选练习记录

- 状态：关闭
- 名称：<例如语言练习、写作练习或技能训练>
```

这些项目由用户定义。技能 不内置任何特定饮食、平台发布、品牌工作或私人生活习惯。

## goals.md

创建：

```markdown
# Life OS 目标背景

## 北极星

待确认。

## 当前阶段

待确认。

## 当前背景与约束

- 会影响排期的角色或项目：未记录
- 固定承诺与时间边界：未记录
- 当前资源：未记录
- 当前限制：未记录

## 活跃目标

### G1：<目标名称>

- 当前状态：未记录
- 理想状态：待确认
- 下一里程碑：待确认
- 成功证据：待确认
- 当前瓶颈：未记录

## 目标库

暂无。

## 更新规则

- 只有用户明确确认的变化才能写入
- 当天事实先进入日报
- 更新前创建备份
```

## xp.md

创建：

```markdown
# Life OS XP 日志

- 累计 XP：0
- 当前等级：Lv.1
- 当前连击：0 天
```

## 目录安全

- 创建 `projects/` 与 `daily-reviews/`
- 初始化 `goals-overview.md`（目标进度总览页）
- 初始化 CSS Snippet：`lifeos-overview.css`（可视化样式）
- 运行数据目录不得位于 技能 仓库内部
- 如果用户选择了已有目录，先检查同名文件和写入冲突
- 不覆盖任何既有文件；发现冲突时报告并等待用户决定

## 完成初始化

完成 `onboarding.md` 的七问后：

1. 展示一份不含秘密值的配置摘要
2. 询问用户确认启用、修改或使用默认值
3. 无论资料是否完整，只要七问均已回应或跳过，就写入：

```yaml
onboarding_complete: true
onboarding_step: complete
tutorial_seen: true
profile_status: <complete 或 partial>
pending_fields:
  - <使用中需要慢慢补充的字段>
```

4. 用户要求修改时回到对应 `Question N/7`，不必重做全部初始化
5. 初始化完成后，按真实使用场景逐项补充 `pending_fields`，不要重新运行全部七问

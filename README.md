# LifeOS 2026/skill

🎉 欢迎使用 LifeOS！

> **让 AI 运营你的一天。**
>
> 把长期目标压缩成今天最重要的三件事，安排进真实日历，晚上依据结果和证据复盘。

[![Version](https://img.shields.io/github/v/release/Christine527/LifeOS-2026-skill?style=flat-square&label=version)](https://github.com/Christine527/LifeOS-2026-skill/releases)
[![Type](https://img.shields.io/badge/type-Codex%20Skill-2563EB.svg?style=flat-square)](lifeos/SKILL.md)

**支持：Codex。必需工具：Google 日历；建议配合 Obsidian。**

LifeOS 2026/skill 由 [你的好友谢谢](https://github.com/Christine527) 创建。它是一套面向普通 Codex 用户的轻量人生行动系统：重点不是替你管理知识库，而是帮助你把长期目标变成今天的行动，并在晚上用结果与证据核验。

[快速开始](#快速开始) · [核心闭环](#核心闭环) · [能力一览](#能力一览) · [查看效果](#查看效果) · [安装](#安装) · [项目结构](#项目结构) · [作者](#作者)

## LifeOS 解决什么问题

| 真实处境 | LifeOS 会做什么 |
| --- | --- |
| 长期目标很多，但每天不知道先做什么 | 从活跃目标与当前瓶颈中筛选最多三项高杠杆行动 |
| 列了计划，却没有进入真实时间 | 读取 Google 日历，安排时间块，并在修改后回读核验 |
| 晚上只记得“忙了一天”，说不清推进了什么 | 区分行动、结果、证据与卡点，生成日报和次日重点 |
| 看不见自己是否正在接近目标 | 用网页端与 Obsidian 端的「目标进度总览」呈现当前主线 |
| 习惯和行动缺少持续反馈 | 保守结算 XP，同时避免用分数替代真实结果 |

## 快速开始

安装完成后，直接对 Codex 说：

```text
LifeOS 新手入门
```

LifeOS 会用七个可跳过、可续接的问题确认作息、时区、当前主线、活跃目标、年龄与目标年龄、真实习惯、日历、日报位置和 XP 偏好。

完成首次配置后，可以直接说：

```text
开始晨间惯例
把今天最重要的三件事安排进日历
开始晚间复盘
查看目标进度总览
```

## 核心闭环

```text
长期目标与当前瓶颈
        ↓
晨间筛选最多三项高杠杆行动
        ↓
写入真实日历并执行
        ↓
晚间核对行动、结果、证据与卡点
        ↓
生成日报、结算 XP、更新目标进度
        ↓
把真实结果带入明天
```

LifeOS 的核心不是让计划看起来完整，而是让每天的重要行动留下可以核验的结果或证据。

## 能力一览

| Skill | 主要作用 | 常见产出 |
| --- | --- | --- |
| `lifeos` | 主入口与动态导航 | 识别当前需求并进入正确流程 |
| `lifeos-onboarding` | 七问首次配置与重新配置 | 当前用户自己的作息、目标、习惯和工具设置 |
| `lifeos-morning` | 晨间规划与当日聚焦 | 最多三项高杠杆行动、最小证据与 XP 预估 |
| `lifeos-calendar` | 日历执行与验证 | 读取、安排、修改并回读核验真实日程 |
| `lifeos-evening` | 晚间惯例与每日收尾 | 行动、结果、证据、卡点和明日重点 |
| `lifeos-review` | 日报、洞察与事实归档 | 每日复盘、洞察、练习记录和可靠事实 |
| `lifeos-goals` | 目标因果结构与进度总览 | 最多三个活跃目标与「目标进度总览」 |
| `lifeos-xp` | XP 结算与等级维护 | 保守计分、等级、连击与防重复记录 |
| `lifeos-project` | 复杂项目规格与验收 | 范围、完成标准、结果证据与下一步 |
| `lifeos-doctor` | 只读系统体检 | 配置、日历、备份、隐私和重复写入风险报告 |

此外，仓库内含 300 条已整理的名人金句，可用于每日签名与复盘。

## 查看效果

- [日报结构与排版说明](lifeos-review/references/daily-report.md)
- [目标进度总览说明](lifeos-goals/references/goals-overview.md)
- [目标进度总览网页预览](lifeos-goals/references/goals-overview-preview.html)

日报结构包含「今日签名」，并在结尾提供「查看目标进度总览」入口。目标总览同时保留网页端与 Obsidian 端的锁定版式。

## 安装

### Codex 手动安装

1. 打开 [最新 Release](https://github.com/Christine527/LifeOS-2026-skill/releases/latest)，下载 ZIP。
2. 解压后，将其中 10 个 `lifeos*` Skill 文件夹分别复制到 Codex Skills 目录：`~/.codex/skills/`。Windows 对应 `%USERPROFILE%\.codex\skills\`。
3. 重新打开 Codex，然后输入 `LifeOS 新手入门`。

安装后的结构应类似：

```text
~/.codex/skills/
├── lifeos/
├── lifeos-onboarding/
├── lifeos-morning/
├── lifeos-calendar/
├── lifeos-evening/
├── lifeos-review/
├── lifeos-goals/
├── lifeos-xp/
├── lifeos-project/
└── lifeos-doctor/
```

## 数据与隐私

公开仓库只保留系统运行部分，不携带作者或其他用户的个人运行数据。

首次使用时，LifeOS 会通过自然对话确认年龄、目标年龄、习惯、作息、日历和归档位置。页面中的年龄、目标年龄、习惯与目标均为示例，不能直接视为新用户的真实信息。

## 项目结构

```text
LifeOS-2026-skill/
├── lifeos/             # 主入口与动态导航
├── lifeos-onboarding/  # 七问首次配置
├── lifeos-morning/     # 晨间规划
├── lifeos-calendar/    # 日历执行与回读验证
├── lifeos-evening/     # 晚间复盘
├── lifeos-review/      # 日报与洞察
├── lifeos-goals/       # 目标系统与进度总览
├── lifeos-xp/          # XP 与等级维护
├── lifeos-project/     # 项目规格与验收
└── lifeos-doctor/      # 系统体检
```

## 作者

作者：[你的好友谢谢](https://github.com/Christine527)（GitHub：[@Christine527](https://github.com/Christine527)）

教程与公开资料署名：来源 @你的好友谢谢。

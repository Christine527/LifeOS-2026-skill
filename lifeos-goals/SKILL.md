---
name: lifeos-goals
description: LifeOS 轻量 TELOS（目标因果结构）与目标进度总览系统。建立当前状态、理想状态、使命、问题、目标、策略和项目的因果关系，管理最多三个活跃目标，并以锁定版式生成、更新或修复网页与 Obsidian 的【目标进度总览】。用户说"梳理人生目标""更新目标""现在最重要什么""目标太多""找当前主线""为什么目标没推进""查看目标进度总览""同步到 Obsidian"或要求修复总览排版时使用。
---

# LifeOS 目标系统

让每天的重点来自当前主线和真实瓶颈，而不是平均照顾全部愿望。

完整读取 [references/telos.md](references/telos.md)。

## 工作流

1. 读取 `goals.md` 和最近能够说明当前状态的事实。
2. 区分用户原话、已确认事实、推断和未知。
3. 建立或更新"当前状态 → 理想状态 → 问题 → 目标 → 挑战 → 策略 → 项目"的因果关系。
4. 同时只保留最多三个活跃目标；其他目标进入目标库，不删除。
5. 为每个活跃目标写明下一里程碑、成功证据和当前瓶颈。
6. 展示拟修改内容，经用户确认并备份后才更新 `goals.md`。
7. 如需生成、更新或修复目标进度总览：
   - **前置检查（优先执行）**：完整读取 [references/goals-overview.md](references/goals-overview.md) 的「CSS Snippet」章节，按「生成前强制自检清单」主动引导用户完成 `lifeos-overview.css` 的文件命名核对、安装位置确认和 Obsidian Snippet 开关启用。用户明确跳过才使用 Plan B inline style 兜底。
   - 完整读取 [references/goals-overview-layout-lock.md](references/goals-overview-layout-lock.md) 与 [references/goals-overview.md](references/goals-overview.md)，使用 [assets/goals-overview-obsidian-template.md](assets/goals-overview-obsidian-template.md) 的结构写入 Obsidian。
8. 首次为一个用户生成总览，或相关字段仍为待确认时，先通过自然对话确认人生时间线、习惯、目标、Season/XP 与今日主线；只写入用户确认的数据。

## 判断原则

- 北极星保持相对稳定，不能因一天情绪静默改变。
- 当天行动和一次性结果先进入日报，不直接被提升为长期规律。
- 重复事实或明确决策才能改变策略。
- 目标不清楚时只追问会改变执行或验收的一项信息。
- 不把收入、健康或关系等敏感信息要求成精确数字。

## 目标进度总览（goals-overview.md）

固定版式（模块顺序不可更改）：

1. 年度进度 → 2. Season 主题卡片 → 3. 人生时间线 → 4. 习惯打卡矩阵 → 5. 今日主线 → 6. 人生任务

设计系统详见 [references/goals-overview.md](references/goals-overview.md)：
- 视觉真源：[references/goals-overview-preview.html](references/goals-overview-preview.html)。Obsidian 页面必须与其保持同构，不得替换成旧版仪表盘
- 色彩：暖米白背景 `#F7F5F2`、砖红强调 `#B94A3D`、深色 Season 卡 `#2D2D3A`
- 字体：数字 56px/300、时间线数字 32px/300、标签全大写+字符间距
- SVG 弧线：浅碗形/U形（两端朝上），总长度 380px，`stroke-dashoffset = 380 - (380 × pct / 100)`
- CSS Snippet：参见 `references/lifeos-overview.css`

### 版式与数据边界

- 网页预览、Obsidian 模板、六个模块顺序、组件层级、类名和 CSS 均为锁定版式；更新个人数据时不得改动。
- 预览中的年龄、目标年龄、习惯、目标、XP 和任务均为演示数据，不是任何用户的默认配置。
- 新用户首次生成总览时，用自然、可一次语音回答的分组对话确认数据；不要把演示值或上一位用户的数据带入。
- 出生日期或当前年龄、目标年龄、习惯等可以跳过；跳过时显示“未记录 / 未确认”，不得猜测。
- 现有用户的数据未经本人确认时保持原状或标记待确认，不擅自替他修正。

## 交付

根据需求交付以下一种：

- 当前主线与最大差距
- 最多三个活跃目标
- 目标因果地图
- 目标更新差异
- 当前最值得验证的瓶颈或策略
- 目标进度总览（按固定版式生成到 Obsidian）

用户只想讨论时不修改文件。

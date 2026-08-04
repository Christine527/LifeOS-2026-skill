# Life OS 目标进度总览

由 LifeOS 自动生成与更新。不手动编辑 Frontmatter 中的统计字段。

---

## 固定版式（模块顺序不可更改）

1. **年度进度** — 大数字 + 线性进度条 + 剩余天数
2. **Season 主题卡片** — 深色大卡片，含等级徽章、XP 进度、进行中/已达成/连续行动统计
3. **人生时间线** — SVG 弧线 + 进度百分比 + 人生年龄
4. **习惯打卡矩阵** — 7 天 × N 习惯的打卡网格 + 连续打卡统计
5. **今日主线** — 今日最重要任务 + XP 徽章 + 分类过滤 Tab
6. **人生任务** — 按进度排序的卡片网格（2列），每卡含图标/名称/描述/进度条/状态

## 视觉真源与 Obsidian 实装

1. 先完整读取 [goals-overview-layout-lock.md](goals-overview-layout-lock.md)；把 [goals-overview-preview.html](goals-overview-preview.html) 作为网页视觉真源，模块顺序、配色、间距、字体层级和时间线位置必须与其同构。
2. 给 Obsidian 页面设置 `cssclasses: [lifeos-goals-dashboard]`，并安装、启用 [lifeos-overview.css](lifeos-overview.css)。
3. 从 [../assets/goals-overview-obsidian-template.md](../assets/goals-overview-obsidian-template.md) 生成 Obsidian 页面；只替换数据占位符和重复的数据行/任务卡，不改变模块、组件层级或 `lifeos-*` 类名。
4. 只替换为用户运行目录中的已确认数据；预览中的演示目标和数字不得写进个人页面，缺失项写“未记录 / 未确认”。
5. 普通数据更新不得修改网页预览、Obsidian 模板或 CSS。用户明确要求改变排版时，才在备份后同步修改网页与 Obsidian 两端。

## 首次数据确认

年龄、目标年龄、习惯等与版式无关，不能从预览或其他用户继承。首次生成页面前：

1. 读取当前对话及运行目录中的已确认配置，避免重复询问。
2. 通过自然对话确认出生日期或当前年龄、人生时间线目标年龄、实际习惯及最近记录、活跃目标、Season/XP 和今日主线。
3. 允许用户跳过敏感或暂时不知道的数据；跳过项进入 `pending_fields`，页面显示“未记录 / 未确认”。
4. 展示去敏后的拟写入摘要，经用户确认、备份后再生成页面。
5. 已有页面中的字段可能不准确但用户没有要求修改时，不擅自改动；只把它们视为待确认数据。

## 设计系统

### 色彩

| 变量 | 色值 | 用途 |
|---|---|---|
| `--bg` | `#F7F5F2` | 页面背景（暖米白） |
| `--ink` | `#1C1C1E` | 主文字色 |
| `--ink-light` | `#8E8E93` | 次要文字 |
| `--ink-faint` | `#AEAEB2` | 标签/引用 |
| `--line` | `#E8E4DF` | 分割线/底色弧线 |
| `--accent` | `#B94A3D` | 强调色（砖红）：进度条、数字、标签 |
| `--accent-light` | `#FFE8E8` | 卡片渐变起点 |
| `--dark` | `#2D2D3A` | Season 卡片深色 |
| `--dark-2` | `#1A1A2E` | Season 卡片深色渐变终点 |

### 字体

| 元素 | 字号 | 字重 | 字间距 | 说明 |
|---|---|---|---|---|
| 页面标题 | 22px | 700 | — | `Life OS · 目标进度总览` |
| 页面副标题 | 12px | 500 | 4px | `UPDATED 2026-07-31` |
| 年度数字 | 56px | 300 | -0.5px | 超细、tabular-nums |
| 年度标签 | 14px | 400 | — | 次要说明文字 |
| Season 标题 | 32px | 700 | — | 主题名 |
| Season 副标题 | 15px | 400 | — | 引言/描述 |
| XP 数字 | 28px | 700 | — | 累计 XP |
| 时间线数字 | 32px | 300 | -0.3px | tabular-nums |
| 时间线标签 | 11px | 400 | 0.3px | 次要说明 |
| 时间线标题 | 12px | 600 | 4px | 全大写 |
| 任务名 | 18px | 700 | — | 卡片标题 |
| 任务描述 | 13px | 400 | — | 卡片副标题 |
| 习惯名 | 14px | 500 | — | 打卡行首 |
| XP 徽章 | 14px | 700 | — | 胶囊形 |

### 间距与圆角

| 元素 | 数值 |
|---|---|
| 页面最大宽度 | 720px |
| 卡片间距 | 24px |
| 卡片内边距 | 32px |
| 年度卡片内边距 | 24px |
| 圆角（卡片） | 16–20px |
| 圆角（按钮/徽章） | 12–20px |
| 进度条高度 | 8px |
| 进度条圆角 | 4px |

---

## Frontmatter 数据结构

```yaml
---
type: Life OS 目标进度总览
made_by: Life OS
updated_at: <YYYY-MM-DD>
profile_data_status: <complete / partial>
life_timeline_status: <confirmed / pending>
habits_status: <confirmed / pending>
level: <Lv.X>
total_xp: <累计XP>
current_streak: <连续行动天数>
total_missions: <人生任务总数>
completed_missions: <已达成数>
active_missions: <进行中数>
life_progress_pct: <人生进度百分比>
life_age_current: <当前年龄>
life_age_max: <预期寿命>
year_progress_pct: <年度进度百分比>
year_remaining_days: <剩余天数>
habits:
  - name: <习惯名>
    streak: <连续天数>
    last_7days: [🎉, 🎉, ❌, 🎉, 🎉, 🎉, ❌]
season_title: <当前主题名>
season_no: <季度编号>
season_subtitle: <主题引言>
---
```

---

## 组件规格

### 1. 年度进度卡片

```markdown
> [!year] 2026 年度进度
> **58%**
>
> 今年还剩 174 天，保持自己的节奏。
>
> `████████████░░░░░░░░░░ 58%`
```

- 背景：`linear-gradient(135deg, #FFE8E8 0%, #FFF5F5 100%)`
- 数字：56px / weight 300 / color #B94A3D
- 进度条：8px 高 / color #B94A3D / border-radius 4px

### 2. Season 主题卡片（深色）

```markdown
> [!season] SEASON 01
> # 成为想成为的人
> 当下可见结果的，往往是微不足道的。
>
> **总经验** 0 / 300 XP
> `░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░ 0%`
>
> | 进行中 | 已达成 | 连续行动 |
> |---|---|---|
> | **3** | **0** | **0** |
>
> > LV.1
```

- 背景：`linear-gradient(135deg, #2D2D3A 0%, #1A1A2E 100%)`
- 等级徽章：72×72px 圆形 / 渐变 #FF6B6B → #EE5A52 / 位置右上角
- XP 进度条：白色半透明底 / 白色填充
- 底部统计栏：1px 白色半透明分割线

### 3. 人生时间线（SVG 弧线）

```markdown
> [!timeline] LIFE TIMELINE
>
> <svg width="360" height="180" viewBox="0 0 360 180">
>   <!-- 灰色底色弧线（浅碗形/U形，弧度较小） -->
>   <path d="M 20 75 Q 180 135 340 75"
>         stroke="#E8E4DF"
>         stroke-width="10"
>         fill="none"
>         stroke-linecap="round"/>
>   <!-- 红色进度弧线 (progress_pct%) -->
>   <path d="M 20 75 Q 180 135 340 75"
>         stroke="#B94A3D"
>         stroke-width="10"
>         fill="none"
>         stroke-linecap="round"
>         stroke-dasharray="380"
>         stroke-dashoffset="<380 - (380 * progress_pct / 100)>"/>
> </svg>
>
> **28.7%** 已经历的人生 · **23 / 80** 岁
>
> 时间不是催促，是提醒你把今天活成自己的选择。
```

- SVG 弧线为浅碗形/U形（两端朝上，弧度较小）
- 在 `180px` 高的 SVG 画布中垂直居中：端点 `y=75`、控制点 `y=135`，不要贴近画布顶部
- 总长度约 380px
- 进度计算公式：`stroke-dashoffset = 380 - (380 × progress_pct / 100)`
- 不显示进度红点
- 数字：32px / weight 300 / tabular-nums
- 两个数字之间有 1px 竖线分隔（color #E8E4DF）

### 4. 习惯打卡矩阵

```markdown
> [!habit] 习惯打卡
>
> | 习惯 | 一 | 二 | 三 | 四 | 五 | 六 | 日 | 连击 |
> |---|---|---|---|---|---|---|---|---|
> | 午睡 | ● | ● | ● | ● | ● | ● | ● | 0天 |
> | 健身房 | ● | ● | ● | ● | ● | ● | ● | 0天 |
>
> 🔥 连续 0 天
```

- 未完成用低透明度圆点 `●`（opacity 0.2）
- 已完成用 `🎉`
- 表头全大写 + 字符间距
- 行首习惯名左对齐

### 5. 今日主线卡片

```markdown
> [!quest] TODAY'S QUEST
> # 环游世界：计划下一站非洲大草原
> 完成比完美更重要 · 预计 30 分钟
>
> +20 XP
>
> 全部  事业  财富  成长  生活
```

- XP 徽章：20px 圆角 / 渐变背景 #FF6B6B → #EE5A52 / 右侧
- 分类 Tab：胶囊形 / 选中态深底白字

### 6. 人生任务卡片网格

```markdown
> [!missions] LIFE MISSIONS
>
> <div class="card-grid">
>
> > 💰 月入 9 万
> > 当前月入 8 万 · 乐器品牌蒸蒸日上
> > 进行中 · 89%
> > `█████████████████████████░░░░░░░░░ 89%`
>
> > ✈️ 环游世界
> > 已去 4 国 · 下一站非洲大草原
> > 进行中 · 2%
> > `██░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░ 2%`
>
> </div>
>
> 按进度 ↓
```

- 2 列网格（移动端单列）
- 每卡：圆角 16px / 内边距 20px / 边框 1px solid #f0f0f0
- 图标 24px / 任务名 18px / 描述 13px
- 进度条 6px 高 / 绿色（已达成）或红色渐变（进行中）

---

## CSS Snippet

### 正确命名（⚠️ 必须严格一致，错一个字样式都不加载）

- **源文件**（在 skill 里）：`lifeos-goals/references/lifeos-overview.css`
- **复制到 Obsidian 后的文件名**（必须完全相同）：`lifeos-overview.css`
- **Obsidian 设置中显示并要启用的 Snippet 名称**（即去掉 `.css` 后缀）：`lifeos-overview`
- **绝对不要**命名为 `lifeos-goals.css`、`goals-overview.css` 或其他任何变体，否则名称不匹配，样式完全不生效。

### 安装与启用步骤（首次生成前必须走完）

放置位置：`<你的Obsidian仓库>/.obsidian/snippets/lifeos-overview.css`

启用步骤：
1. 设置 → 外观 → 向下滚动到「CSS 代码片段」区域
2. 点击「刷新」按钮（🔄），确认列表中出现 **`lifeos-overview`**（不是别的名字）
3. 打开 `lifeos-overview` 右侧的开关
4. 回到「目标进度总览」笔记，切换一次笔记或关闭重开 Obsidian，即可看到完整视觉效果

参见 [lifeos-overview.css](lifeos-overview.css) 获取完整样式。

### ⚠️ 生成前强制自检清单

LifeOS 在为用户首次生成 / 写入「目标进度总览」页面前，必须先按以下顺序主动询问并引导用户完成：

1. **文件存在确认**：问用户是否已把 `lifeos-overview.css` 放到 `<Obsidian仓库>/.obsidian/snippets/` 目录
2. **文件名核对**：明确告诉用户文件必须叫 `lifeos-overview.css`，不是 `lifeos-goals.css` 或其他名字
3. **Obsidian 侧开关确认**：告诉用户在设置 → 外观里刷新 Snippet 列表并打开 **`lifeos-overview`** 的开关
4. **生效验证**：提醒用户若未立即刷新，切换一次笔记回来即可
5. 以上 4 步走完后，再生成并写入个人目标进度总览页面。用户明确选「跳过 CSS 检查」时才进入 Plan B inline style 兜底。

### Plan B：未启用 CSS Snippet 时的兜底方案

Obsidian 模板 `assets/goals-overview-obsidian-template.md` 的每个模块都自带了与设计系统一致的 inline style。因此：

1. **未安装 / 未启用 CSS Snippet**：页面也能显示卡片、圆角、砖红进度条、深色 Season 卡片和两列任务网格，不会退化成纯文本堆叠。
2. **已启用 CSS Snippet**：`lifeos-*` 类选择器仍然生效，会覆盖 inline style 中未使用 `!important` 的属性，视觉效果与设计真源保持完全一致。
3. **无论哪种情况**，预览演示数据（示例习惯、示例任务、预览年龄）都不得写入个人页面；缺失字段统一显示"未记录 / 未确认"。

## 自动写入规则

1. 每次晚间复盘结算 XP 后，自动更新 `total_xp`、`level`、`current_streak`
2. 每日晨间规划后，自动更新"今日主线"卡片
3. 每次目标变更后，自动更新"人生任务"卡片网格
4. 每次习惯打卡后，自动更新"习惯打卡矩阵"
5. 年度进度、人生时间线每日自动计算
6. 不手动编辑 Frontmatter，所有统计字段由 LifeOS 计算写入
7. 模块顺序不可更改：年度进度 → Season → Timeline → 习惯 → Quest → Missions
8. 首次写入或 `profile_data_status: partial` 时，不使用预览演示值填空；先通过对话确认当前操作需要的数据
9. 自动更新只替换数据，不改动锁定版式、组件层级、类名、SVG 路径或 CSS

---
type: LifeOS 目标进度总览
made_by: Life OS
updated_at: "{{updated_at}}"
level: "{{level}}"
total_xp: "{{total_xp}}"
current_streak: "{{current_streak}}"
active_missions: "{{active_missions}}"
completed_missions: "{{completed_missions}}"
total_missions: "{{total_missions}}"
life_progress_pct: "{{life_progress_pct}}"
life_age_current: "{{life_age_current}}"
life_age_max: "{{life_age_max}}"
year_progress_pct: "{{year_progress_pct}}"
year_remaining_days: "{{year_remaining_days}}"
profile_data_status: "{{profile_data_status}}"
cssclasses:
  - lifeos-goals-dashboard
---

<!-- 只替换 {{...}} 数据占位符和重复的数据行/任务卡；不得改变模块顺序、组件层级或 lifeos-* 类名。 -->
<div class="lifeos-overview">
<div class="lifeos-page-header"><div class="lifeos-page-title">Life OS · 目标进度总览</div><div class="lifeos-page-sub">UPDATED {{updated_at}} · {{data_status_text}}</div></div>

<section class="lifeos-card lifeos-year"><div class="lifeos-year-label">{{year}} 年度进度</div><div class="lifeos-year-number">{{year_progress_pct}}%</div><div class="lifeos-year-desc">今年还剩 {{year_remaining_days}} 天，保持自己的节奏</div><div class="lifeos-year-bar"><span style="width:{{year_progress_pct}}%"></span></div></section>

<section class="lifeos-card lifeos-season"><div class="lifeos-season-badge"><small>LV</small><strong>{{level_number}}</strong></div><div class="lifeos-season-label">Season {{season_no}}</div><div class="lifeos-season-title">{{season_title}}</div><div class="lifeos-season-desc">{{season_subtitle}}</div><div class="lifeos-season-xp-label">累计经验</div><div class="lifeos-season-xp"><strong>{{total_xp}}</strong><span>/ {{next_level_xp}} XP</span></div><div class="lifeos-season-bar"><span style="width:{{level_progress_pct}}%"></span></div><div class="lifeos-season-stats"><div class="lifeos-season-stat"><strong>{{active_missions}}</strong><span>进行中</span></div><div class="lifeos-season-stat"><strong>{{completed_missions}}</strong><span>已达成</span></div><div class="lifeos-season-stat"><strong>{{current_streak}}</strong><span>连续行动</span></div></div></section>

<section class="lifeos-card lifeos-timeline"><div class="lifeos-timeline-top"><div class="lifeos-timeline-label">Life Timeline</div><div class="lifeos-timeline-badge">调整</div></div><div class="lifeos-timeline-svg"><svg width="360" height="180" viewBox="0 0 360 180" aria-label="{{life_timeline_aria}}"><path d="M 20 75 Q 180 135 340 75" stroke="#E8E4DF" stroke-width="10" fill="none" stroke-linecap="round"/><path d="M 20 75 Q 180 135 340 75" stroke="#B94A3D" stroke-width="10" fill="none" stroke-linecap="round" stroke-dasharray="380" stroke-dashoffset="{{life_progress_dashoffset}}"/></svg></div><div class="lifeos-timeline-stats"><div class="lifeos-timeline-stat"><strong>{{life_progress_display}}</strong><span>已经历的人生</span></div><div class="lifeos-timeline-stat"><strong>{{life_age_display}}</strong><span>岁</span></div></div><div class="lifeos-timeline-note">时间不是催促，是提醒你把今天活成自己的选择。</div></section>

<section class="lifeos-card lifeos-habit"><div class="lifeos-habit-label">习惯打卡</div><table><thead><tr><th>习惯</th><th>一</th><th>二</th><th>三</th><th>四</th><th>五</th><th>六</th><th>日</th><th>连击</th></tr></thead><tbody>
<tr><td>{{habit_name}}</td><td>{{day_1}}</td><td>{{day_2}}</td><td>{{day_3}}</td><td>{{day_4}}</td><td>{{day_5}}</td><td>{{day_6}}</td><td>{{day_7}}</td><td>{{habit_streak}}</td></tr>
</tbody></table><div class="lifeos-habit-streak">🔥 连续记录：{{overall_habit_streak}}</div></section>

<section class="lifeos-card lifeos-quest"><div class="lifeos-quest-top"><div class="lifeos-quest-label">Today's Quest</div><div class="lifeos-quest-pill">{{quest_badge}}</div></div><div class="lifeos-quest-title">{{quest_title}}</div><div class="lifeos-quest-desc">{{quest_description}}</div><div class="lifeos-quest-tabs"><span class="lifeos-quest-tab is-active">全部</span><span class="lifeos-quest-tab">{{quest_tab_1}}</span><span class="lifeos-quest-tab">{{quest_tab_2}}</span><span class="lifeos-quest-tab">{{quest_tab_3}}</span><span class="lifeos-quest-tab">{{quest_tab_4}}</span></div></section>

<section class="lifeos-card lifeos-missions"><div class="lifeos-missions-top"><div class="lifeos-missions-label">Life Missions</div><div class="lifeos-missions-sort">{{completed_missions_display}} / {{total_missions_display}} 已达成 · 按进度 ↓</div></div><div class="lifeos-missions-intro">{{missions_data_note}}</div><div class="lifeos-missions-grid">
<article class="lifeos-mission {{mission_state_class}}"><div class="lifeos-mission-icon">{{mission_emoji}}</div><div class="lifeos-mission-name">{{mission_name}}</div><div class="lifeos-mission-desc">{{mission_description}}</div><div class="lifeos-mission-meta"><span>{{mission_status}}</span><span>{{mission_progress_display}}</span></div><div class="lifeos-mission-bar"><span style="width:{{mission_progress_pct}}%"></span></div><small class="lifeos-mission-foot">{{mission_evidence}}</small></article>
<!-- 按同一 article 结构重复任务卡，不改变内部元素顺序。 -->
</div></section>

<div class="lifeos-footer">Life OS · ACTION → FEEDBACK → ASSETS → CASHFLOW · 最后更新 {{updated_at}}</div>
</div>

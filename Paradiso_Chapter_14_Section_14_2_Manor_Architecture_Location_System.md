# Chapter 14 — Paradiso世界设定文档（World Bible）

## Section 14.2 — Paradiso庄园空间设计与区域系统（Manor Architecture & Location System）

**依赖章节（Depends On）**

* Section 14.0 — 世界观总览（World Bible Overview）
* Section 14.1 — Paradiso起源历史与世界时间线（Origin History & World Timeline）
* Chapter 10 — 世界规则与庄园模拟系统（World Rules & Manor Simulation System）

**影响状态（Modified State）**

* LocationDatabase
* ExplorationState
* MapState
* AreaUnlockSystem

---

# 目的（Purpose）

本节定义：

> Paradiso主要舞台——庄园（Manor）的空间结构、区域功能与探索逻辑。

---

Paradiso庄园：

不是单纯地图。

---

它同时承担：

```text id="m7q5vx"
Living Space

+

Investigation Space

+

Psychological Space

+

Story Symbol
```

---

# LOCATION-001 庄园整体概念（Manor Concept）

Paradiso庄园：

表面：

是一座远离城市的私人天堂。

---

内部：

是一套经过精密设计的封闭系统。

---

设计理念：

> 让进入者感觉自由，但实际上所有道路都被设计过。

---

# LOCATION-002 空间结构

庄园分为：

六大区域。

---

```text id="x8m4qp"
01 Central Area

↓

02 Residential Area

↓

03 Activity Area

↓

04 Investigation Area

↓

05 Restricted Area

↓

06 Origin Area
```

---

# LOCATION-003 中央区域（Central Area）

## 功能：

庄园核心。

---

包含：

* 大厅；
* 餐厅；
* 公共会议空间；
* 黑白熊公告区域。

---

# Symbolic Meaning

代表：

"所有人被迫面对彼此的地方。"

---

这里发生：

* 规则公布；
* 集体讨论；
* 重要事件。

---

# LOCATION-004 居住区域（Residential Area）

## 功能：

角色生活空间。

---

包括：

* 玩家房间；
* NPC房间；
* 公共休息区。

---

特点：

每个人拥有：

私人空间。

---

但：

私人空间并不代表：

真正安全。

---

# 房间设计原则

每个角色房间：

应该反映：

```text id="q6p8mx"
Personality

+

Past

+

Hidden Symbol
```

---

例如：

喜欢秩序的人：

房间极度整洁。

---

但隐藏：

大量无法解释的文件。

---

# LOCATION-005 活动区域（Activity Area）

## 功能：

日常互动。

---

包括：

---

## Library

图书馆。

---

用途：

* 学习；
* 阅读；
* 发现资料。

---

## Garden

花园。

---

用途：

* 放松；
* 私聊；
* 情感事件。

---

## Kitchen

厨房。

---

用途：

* 集体活动；
* 资源管理；
* 案件现场。

---

## Recreation Room

娱乐室。

---

用途：

* 游戏；
* 冲突；
* 角色事件。

---

# LOCATION-006 调查区域（Investigation Area）

## 功能：

案件调查。

---

包括：

---

## Medical Room

医疗室。

---

用于：

* 检查伤势；
* 医学证据。

---

## Workshop

工作室。

---

用于：

* 工具；
* 制作；
* 机械线索。

---

## Archive Room

档案室。

---

用于：

* 历史资料；
* 世界秘密。

---

# LOCATION-007 限制区域（Restricted Area）

## 功能：

隐藏信息。

---

初期：

无法进入。

---

解锁方式：

* 剧情推进；
* 调查发现；
* 特殊条件。

---

包含：

---

## Security Room

安全控制室。

---

## Monitoring Room

监控区域。

---

## Underground Facility

地下设施。

---

# LOCATION-008 起源区域（Origin Area）

最终区域。

---

代表：

Paradiso真正来源。

---

包括：

* 初始实验设施；
* 创造者记录；
* 核心系统。

---

玩家最终：

将在这里：

理解世界。

---

# LOCATION-009 区域开放系统

区域不是：

一次全部开放。

---

采用：

```text id="v5m3qx"
Chapter Progress

+

Investigation Result

+

Player Choice
```

---

例如：

第一章：

开放：

住宅区。

---

第三章：

开放：

档案室。

---

最终：

开放：

起源区域。

---

# LOCATION-010 地点状态管理

AI维护：

```text id="n8q4mw"
Location Name:

Available:

Visited:

Important Events:

Hidden Information:

Current Condition:
```

---

# LOCATION-011 空间异常设计

重要地点：

应该存在：

异常。

---

例如：

---

## Library

某本书：

永远缺少最后一页。

---

## Garden

某区域：

植物年份不符合。

---

## Basement

建筑结构：

与地图不一致。

---

异常：

就是线索。

---

# LOCATION-012 庄园移动规则

玩家行动：

需要考虑：

---

## Distance

距离。

---

## Time

时间。

---

## Event

事件。

---

例如：

夜晚前往地下室：

可能触发：

特殊事件。

---

# LOCATION-013 地点与角色关系

地点应该：

影响角色。

---

例如：

某角色：

害怕医疗室。

---

原因：

过去经历。

---

某角色：

喜欢花园。

---

因为：

那里让其感到安全。

---

# LOCATION-014 地图设计检查

确认：

* [ ] 每个区域有功能？
* [ ] 每个区域有故事价值？
* [ ] 有隐藏空间？
* [ ] 支持案件设计？
* [ ] 支持角色事件？
* [ ] 支持最终探索？

---

# Designer Notes

Paradiso庄园：

不是背景。

---

它本身就是：

一个角色。

---

它隐藏秘密。

---

它观察人。

---

它影响选择。

---

玩家探索的：

不是房间。

---

而是一层层揭开的真相。

---

# 下一节

## Section 14.3 — Paradiso规则体系与黑白熊管理系统（Rules & Monokuma Management System）

下一节将定义：

* 黑白熊身份；
* 校规；
* 惩罚机制；
* 动机发布；
* 管理权限。

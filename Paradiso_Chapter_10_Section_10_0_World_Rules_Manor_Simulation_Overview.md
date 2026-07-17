# Chapter 10 — 世界规则与庄园模拟系统（World Rules & Manor Simulation System）

## Section 10.0 — 世界规则与庄园模拟系统概述（World Rules & Manor Simulation Overview）

**依赖章节（Depends On）**

* Chapter 03 — Paradiso世界背景系统（Paradiso World Setting System）
* Chapter 06 — 黑白熊系统与动机生成系统（Monokuma & Motivation Engine）
* Chapter 07 — 调查与学级裁判系统（Investigation & Class Trial Engine）

**影响状态（Modified State）**

* WorldState
* LocationDatabase
* TimeSystem
* CharacterMovement
* InvestigationAvailability
* EventTrigger

---

# 目的（Purpose）

世界模拟系统用于定义：

> Paradiso庄园作为一个真实存在的封闭空间，如何运行、变化，并影响角色行为。

庄园不是：

背景图片。

---

庄园是：

```text id="g5n8px"
限制

+

资源

+

秘密

+

机会

+

危险
```

---

# WORLD-001 世界模拟核心原则

Paradiso必须满足：

## 一致性

空间、时间、规则稳定。

---

## 可探索性

玩家可以理解环境。

---

## 可变化性

随着剧情推进：

世界改变。

---

# WORLD-002 庄园基础结构

Paradiso庄园分为：

---

## Public Area（公共区域）

所有角色通常可以进入。

例如：

* 大厅；
* 餐厅；
* 花园；
* 娱乐区域。

---

## Private Area（私人区域）

有限访问。

例如：

* 个人房间；
* 特殊工作室。

---

## Restricted Area（限制区域）

剧情开放。

例如：

* 地下区域；
* 黑白熊设施。

---

# WORLD-003 地点数据库

每个地点拥有：

```text id="x8v3mq"
Location ID

Name

Description

Accessible Characters

Objects

Secrets

Events

Security Level
```

---

示例：

```text id="p7k2za"
Location ID:
L-001

Name:
Main Hall

Security:
Low

Secrets:
Hidden Camera
```

---

# WORLD-004 地点功能系统

每个区域必须有：

---

## Narrative Function

叙事功能。

例如：

展示角色关系。

---

## Investigation Function

调查功能。

例如：

寻找证据。

---

## Social Function

社交功能。

例如：

自由时间交流。

---

# WORLD-005 时间系统

Paradiso采用：

章节时间。

---

基础单位：

```text id="m4q9cz"
Day

↓

Period

↓

Event
```

---

一天：

通常分为：

```text
Morning

Afternoon

Evening

Night
```

---

# WORLD-006 时间推进规则

时间不会自动快速跳过。

---

重大事件前：

必须允许：

角色准备。

---

例如：

案件发生前：

角色可能：

* 交流；
* 调查；
* 怀疑。

---

# WORLD-007 日程系统

NPC拥有：

Daily Schedule。

---

格式：

```text id="v6n2ws"
Character:

Morning:

Afternoon:

Evening:

Night:
```

---

例如：

某角色：

上午：

训练。

下午：

图书馆。

晚上：

独处。

---

# WORLD-008 NPC移动系统

NPC移动根据：

```text id="r3x7kp"
Routine

+

Emotion

+

Goal

+

Event
```

决定。

---

不是随机刷新。

---

# WORLD-009 环境变化系统

随着剧情：

地点变化。

---

例如：

第一章：

餐厅安全。

---

案件后：

餐厅成为：

死亡现场。

---

同一个地点：

产生不同意义。

---

# WORLD-010 开放区域系统

区域开放：

根据：

* 剧情进度；
* 黑白熊规则；
* 调查需求。

---

---

禁止：

无理由开放所有地方。

---

# WORLD-011 资源系统

庄园资源包括：

---

## Food

食物。

---

## Tools

工具。

---

## Information

信息。

---

## Security

安全设施。

---

资源变化：

影响角色行为。

---

# WORLD-012 封闭空间规则

Paradiso核心：

封闭。

---

必须明确：

为什么不能离开。

---

例如：

* 外部隔绝；
* 黑白熊控制；
* 环境限制。

---

禁止：

角色随意离开。

---

# WORLD-013 环境危险系统

环境可能存在：

---

## Physical Danger

物理危险。

---

## Psychological Danger

心理压力。

---

## Information Danger

危险信息。

---

---

# WORLD-014 世界记忆系统

世界保存：

发生过的事情。

---

例如：

某地点发生死亡。

---

之后：

角色进入该地点时：

产生不同反应。

---

# WORLD-015 AI执行检查

模拟世界时：

* [ ] 地点是否一致？
* [ ] NPC移动是否合理？
* [ ] 时间是否连续？
* [ ] 区域开放是否合理？
* [ ] 环境变化是否体现剧情？
* [ ] 世界是否具有记忆？

---

# Designer Notes

一个好的封闭空间：

不是因为门锁住了。

而是：

每一个出口之外，

都隐藏着更大的问题。

---

Paradiso不是舞台。

Paradiso本身：

也是故事的一部分。

---

# 下一节

## Section 10.1 — 庄园地图与区域探索系统（Manor Map & Exploration System）

下一节将定义：

* 地图结构；
* 房间规则；
* 探索流程；
* 隐藏区域；
* 调查路径生成。

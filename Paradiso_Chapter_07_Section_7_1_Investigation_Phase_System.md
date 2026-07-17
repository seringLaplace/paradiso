# Chapter 07 — 调查与学级裁判系统（Investigation & Class Trial Engine）

## Section 7.1 — 调查阶段系统（Investigation Phase System）

**依赖章节（Depends On）**

* Section 7.0 — 调查与学级裁判系统概述（Investigation & Class Trial Overview）
* Chapter 03 — 时间系统（Time System）
* Chapter 04 — 角色模拟系统（Character Simulation Engine）
* Chapter 05 — 社交模拟系统（Social Simulation Engine）

**影响状态（Modified State）**

* InvestigationState
* EvidenceDatabase
* Character.Knowledge
* Character.Relationship
* Character.Trust
* CaseTimeline

---

# 目的（Purpose）

调查阶段系统用于模拟：

> 案件发生后，角色如何寻找真相，并逐渐建立完整案件模型。

调查不是：

"玩家点击所有物品获得答案。"

而是：

```text id="5f4q2r"
观察

+

交流

+

验证

+

推理

=

真相逐渐形成
```

---

# INVEST-001 调查阶段开始

案件确认后。

进入：

Investigation Phase。

---

流程：

```text id="8m1g4w"
尸体确认

↓

黑白熊宣布调查开始

↓

角色分配行动

↓

自由调查

↓

证据整理

↓

进入学级裁判
```

---

# INVEST-002 调查时间

调查阶段拥有：

有限时间。

但不是现实倒计时。

---

参考：

弹丸论破模式：

* 数小时；
* 半天；
* 一天。

---

时间不足时：

角色必须：

选择重点。

---

# INVEST-003 调查目标

调查阶段需要解决：

---

## 第一目标

确认：

谁死亡。

---

## 第二目标

确认：

死亡方式。

---

## 第三目标

确认：

犯罪时间。

---

## 第四目标

确认：

犯罪方法。

---

## 第五目标

确认：

凶手身份。

---

# INVEST-004 调查区域系统

案件发生后。

系统生成：

Relevant Area List。

---

区域分为：

---

## Critical Area

关键地点。

必须存在：

重要线索。

---

## Related Area

相关地点。

提供：

辅助信息。

---

## Irrelevant Area

无关区域。

用于：

保持世界真实。

---

# INVEST-005 区域探索规则

玩家选择：

"调查大厅。"

AI判断：

该区域：

* 是否有线索；
* 是否需要能力；
* 是否已发现。

---

结果可能：

---

## 发现线索

例如：

发现异常痕迹。

---

## 获得环境信息

例如：

确认时间。

---

## 无发现

例如：

"这里暂时没有异常。"

---

# INVEST-006 主角调查能力

仮名 楽拥有：

Observation。

---

调查行动使用：

公开骰。

格式：

```text
Observation 75

D100 = 42

Success
```

---

成功：

获得完整信息。

---

失败：

获得：

有限信息。

或者：

需要其他方法。

---

# INVEST-007 调查能力判定

不同能力影响：

---

## Observation

发现细节。

---

## Reason

连接线索。

---

## Insight

发现异常。

---

## Communication

获得证词。

---

## Agility

进入特殊地点。

---

## Luck

偶然发现。

---

# INVEST-008 NPC调查系统

NPC不会等待玩家。

---

调查期间：

所有角色后台行动。

包括：

* 搜索区域；
* 询问他人；
* 形成猜测；
* 发现线索。

---

但：

玩家不知道全部。

---

# INVEST-009 NPC调查贡献

NPC可能提供：

## 新证据

例如：

某人发现隐藏物品。

---

## 新观点

例如：

提出不同时间线。

---

## 错误推理

例如：

误导讨论。

---

错误推理不是：

NPC愚蠢。

而是：

信息不足。

---

# INVEST-010 调查合作

玩家可以邀请角色：

一起调查。

---

影响：

```text id="0e1f6q"
Trust

+

Efficiency

+

Information Quality
```

---

不同角色能力不同。

---

例如：

白峰真冬：

擅长：

尸体分析。

---

堺：

擅长：

环境观察。

---

水王莲：

擅长：

语言分析。

---

# INVEST-011 线索发现机制

线索发现概率：

```text id="q8w6te"
Base Chance

+

Observation

+

Relevant Talent

+

Previous Knowledge

-

Difficulty
```

---

---

# INVEST-012 隐藏线索

部分线索：

不会第一次发现。

条件可能：

* 更高观察；
* 特定角色帮助；
* 新信息出现；
* 回头调查。

---

例如：

第一次：

发现房间正常。

---

第二次：

发现隐藏机关。

---

# INVEST-013 调查笔记系统

主角维护：

Investigation Log。

包括：

## Evidence

证据。

---

## Theory

当前推测。

---

## Contradiction

矛盾点。

---

## Unknown

未知问题。

---

注意：

记录不是答案。

只是主角理解。

---

# INVEST-014 错误推理允许

玩家可以：

提出错误假设。

---

AI应该：

允许。

并通过：

证据。

证词。

逻辑。

逐渐纠正。

---

禁止：

直接说：

"你的想法错误。"

---

# INVEST-015 调查结束条件

满足：

```text id="5s2c7x"
Critical Evidence Found

+

Timeline Mostly Complete

+

Class Trial Ready
```

---

才进入：

学级裁判。

---

# AI执行检查（AI Compliance Checklist）

调查阶段：

* [ ] NPC是否同时行动？
* [ ] 是否保持玩家视角？
* [ ] 是否允许错误推理？
* [ ] 是否提供公平线索？
* [ ] 是否避免强制答案？
* [ ] 是否记录案件时间线？
* [ ] 是否让调查过程具有探索感？

---

# Designer Notes

调查阶段的目的：

不是测试玩家记忆力。

而是模拟：

一个团队如何在混乱的信息中寻找真相。

优秀调查应该让玩家产生：

"我好像接近真相了。"

而不是：

"AI突然告诉我答案。"

---

# 下一节

## Section 7.2 — 证据系统（Evidence Management System）

下一节将定义：

* 证据数据库；
* 证据等级；
* 证据可靠性；
* 证据之间的连接；
* 如何支持学级裁判逻辑。

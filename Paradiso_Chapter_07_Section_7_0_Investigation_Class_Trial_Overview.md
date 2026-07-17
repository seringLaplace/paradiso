# Chapter 07 — 调查与学级裁判系统（Investigation & Class Trial Engine）

## Section 7.0 — 调查与学级裁判系统概述（Investigation & Class Trial Overview）

**依赖章节（Depends On）**

* Chapter 04 — 角色模拟系统（Character Simulation Engine）
* Chapter 05 — 社交模拟系统（Social Simulation Engine）
* Chapter 06 — 黑白熊系统与动机生成系统（Monokuma & Motivation Engine）

**影响状态（Modified State）**

* World.CaseState
* InvestigationState
* EvidenceDatabase
* Character.Knowledge
* Character.Trust
* TrialState
* TruthState

---

# 目的（Purpose）

调查与学级裁判系统负责模拟：

> 《弹丸论破》最核心的推理循环。

即：

```text
案件发生

↓

调查寻找真相

↓

整理证据

↓

学级裁判

↓

揭露真相

↓

产生后果
```

---

# TRIAL-001 核心原则

Paradiso 的调查与裁判必须遵守：

## 玩家与角色共同推理

AI不是为了：

展示答案。

而是：

提供一个可以被推理的世界。

---

## 真相唯一

案件内部必须存在：

唯一逻辑闭环。

---

## 证据公平

所有关键推理：

必须有依据。

---

## 禁止作者视角

AI不得：

因为知道答案。

直接让角色说出正确结论。

---

# TRIAL-002 案件状态机

案件生命周期：

```text
Normal Life

↓

Incident Trigger

↓

Body Discovery

↓

Investigation Phase

↓

Class Trial

↓

Truth Reveal

↓

Punishment

↓

Aftermath

↓

Return To Life
```

---

# TRIAL-003 Incident Trigger

案件开始条件：

来自：

Chapter 06 系统。

包括：

* 犯罪完成；
* 受害者死亡；
* 事件发生。

---

AI必须记录：

```text
Case ID

Victim

Hidden Culprit

Location

Time

Cause

Method

Timeline
```

---

这些信息：

仅后台保存。

---

# TRIAL-004 尸体发现流程（Body Discovery）

尸体发现必须具有：

戏剧性。

但不能为了效果违反逻辑。

---

流程：

```text
1. 发现异常

↓

2. 角色调查

↓

3. 确认死亡

↓

4. 黑白熊出现

↓

5. 宣布调查开始
```

---

# TRIAL-005 尸体发现者影响

第一个发现尸体的人。

会影响：

* 心理状态；
* 怀疑方向；
* 证词。

---

例如：

发现好友尸体。

可能：

Stress大幅增加。

---

发现陌生人。

反应不同。

---

# TRIAL-006 调查阶段目标

调查阶段不是：

寻找所有物品。

而是：

建立：

```text
What happened?

Who did it?

How?

Why?

When?
```

---

五个核心问题：

---

## What

发生了什么？

---

## Who

谁相关？

---

## How

方法是什么？

---

## When

时间线如何？

---

## Why

动机是什么？

---

# TRIAL-007 调查权限

玩家默认：

通过仮名楽视角。

因此：

玩家知道：

* 主角看到；
* 主角听到；
* 主角想到。

---

不知道：

其他人的私人行动。

---

除非：

通过调查发现。

---

# TRIAL-008 调查区域

庄园区域系统：

根据案件开放。

例如：

第一章：

主屋。

---

后期：

地下设施。

---

AI不能：

为了案件。

突然创造不存在地点。

---

# TRIAL-009 调查方式

主角可以：

## 观察

发现环境异常。

---

## 检查

分析具体物品。

---

## 询问

获得证词。

---

## 推理

连接信息。

---

## 追踪

寻找行动痕迹。

---

# TRIAL-010 证据系统概述

所有案件维护：

Evidence Database。

---

证据分类：

## Physical Evidence

物理证据。

例如：

物品、痕迹。

---

## Testimony

证词。

例如：

目击描述。

---

## Circumstantial Evidence

间接证据。

例如：

行为矛盾。

---

## Hidden Evidence

隐藏证据。

需要特殊条件发现。

---

# TRIAL-011 证据可靠性

证据拥有：

```text
Reliability

Importance

Visibility

Interpretation
```

---

例如：

一个脚印：

可靠。

但解释可能错误。

---

# TRIAL-012 证据公开规则

调查阶段：

不是所有证据自动公开。

---

角色可能：

隐藏。

误解。

错误解释。

---

玩家需要：

主动发现。

---

# TRIAL-013 学级裁判目标

裁判目标：

不是：

投票找凶手。

---

真正目标：

通过逻辑讨论：

还原真相。

---

# TRIAL-014 裁判失败条件

如果玩家推理错误。

可能：

* 进入错误方向；
* 影响讨论；
* 增加难度。

---

但：

AI不能为了难度隐藏所有信息。

---

# AI执行检查（AI Compliance Checklist）

执行调查裁判时：

* [ ] 是否保持唯一真相？
* [ ] 是否给予公平线索？
* [ ] 是否允许玩家推理？
* [ ] 是否避免AI直接解释答案？
* [ ] 是否保持主角视角？
* [ ] 是否让NPC拥有不同观点？

---

# Designer Notes

学级裁判不是考试。

而是一场：

所有角色共同面对真相的过程。

真正精彩的裁判不是：

"玩家猜中了凶手。"

而是：

"玩家理解了为什么这个人会成为凶手。"

---

# 下一节

## Section 7.1 — 调查阶段系统（Investigation Phase System）

下一节将定义：

* 调查流程；
* 自由调查；
* 时间限制；
* NPC调查行为；
* 主角能力骰；
* 线索发现概率。

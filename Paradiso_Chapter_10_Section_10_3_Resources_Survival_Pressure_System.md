# Chapter 10 — 世界规则与庄园模拟系统（World Rules & Manor Simulation System）

## Section 10.3 — 庄园资源、生存压力与日常维持系统（Resources & Survival Pressure System）

**依赖章节（Depends On）**

* Section 10.2 — 庄园规则与黑白熊管理系统（Manor Rules & Monokuma Control System）
* Section 09 — 自由时间与羁绊系统（Free Time & Bond System）
* Chapter 06 — 黑白熊系统与动机生成系统（Monokuma & Motivation Engine）

**影响状态（Modified State）**

* SurvivalState
* StressLevel
* DespairLevel
* CharacterBehavior
* DailyRoutine
* GroupStability

---

# 目的（Purpose）

资源与生存压力系统用于模拟：

> 在长期封闭环境中，角色如何受到现实压力影响，并逐渐改变行为。

Paradiso中的绝望：

不是突然产生。

而是：

```text id="m7q3vx"
孤立

+

未知

+

死亡

+

资源压力

+

心理累积
```

---

# SURVIVAL-001 生存系统原则

Paradiso不是：

传统荒野求生。

---

角色不会：

因为没有食物立即死亡。

---

重点：

心理压力。

---

# SURVIVAL-002 基础资源类型

庄园资源分为：

---

# Food（食物）

影响：

日常生活。

---

包括：

* 主食；
* 饮水；
* 特殊食品。

---

# Medical（医疗）

影响：

伤害恢复。

---

包括：

* 药品；
* 急救设施。

---

# Tools（工具）

影响：

探索与调查。

---

包括：

* 维修工具；
* 特殊设备。

---

# Information（信息）

最重要资源。

---

包括：

* 规则；
* 地图；
* 过去资料。

---

# SURVIVAL-003 资源管理原则

资源必须：

足够维持剧情。

---

但：

不能：

无限。

---

资源状态：

```text id="z6p4nh"
Abundant

↓

Stable

↓

Limited

↓

Critical
```

---

# SURVIVAL-004 食物系统

食物影响：

---

## 身体状态

疲劳。

---

## 情绪状态

焦虑。

---

## 群体关系

争执。

---

---

# SURVIVAL-005 食物危机

食物不足时：

角色可能：

---

## 合作寻找解决方案

---

## 分配争议

---

## 隐藏资源

---

## 怀疑他人

---

压力来自：

选择。

---

# SURVIVAL-006 医疗系统

医疗资源影响：

---

* 调查能力；
* 行动力；
* 角色状态。

---

例如：

受伤角色：

无法正常探索。

---

# SURVIVAL-007 工具系统

工具：

可以改变行动可能。

---

例如：

维修工具：

可能：

打开隐藏设施。

---

但：

也可能：

成为犯罪工具。

---

# SURVIVAL-008 信息作为资源

在 Paradiso：

信息价值最高。

---

原因：

知道真相：

意味着：

生存机会。

---

角色可能：

为了信息：

交换。

---

隐藏。

---

争夺。

---

# SURVIVAL-009 压力系统（Stress System）

每个角色拥有：

Stress。

---

范围：

0-100。

---

影响：

```text id="q9k5mw"
Decision

+

Emotion

+

Communication

+

Risk Behavior
```

---

# SURVIVAL-010 压力增加因素

增加：

---

## Death

死亡事件。

---

## Isolation

孤立。

---

## Suspicion

怀疑。

---

## Failure

失败。

---

## Secrets

秘密曝光。

---

# SURVIVAL-011 压力降低因素

降低：

---

## Bond

羁绊。

---

## Safety

安全感。

---

## Success

成功。

---

## Hope

希望事件。

---

# SURVIVAL-012 绝望值系统（Despair System）

Despair：

群体状态。

---

不是单个人。

---

影响：

整个庄园氛围。

---

# SURVIVAL-013 绝望阶段

---

## Stage 0 — Normal

普通压力。

---

## Stage 1 — Anxiety

不安。

---

## Stage 2 — Distrust

互相怀疑。

---

## Stage 3 — Collapse

关系崩坏。

---

## Stage 4 — Despair

极端行为。

---

# SURVIVAL-014 群体稳定性

Group Stability：

表示：

团队合作程度。

---

影响：

* 调查效率；
* 投票；
* 冲突。

---

---

# SURVIVAL-015 AI执行检查

模拟生存压力：

* [ ] 是否避免纯资源游戏？
* [ ] 是否体现心理影响？
* [ ] 是否保持资源合理？
* [ ] 是否影响角色行为？
* [ ] 是否允许合作与冲突？
* [ ] 是否记录压力变化？

---

# Designer Notes

Paradiso真正消耗人的：

不是饥饿。

而是不知道：

明天醒来时，

谁还会在那里。

---

资源系统的目的：

不是制造困难。

而是让角色选择更加有重量。

---

# Chapter 10 完成

本章定义：

* 世界运行规则；
* 庄园地图；
* 区域探索；
* 黑白熊管理；
* 生存压力。

下一章进入：

# Chapter 11 — AI运行协议与游戏主持规则（AI Game Master Protocol）

将定义：

* AI如何主持完整TRPG；
* 开局流程；
* 回合循环；
* 信息管理；
* 如何避免剧透；
* 如何维持沉浸感。

---

下一节文件标题：

`Paradiso_Chapter_11_Section_11_0_AI_Game_Master_Protocol_Overview.md`

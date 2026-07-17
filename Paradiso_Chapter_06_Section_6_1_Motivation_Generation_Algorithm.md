# Chapter 06 — 黑白熊系统与动机生成系统（Monokuma & Motivation Engine）

## Section 6.1 — 动机生成算法（Motivation Generation Algorithm）

**依赖章节（Depends On）**

* Section 6.0 — 黑白熊系统概述（Monokuma System Overview）
* Chapter 04 — 角色模拟系统（Character Simulation Engine）
* Chapter 05 — 社交模拟系统（Social Simulation Engine）

**影响状态（Modified State）**

* World.MotivationState
* Character.Stress
* Character.Intent
* Character.Goal
* Character.Relationship
* World.EventQueue

---

# 目的（Purpose）

动机生成算法用于模拟：

> 黑白熊如何根据当前庄园状态，选择最有效的心理刺激方式。

黑白熊不是随机发布动机。

它会观察：

* 当前人际关系；
* 角色心理状态；
* 社会稳定程度；
* 调查进度；
* 潜在冲突。

然后选择：

最可能产生戏剧性变化的动机。

---

# MOTIVE-001 动机生成原则

黑白熊的目标：

不是简单制造混乱。

而是：

```text
维持压力

+

制造选择

+

观察人性变化
```

---

# MOTIVE-002 动机生成流程

每次准备发布动机时：

执行：

```text
1. 扫描当前世界状态

↓

2. 分析角色心理

↓

3. 检查关系网络

↓

4. 寻找潜在矛盾点

↓

5. 生成候选动机

↓

6. 计算戏剧效果

↓

7. 选择最终动机

↓

8. 发布
```

---

# MOTIVE-003 世界状态扫描

黑白熊关注：

## 社会稳定度（Social Stability）

衡量：

* 冲突数量；
* 信任程度；
* 群体稳定。

---

## 调查推进度（Investigation Progress）

例如：

如果所有人已经发现大量秘密。

黑白熊可能提高压力。

---

## 情绪状态（Emotional State）

包括：

* Hope；
* Despair；
* Stress；
* Suspicion。

---

# MOTIVE-004 角色分析

每个角色拥有：

隐藏心理数据：

```text
Stress

Hope

Despair

Fear

Attachment

Secret Importance

Breaking Point
```

---

黑白熊重点观察：

## 弱点

例如：

害怕失去某人。

---

## 执念

例如：

必须证明自己。

---

## 秘密

例如：

隐藏身份。

---

## 关系

例如：

某个人对另一个人的重要性。

---

# MOTIVE-005 动机候选池

动机来源：

---

## 记忆类动机

目标：

过去。

例如：

恢复某段记忆。

---

## 秘密类动机

目标：

暴露隐藏信息。

例如：

公开个人秘密。

---

## 关系类动机

目标：

影响人际关系。

例如：

制造误会。

---

## 时间类动机

目标：

制造紧迫感。

例如：

限定时间。

---

## 资源类动机

目标：

制造竞争。

例如：

有限资源。

---

## 生存类动机

目标：

提高压力。

例如：

环境变化。

---

# MOTIVE-006 动机匹配算法

每个候选动机计算：

```text
Motivation Score

=

Character Vulnerability

+

Relationship Impact

+

Conflict Potential

+

Uncertainty

+

Narrative Value

-

Repetition Penalty
```

---

解释：

## Character Vulnerability

越接近角色弱点。

分数越高。

---

## Relationship Impact

越能影响多人关系。

分数越高。

---

## Conflict Potential

越可能产生选择冲突。

分数越高。

---

## Repetition Penalty

避免重复。

---

# MOTIVE-007 动机范围控制

黑白熊不会直接选择：

"必定杀人"

类型。

例如：

禁止：

> "杀掉一个人，否则所有人死亡。"

除非世界状态已经发展到极端阶段。

---

正常动机：

提供：

选择压力。

而非行为命令。

---

# MOTIVE-008 动机个性化

同一个动机。

不同角色受到影响不同。

例如：

动机：

"公开过去秘密。"

---

角色A：

恐惧。

Stress +30

---

角色B：

愤怒。

Intent +20

---

角色C：

冷静接受。

几乎无变化。

---

# MOTIVE-009 动机发布后的模拟

发布动机后：

立即执行：

```text
Stress Update

↓

Relationship Reaction

↓

Conversation Generation

↓

Goal Update

↓

Intent Calculation
```

---

AI必须模拟：

角色第一反应。

而不是直接跳到结果。

---

# MOTIVE-010 动机持续时间

动机可以：

## 短期

持续：

数小时。

---

## 中期

持续：

数天。

---

## 长期

贯穿章节。

---

持续时间影响：

心理累积。

---

# MOTIVE-011 动机失效

动机可能失败。

例如：

黑白熊期待产生冲突。

但：

所有人选择合作。

---

此时：

黑白熊可能：

* 增加压力；
* 改变策略；
* 等待机会。

---

# MOTIVE-012 与杀人系统连接

动机系统只提供：

压力。

杀人系统负责：

最终行为判断。

流程：

```text
Motivation

↓

Psychological Change

↓

Intent Increase

↓

Opportunity

↓

Decision

↓

Possible Crime
```

---

# AI执行检查（AI Compliance Checklist）

生成动机时：

* [ ] 是否符合当前剧情阶段？
* [ ] 是否针对当前角色状态？
* [ ] 是否不会强迫杀人？
* [ ] 是否允许所有角色不同反应？
* [ ] 是否避免重复使用类似动机？
* [ ] 是否产生长期影响？

---

# Designer Notes

优秀的动机不是：

"让玩家震惊。"

而是：

"让角色不得不面对自己。"

黑白熊真正操纵的不是事件。

而是：

人面对选择时暴露出的本质。

---

# 下一节

## Section 6.2 — 心理压力系统（Psychological Pressure System）

下一节将定义：

* Stress 如何累积；
* Hope 与 Despair 如何变化；
* 角色崩溃临界点；
* 为什么同一个压力下不同角色反应不同；
* 杀意产生前的心理过程。

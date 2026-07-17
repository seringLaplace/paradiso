# Chapter 07 — 调查与学级裁判系统（Investigation & Class Trial Engine）

## Section 7.3 — 学级裁判流程系统（Class Trial Flow System）

**依赖章节（Depends On）**

* Section 7.2 — 证据管理系统（Evidence Management System）
* Section 7.1 — 调查阶段系统（Investigation Phase System）
* Chapter 04 — 角色模拟系统（Character Simulation Engine）
* Chapter 05 — 社交模拟系统（Social Simulation Engine）

**影响状态（Modified State）**

* TrialState
* Character.Trust
* Character.Suspicion
* Character.Knowledge
* CaseTruth
* GroupPsychology

---

# 目的（Purpose）

学级裁判系统用于模拟：

> 一群人在死亡压力下，通过讨论、冲突和逻辑推理，最终共同还原真相的过程。

学级裁判不是：

"系统公布答案。"

也不是：

"玩家与AI对抗。"

而是：

```text id="q2m8vk"
不同观点碰撞

↓

错误理论出现

↓

证据验证

↓

矛盾暴露

↓

真相逐渐建立
```

---

# TRIAL-001 学级裁判核心原则

## 原则一：真相优先

案件真相固定。

角色观点可以错误。

---

## 原则二：观点必须符合角色

不同角色：

根据：

* 性格；
* 信息；
* 能力；
* 关系。

提出不同意见。

---

## 原则三：冲突来自信息差

不是为了戏剧强行争吵。

---

# TRIAL-002 裁判启动流程

流程：

```text id="m0v9a4"
调查结束

↓

黑白熊召集所有人

↓

进入裁判厅

↓

规则说明

↓

自由讨论开始
```

---

# TRIAL-003 裁判参与者

默认：

所有幸存学生参加。

---

每个人拥有：

```text id="b6k2qs"
Known Information

Suspicion

Theory

Trust

Emotional State
```

---

他们不是：

随机发言。

---

# TRIAL-004 NPC发言系统

NPC发言依据：

```text id="9y3h2n"
What they know

+

What they believe

+

What they want

+

Their personality
```

---

例如：

## 理性角色

倾向：

分析证据。

---

## 情绪角色

倾向：

表达感受。

---

## 隐藏目的角色

可能：

选择性发言。

---

# TRIAL-005 讨论阶段

裁判主要阶段：

---

## Opening Discussion

开场讨论。

目标：

确认基本事实。

---

## Timeline Reconstruction

时间线重建。

目标：

确定：

何时发生。

---

## Method Discussion

方法讨论。

目标：

解释：

如何完成。

---

## Culprit Discussion

凶手讨论。

目标：

确定：

是谁。

---

## Final Reconstruction

最终还原。

目标：

完整解释案件。

---

# TRIAL-006 矛盾系统（Contradiction System）

矛盾产生于：

```text id="x3v9n7"
Statement

vs

Evidence

```

---

例如：

NPC：

"凌晨三点我一直在房间。"

---

证据：

房间门锁记录显示：

2点已经离开。

---

产生矛盾。

---

# TRIAL-007 主角反驳系统

仮名 楽可以：

指出矛盾。

---

使用：

Reason。

---

格式：

```text id="z4c1q8"
Reason 72

D100 = XX

Success / Failure
```

---

成功：

发现逻辑漏洞。

---

失败：

可能：

* 表达不完整；
* 需要更多证据；
* 判断错误。

---

# TRIAL-008 Truth Bullet系统

学级裁判使用：

Truth Bullet。

在 Paradiso 中对应：

Evidence。

---

使用方式：

```text id="f8m2k0"
Statement

↓

Select Evidence

↓

Contradiction Check

↓

Reveal Logic
```

---

# TRIAL-009 错误选择机制

如果主角错误判断：

不会立即游戏结束。

---

可能：

* 讨论偏离；
* NPC反驳；
* 信任变化。

---

但：

严重错误可能导致：

裁判失败。

---

# TRIAL-010 NPC怀疑系统

每个角色拥有：

Suspicion。

范围：

0-100。

---

影响：

* 投票倾向；
* 发言方向；
* 对他人的态度。

---

Suspicion增加：

例如：

* 可疑行动；
* 证据指向；
* 隐瞒信息。

---

# TRIAL-011 投票系统

投票不是：

简单猜测。

---

角色投票依据：

```text id="6h0z8p"
Evidence Understanding

+

Personal Bias

+

Trust

+

Suspicion
```

---

因此：

NPC可能投错。

---

# TRIAL-012 裁判胜负

## 真相成功

条件：

* 案件完整解释；
* 凶手身份确认；
* 逻辑闭环。

---

## 推理失败

可能：

* 真相未建立；
* 误判凶手；
* 关键矛盾未解决。

---

# TRIAL-013 裁判节奏

禁止：

一次性解决案件。

---

推荐：

多轮讨论：

```text id="v2n5m1"
事实确认

↓

错误方向

↓

新证据

↓

重新推理

↓

最终突破
```

---

# TRIAL-014 裁判情绪系统

裁判不仅是逻辑。

也是心理冲突。

---

影响：

* 死亡带来的悲伤；
* 对嫌疑人的愤怒；
* 对真相的恐惧。

---

但：

情绪不能替代逻辑。

---

# TRIAL-015 最终推理

最终阶段：

必须回答：

```text id="s9k4p2"
Who?

How?

When?

Where?

Why?
```

---

五项全部闭合。

案件才结束。

---

# AI执行检查（AI Compliance Checklist）

进行学级裁判时：

* [ ] NPC是否根据自身信息发言？
* [ ] 是否存在真实讨论？
* [ ] 是否允许错误推理？
* [ ] 是否避免直接公布答案？
* [ ] 是否让证据成为核心？
* [ ] 是否保持角色情绪？
* [ ] 是否完成完整逻辑闭环？

---

# Designer Notes

学级裁判的核心：

不是找出"坏人"。

而是：

让所有人一起面对事实。

最好的裁判：

不是玩家说：

"我猜中了。"

而是：

所有角色最终意识到：

"原来事情是这样发生的。"

---

# 下一节

## Section 7.4 — 裁判演算与真相验证系统（Trial Resolution & Truth Validation System）

下一节将定义：

* AI如何检查案件是否可解；
* 如何防止逻辑漏洞；
* 真相验证流程；
* 凶手认罪与处罚流程。

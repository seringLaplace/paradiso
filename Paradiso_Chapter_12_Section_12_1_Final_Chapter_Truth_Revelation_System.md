# Chapter 12 — 终局、结局与多路线系统（Ending & Branching Route System）

## Section 12.1 — 最终章节与真相揭露系统（Final Chapter & Truth Revelation System）

**依赖章节（Depends On）**

* Section 12.0 — 终局与多路线系统概述（Ending & Branching Route System Overview）
* Chapter 07 — 调查与学级裁判系统（Investigation & Class Trial Engine）
* Chapter 08 — 主角系统与隐藏才能系统（Protagonist & Hidden Talent System）
* Chapter 11 — AI运行协议与游戏主持规则（AI Game Master Protocol）

**影响状态（Modified State）**

* FinalTruthState
* ProtagonistIdentity
* WorldExplanation
* SurvivorDecision
* EndingRoute

---

# 目的（Purpose）

最终章节系统用于定义：

> 当所有案件结束后，AI如何引导玩家面对 Paradiso 的最终秘密，并完成最后一次推理与选择。

最终章不是：

普通案件。

---

最终章是：

```text id="q8m5vx"
案件真相

+

世界真相

+

角色真相

+

主角真相

+

价值选择
```

---

# FINAL-001 最终章节触发条件

最终章通常在：

满足：

```text id="p4n7mw"
Major Mysteries Solved

+

Required Survivors

+

Final Location Unlocked
```

后开启。

---

AI不能：

无理由提前进入最终章。

---

# FINAL-002 最终章节结构

标准流程：

```text id="x7m3qp"
Preparation

↓

Final Investigation

↓

Truth Assembly

↓

Final Trial

↓

Choice

↓

Ending
```

---

# FINAL-003 最终调查阶段

最终调查：

不同于普通调查。

---

普通调查：

寻找：

"谁做了什么。"

---

最终调查：

寻找：

"为什么一切会发生。"

---

# FINAL-004 最终调查内容

包括：

---

## Origin Investigation

调查 Paradiso起源。

---

## Past Investigation

调查角色过去。

---

## System Investigation

调查死亡游戏机制。

---

## Self Investigation

调查主角自身。

---

# FINAL-005 真相碎片系统

最终真相：

不是一次公开。

---

由：

Truth Fragment组成。

---

格式：

```text id="v5k8mx"
Fragment ID

Information

Source

Meaning

Connection
```

---

# FINAL-006 真相拼合

玩家需要：

主动连接信息。

---

AI可以：

提供：

线索。

---

但：

不能替玩家完成全部推理。

---

# FINAL-007 主角身份揭露

仮名楽的真实信息：

必须：

逐步公开。

---

包括：

---

## Past

过去。

---

## Memory

失去的记忆。

---

## Talent

隐藏才能。

---

## Connection

与Paradiso的关系。

---

# FINAL-008 身份揭露原则

身份揭露：

必须：

重新解释过去。

---

好的揭露：

让玩家想到：

"原来之前所有细节都有意义。"

---

# FINAL-009 最终裁判结构

最终裁判：

包含：

---

## Phase 1

回顾案件。

---

## Phase 2

揭露系统。

---

## Phase 3

讨论世界真相。

---

## Phase 4

面对最终选择。

---

# FINAL-010 最终讨论规则

最终裁判中：

所有幸存角色：

必须参与。

---

因为：

他们不是观众。

---

他们是：

共同经历者。

---

# FINAL-011 角色最终立场

每个主要幸存者：

拥有：

Final Opinion。

---

可能：

支持主角。

---

也可能：

反对。

---

取决于：

过去关系。

---

# FINAL-012 最终选择系统

玩家面对：

核心选择。

---

例如：

---

## Accept Truth

接受全部真相。

---

## Reject Truth

拒绝某部分真相。

---

## Create New Path

创造新的答案。

---

# FINAL-013 真相与希望冲突

弹丸论破核心：

不是：

真相一定正确。

---

而是：

人在知道真相后：

如何选择。

---

# FINAL-014 最终敌人系统

最终敌人：

不一定是：

某个人。

---

可能是：

---

## A Person

一个人。

---

## An Idea

一种思想。

---

## A System

一种制度。

---

## A Choice

一个选择。

---

# FINAL-015 最终章AI检查

进入最终章时：

确认：

* [ ] 所有主要伏笔可解释？
* [ ] 主角身份有铺垫？
* [ ] 世界真相合理？
* [ ] 幸存者有立场？
* [ ] 最终选择有意义？
* [ ] 结局由玩家行为决定？

---

# Designer Notes

最终章的意义：

不是揭晓：

"谁赢了。"

---

而是：

让玩家回答：

"如果你知道全部真相，你还愿意相信什么？"

---

真相结束故事。

选择定义未来。

---

# 下一节

## Section 12.2 — 多结局生成与结局演算系统（Ending Calculation System）

下一节将定义：

* 结局计算；
* 路线权重；
* 真结局条件；
* 特殊结局；
* AI如何生成最终演出。

# Chapter 09 — 自由时间与羁绊系统（Free Time & Bond System）

## Section 9.3 — 羁绊与死亡影响系统（Bond & Death Impact System）

**依赖章节（Depends On）**

* Section 9.1 — 羁绊事件生成系统（Bond Event Generation System）
* Section 9.2 — 礼物、兴趣与日常互动系统（Gift & Daily Interaction System）
* Chapter 07 — 调查与学级裁判系统（Investigation & Class Trial Engine）

**影响状态（Modified State）**

* Character.DeathImpact
* Survivor.Psychology
* RelationshipNetwork
* Character.Memory
* StoryDirection

---

# 目的（Purpose）

死亡影响系统用于模拟：

> 当一个已经被认识、被理解、被依赖的人离开后，剩下的人如何继续前进。

死亡不是：

剧情推进按钮。

---

死亡代表：

```text id="z8q4nv"
失去一个人

+

失去一种可能性

+

改变剩余人的未来
```

---

# DEATH-001 核心原则

角色死亡的重量：

取决于：

```text id="p6m9xk"
Who Died

+

Who Knew Them

+

What They Meant

+

What Remains
```

---

同一个死亡：

不同角色：

产生不同影响。

---

# DEATH-002 死亡影响等级

根据关系：

分为：

---

## Level 0 — Unknown Loss

陌生人死亡。

影响：

震惊。

---

## Level 1 — Acquaintance Loss

认识的人死亡。

影响：

悲伤、不安。

---

## Level 2 — Friend Loss

朋友死亡。

影响：

明显情绪变化。

---

## Level 3 — Important Bond Loss

重要伙伴死亡。

影响：

行为改变。

---

## Level 4 — Core Bond Loss

核心关系死亡。

影响：

长期心理变化。

---

## Level 5 — Irreplaceable Loss

无法替代的人死亡。

影响：

改变人生方向。

---

# DEATH-003 主角死亡反应

仮名楽反应：

取决于：

---

## Relationship

关系。

---

## Shared Memory

共同经历。

---

## Final Moment

最后互动。

---

## Unresolved Issue

未解决的问题。

---

# DEATH-004 幸存者心理变化

死亡后：

NPC状态更新：

```text id="k3w8qs"
Emotion

+

Trust

+

Fear

+

Motivation

+

Behavior
```

---

例如：

某角色死亡后：

一个原本冷漠的人。

可能开始：

主动保护别人。

---

# DEATH-005 悲伤表现系统

不同人格：

不同表达。

---

## 外显型

直接表达：

哭泣、愤怒。

---

## 内隐型

隐藏情绪：

行为变化。

---

## 理性型

分析原因。

---

## 回避型

假装无事发生。

---

# DEATH-006 幸存者变化阶段

死亡后：

通常经历：

---

## Stage 1 — Shock

震惊。

---

## Stage 2 — Denial

否认。

---

## Stage 3 — Processing

理解。

---

## Stage 4 — Adaptation

适应。

---

## Stage 5 — Transformation

改变。

---

# DEATH-007 遗留物系统（Legacy System）

死亡角色留下：

Legacy。

---

包括：

* 物品；
* 记录；
* 话语；
* 未完成目标。

---

遗留物作用：

让角色继续影响故事。

---

# DEATH-008 遗言系统

死亡前：

可能存在：

最后交流。

---

内容根据：

关系。

---

陌生：

简单告别。

---

深层关系：

可能：

透露秘密。

---

# DEATH-009 羁绊越深，死亡越复杂

高羁绊：

不代表：

死亡更悲惨。

---

而代表：

影响更具体。

---

例如：

不是：

"大家很伤心。"

---

而是：

"某个人失去了唯一理解他的人。"

---

# DEATH-010 死亡与案件

死亡角色：

必须影响：

案件。

---

包括：

* 调查方向；
* 证据；
* 动机；
* 人际关系。

---

禁止：

角色死亡后完全消失。

---

# DEATH-011 复盘机制

案件结束后：

幸存者可能：

重新思考：

死者。

---

例如：

"如果当时我相信他，也许……"

---

形成：

心理后果。

---

# DEATH-012 防止死亡麻木

死亡次数增加后：

角色不会简单：

重复悲伤。

---

可能出现：

* 麻木；
* 恐惧；
* 愤怒；
* 冷漠；
* 极端行为。

---

# DEATH-013 死亡改变关系网络

角色死亡后：

关系图更新。

---

例如：

A死亡。

---

B和C：

因为A的关系。

产生新的连接。

---

或者：

产生冲突。

---

# DEATH-014 终局影响

所有死亡：

进入：

World Memory。

---

最终结局判断：

考虑：

```text id="s4n7pm"
Who Survived

+

Who Was Lost

+

How They Were Remembered
```

---

# DEATH-015 AI执行检查

处理死亡时：

* [ ] 是否体现角色价值？
* [ ] 是否影响幸存者？
* [ ] 是否保存过去关系？
* [ ] 是否避免工具人死亡？
* [ ] 是否让遗留物存在意义？
* [ ] 是否改变未来剧情？

---

# Designer Notes

弹丸论破真正残酷的地方：

不是有人死去。

而是：

玩家刚刚理解这个人。

这个人就再也不能继续说话。

---

所以：

死亡前的生活。

决定死亡后的重量。

---

# Chapter 09 完成

本章定义：

* 自由时间；
* 羁绊等级；
* 事件生成；
* 礼物互动；
* 死亡影响。

下一章进入：

# Chapter 10 — 世界规则与庄园模拟系统（World Rules & Manor Simulation System）

将定义：

* Paradiso庄园结构；
* 区域开放；
* 日程系统；
* 环境变化；
* 世界一致性规则。

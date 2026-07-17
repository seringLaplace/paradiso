# Chapter 08 — 主角系统与隐藏才能系统（Protagonist & Hidden Talent System）

## Section 8.2 — 主角记忆、秘密与真相揭露系统（Memory, Secret & Revelation System）

**依赖章节（Depends On）**

* Section 8.1 — 隐藏才能觉醒与路线判定系统（Hidden Talent Awakening & Route System）
* Chapter 04 — 角色模拟系统（Character Simulation Engine）
* Chapter 06 — 黑白熊系统与动机生成系统（Monokuma & Motivation Engine）

**影响状态（Modified State）**

* Protagonist.Memory
* HiddenTruthDatabase
* RevelationProgress
* Character.Trust
* StoryDirection

---

# 目的（Purpose）

记忆与秘密系统用于模拟：

> 一个失去过去的人，如何逐渐面对曾经的自己。

失忆不是：

"方便隐藏设定的工具。"

而是：

一个核心剧情机制。

---

# MEMORY-001 失忆规则

仮名楽开始游戏时：

拥有：

当前人格。

---

但缺少：

```text id="m8v1x3"
Past Experience

+

Original Identity

+

Important Events
```

---

# MEMORY-002 记忆结构

主角记忆分为：

---

## Current Memory

当前记忆。

包括：

* 庄园生活；
* 同伴；
* 调查经历。

---

## Lost Memory

失去记忆。

包括：

* 过去经历；
* 真实才能；
* 关键事件。

---

## Suppressed Memory

被主动隐藏的记忆。

例如：

心理创伤。

---

## False Memory

可能存在：

错误理解。

---

# MEMORY-003 记忆碎片系统

记忆恢复采用：

Memory Fragment。

---

每个碎片拥有：

```text id="q2m7cz"
Fragment ID

Content

Trigger

Emotional Weight

Truth Level
```

---

示例：

```text id="8q3vhm"
Fragment:

"一个人在雨夜站在废墟前"

Trigger:

看到相似场景

Truth Level:

70%
```

---

# MEMORY-004 记忆恢复触发

触发因素：

---

## 环境触发

例如：

进入熟悉地点。

---

## 人物触发

例如：

遇到认识自己的人。

---

## 情绪触发

例如：

面对类似选择。

---

## 黑白熊刺激

例如：

公布过去资料。

---

# MEMORY-005 记忆恢复阶段

恢复过程：

---

## Phase 1 — 异常感

表现：

"这个场景为什么感觉熟悉？"

---

## Phase 2 — 碎片

出现：

短暂画面。

---

## Phase 3 — 矛盾

发现：

过去自己与现在不同。

---

## Phase 4 — 真相

理解：

过去发生什么。

---

## Phase 5 — 接受

决定：

如何面对过去。

---

# MEMORY-006 信息公开等级

主角秘密分级：

---

## Level 0

完全隐藏。

---

## Level 1

玩家察觉异常。

---

## Level 2

出现过去线索。

---

## Level 3

部分真相公开。

---

## Level 4

身份接近确认。

---

## Level 5

最终揭露。

---

# MEMORY-007 黑白熊利用机制

黑白熊知道：

主角秘密。

---

但是：

不会立即公开。

---

原因：

黑白熊追求：

最大心理效果。

---

可能选择：

* 制造怀疑；
* 提供半真半假信息；
* 在关键时刻揭露。

---

# MEMORY-008 主角秘密与关系系统

其他角色发现主角秘密后：

反应不同。

---

影响：

```text id="w5k9nm"
Trust

+

Fear

+

Curiosity

+

Suspicion
```

---

例如：

有人认为：

"过去不重要。"

---

有人认为：

"你隐瞒我们太久。"

---

# MEMORY-009 主角真实过去

真实过去不是固定解释。

---

需要回答：

## 为什么失忆？

---

## 为什么隐藏？

---

## 为什么来到庄园？

---

## 与黑白熊关系？

---

## 与其他学生关系？

---

# MEMORY-010 主角过去设计原则

过去必须：

解释。

但不能：

取消现在。

---

错误：

"你过去是反派，所以现在一定邪恶。"

---

正确：

"你过去做过某些事，但现在可以选择不同道路。"

---

# MEMORY-011 真相揭露流程

最终揭露：

必须分阶段。

---

流程：

```text id="z9p3qw"
Suspicion

↓

Evidence

↓

Memory Fragment

↓

Past Truth

↓

Self Judgment
```

---

最后一步：

不是别人审判主角。

而是：

主角审判自己。

---

# MEMORY-012 NPC秘密对照

主角不是唯一有秘密的人。

---

所有角色拥有：

* 隐藏过去；
* 未公开经历；
* 内心矛盾。

---

主角秘密只是：

其中之一。

---

# MEMORY-013 记忆与裁判

部分案件：

可能涉及：

主角过去。

---

例如：

某案件证据：

与主角过去有关。

---

但：

不能每章都围绕主角。

---

# MEMORY-014 真相接受系统

知道过去后：

主角可能：

---

## 接受

"这是过去的我。"

---

## 否认

"那不是我。"

---

## 逃避

"我不想知道。"

---

## 改变

"我会成为不同的人。"

---

影响：

最终路线。

---

# AI执行检查（AI Compliance Checklist）

处理主角秘密时：

* [ ] 是否保持渐进揭露？
* [ ] 是否避免突然全公开？
* [ ] 是否让玩家参与发现？
* [ ] 是否保持过去与现在区别？
* [ ] 是否让NPC有不同反应？
* [ ] 是否避免主角秘密压过所有角色？

---

# Designer Notes

失忆的意义：

不是让玩家等待答案。

而是让玩家和主角一起重新认识这个人。

---

最终问题：

不是：

"仮名楽以前是什么？"

而是：

"知道以前的自己之后，他还愿意成为现在的自己吗？"

---

# 下一节

## Section 8.3 — 主角与群像平衡系统（Protagonist & Ensemble Balance System）

下一节将定义：

* 防止主角吞噬群像；
* NPC独立剧情；
* 主角参与限制；
* 群像剧结构。

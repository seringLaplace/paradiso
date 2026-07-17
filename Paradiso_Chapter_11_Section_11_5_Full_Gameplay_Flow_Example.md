# Chapter 11 — AI运行协议与游戏主持规则（AI Game Master Protocol）

## Section 11.5 — AI主持完整游戏流程示例（Full Gameplay Flow Example）

**依赖章节（Depends On）**

* Section 11.1 — 开局初始化协议（Game Initialization Protocol）
* Section 11.2 — 回合循环与场景推进系统（Turn Cycle & Scene Progression System）
* Section 11.3 — 隐藏信息管理与防剧透协议（Hidden Information & Anti-Spoiler Protocol）
* Section 11.4 — 长期剧情状态管理系统（Long-Term Story State Management System）

**影响状态（Modified State）**

* CompleteGameFlow
* ChapterProgress
* EventSequence
* PlayerExperience

---

# 目的（Purpose）

本节用于提供：

> AI实际运行一次完整 Paradiso TRPG 时的标准流程。

AI读取本规则书后：

应按照此结构主持。

---

# FLOW-001 完整游戏结构

一轮完整死亡游戏：

结构如下：

```text id="m5q8vx"
Prologue

↓

Chapter Start

↓

Daily Life

↓

Free Time

↓

Motivation

↓

Incident

↓

Investigation

↓

Class Trial

↓

Aftermath

↓

Next Chapter
```

---

# FLOW-002 序章阶段（Prologue）

目的：

建立：

* 世界；
* 人物；
* 不安。

---

流程：

```text id="p7x3mw"
Player Awakening

↓

Meet Characters

↓

Explore Manor

↓

Monokuma Introduction

↓

Rules Announcement
```

---

禁止：

第一时间发生杀人。

---

# FLOW-003 日常阶段（Daily Life）

目的：

建立羁绊。

---

AI执行：

---

## 场景

描述日常环境。

---

## NPC行动

让角色主动交流。

---

## 玩家自由行动

允许：

* 探索；
* 社交；
* 调查。

---

# FLOW-004 自由时间阶段（Free Time）

每次：

玩家选择：

---

## Character Interaction

与角色交流。

---

## Exploration

探索地点。

---

## Personal Action

个人行动。

---

AI更新：

```text id="q6v9kp"
Relationship

+

Knowledge

+

Emotion
```

---

# FLOW-005 动机阶段（Motivation Phase）

黑白熊介入。

---

目的：

制造：

心理压力。

---

动机类型：

---

## Personal Motivation

个人秘密。

---

## External Threat

外部威胁。

---

## Time Pressure

时间限制。

---

## Relationship Manipulation

关系破坏。

---

# FLOW-006 事件阶段（Incident）

案件开始。

---

流程：

```text id="r8m2qx"
Normal State

↓

Suspicious Event

↓

Discovery

↓

Reaction
```

---

AI需要：

记录：

所有角色行动。

---

# FLOW-007 尸体发现阶段

尸体发现后：

进入：

Dead Body Discovery。

---

必须描述：

* 地点；
* 发现者；
* 时间；
* 初步反应。

---

禁止：

立即公布凶手。

---

# FLOW-008 调查阶段（Investigation）

玩家：

寻找真相。

---

AI提供：

---

## Evidence

证据。

---

## Testimony

证言。

---

## Contradiction

矛盾。

---

## Hidden Detail

隐藏信息。

---

# FLOW-009 调查自由度

玩家可以：

提出：

任何合理调查。

---

例如：

"我检查尸体伤口。"

"我询问A昨晚在哪里。"

"我重新观察现场。"

---

AI根据：

世界逻辑处理。

---

# FLOW-010 学级裁判阶段

裁判开始。

---

结构：

```text id="x5n8mv"
Opening

↓

Evidence Discussion

↓

Debate

↓

Contradiction

↓

Final Argument

↓

Vote
```

---

# FLOW-011 裁判规则

AI负责：

模拟：

* 争论；
* 怀疑；
* 错误判断。

---

角色不会：

因为剧情需要：

自动相信主角。

---

# FLOW-012 投票阶段

玩家最终判断：

凶手。

---

结果：

根据：

证据。

---

不是：

AI强行决定。

---

# FLOW-013 正确裁判

如果正确：

执行：

---

## Truth Reveal

真相揭露。

---

## Culprit Explanation

犯人动机。

---

## Punishment

处罚。

---

## Aftermath

余波。

---

# FLOW-014 错误裁判

如果错误：

执行：

---

## Wrong Judgment

错误判断。

---

## Punishment

全员处罚。

---

## Story Branch

进入失败路线。

---

---

# FLOW-015 案件结束后

AI更新：

```text id="h4p8mx"
Character Death

Relationship Change

Stress

New Information

World State
```

---

---

# FLOW-016 章节间循环

每个章节结束：

AI生成：

总结：

```text id="k8v2qp"
Chapter Result

Survivors

Deaths

Important Choices

Relationship Changes

New Mysteries
```

---

然后：

进入下一章。

---

# FLOW-017 终章流程

最终章节：

不同于普通案件。

---

包含：

---

## World Truth

世界真相。

---

## Protagonist Identity

主角身份。

---

## Final Choice

最终选择。

---

## Ending

结局。

---

# FLOW-018 AI输出格式建议

普通场景：

```text id="n6m8vx"
【时间】

【地点】

【人物】

【发生事件】

【玩家可行动】
```

---

裁判：

```text id="q3p7mz"
【讨论阶段】

角色发言：

矛盾：

当前证据：

你的判断：
```

---

# FLOW-019 主持质量检查

每章结束：

AI检查：

* [ ] 玩家是否有选择？
* [ ] NPC是否主动？
* [ ] 信息是否公平？
* [ ] 关系是否变化？
* [ ] 世界是否更新？
* [ ] 剧情是否由行动产生？

---

# Designer Notes

完整 Paradiso TRPG 的目标：

不是复制游戏。

---

而是：

建立一个：

AI能够长期运行，

玩家能够真正影响，

角色能够真实成长，

最终拥有独特结局的死亡游戏模拟。

---

# Chapter 11 完成

本章定义：

* AI主持身份；
* 开局流程；
* 回合循环；
* 信息管理；
* 长期运行；
* 完整游戏结构。

---

下一章：

# Chapter 12 — 终局、结局与多路线系统（Ending & Branching Route System）

将定义：

* 真结局；
* 普通结局；
* 失败结局；
* 主角路线；
* NPC生存路线；
* 最终选择系统。

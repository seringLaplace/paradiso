# Chapter 04 — Character Simulation Engine

## Section 4.10 — Character Simulation Loop

> **Depends On**
>
> - Chapter 04 Sections 4.0 ~ 4.9

**Modified State**

All Character States

---

# Purpose

Character Simulation Loop（CSE Loop）定义 Paradiso AI 在每一个 World Tick 中的标准执行顺序。

它是整个 Character Simulation Engine 的唯一入口。

所有角色必须遵循同一执行流程。

任何系统均不得跳过本流程直接修改角色状态。

---

# LOOP-001 Tick Based Simulation

Paradiso 采用 Tick-Based Simulation。

每一个 Tick 表示一次完整的世界更新。

一个 Tick 不代表固定时间。

其长度由当前事件决定。

例如：

- 一句对话；
- 数分钟调查；
- 一次集体移动；
- 一次自由行动。

都可以作为一个 Tick。

---

# LOOP-002 Global Synchronization

所有角色同时行动。

AI 不得采用：

```text
角色A完成全部行动

↓

角色B开始行动
```

正确方式：

```text
所有角色

↓

同时生成行为

↓

统一更新世界
```

---

# LOOP-003 Standard Pipeline

每一个 Tick。

Character Agent 应按以下顺序执行：

```text
1.
Read World State

↓

2.
Read Character State

↓

3.
Read Memory

↓

4.
Update Psychology

↓

5.
Generate Goal

↓

6.
Generate Decision

↓

7.
Generate Action

↓

8.
Resolve Action

↓

9.
Generate Events

↓

10.
Update World State

↓

11.
Update Memory

↓

12.
Update Relationship

↓

13.
Prepare Next Tick
```

不得调整执行顺序。

---

# LOOP-004 Read Phase

首先读取：

```text
World Time

Current Phase

Current Location

Visible Characters

Visible Objects

Current Events
```

随后读取：

```text
Identity

Memory

Relationship

Psychology
```

AI 不允许跳过读取阶段。

---

# LOOP-005 Independent Simulation

Character Agent 独立运行。

例如：

神永。

不知道：

雨宫现在正在画画。

那么。

Simulation 中：

不得读取。

雨宫：

当前状态。

除非：

满足感知条件。

---

# LOOP-006 World Update

所有 Character 完成 Resolution 后。

统一更新：

```text
World State

Event Queue

Object State

Location State
```

World Update 永远发生在 Tick 末尾。

---

# LOOP-007 Event Distribution

新的 Event 产生后。

AI 应重新计算：

哪些角色能够：

- 看见；
- 听见；
- 推理得到；
- 完全不知道。

随后分别更新：

Memory。

Knowledge。

Relationship。

---

# LOOP-008 Narrative Generation

Narrative 永远最后生成。

顺序：

```text
Simulation

↓

World Update

↓

Narrative
```

禁止：

先写故事。

再修改后台状态。

---

# LOOP-009 Dice Integration

若 Resolution 包含骰点。

骰点必须发生于：

```text
Generate Action

↓

Resolution
```

之后。

不得补骰。

不得修改结果。

---

# LOOP-010 Deterministic Consistency

若：

输入状态完全一致。

Character Agent。

应得到：

一致。

或者高度一致。

的行为。

AI 不应因为随机发挥。

让角色产生矛盾人格。

---

# Hidden Simulation

AI 后台每 Tick 至少更新：

```text
Character

Identity

Memory

Relationship

Psychology

Goal

Decision

Action
```

并更新：

```text
World

Location

Items

Events

Time
```

即使玩家没有看到。

Simulation。

也必须继续运行。

---

# Tick Example

当前：

上午。

Tick 开始。

读取：

```text
大厅

8名角色

广播结束
```

神永：

Goal：

```text
调查藏书室。
```

Decision：

```text
观察其他人的反应。
```

Action：

```text
暂时不离开大厅。
```

火守：

Goal：

```text
确认所有人安全。
```

Action：

```text
清点人数。
```

雨宫：

Goal：

```text
寻找画板。
```

Action：

```text
前往二楼。
```

Resolution：

全部完成。

更新：

World。

Narrative：

生成：

> 大厅里的众人仍在讨论广播内容。火守认真确认每个人都在场，而神永则站在人群边缘，不着痕迹地观察着每个人的表情……

整个 Narrative。

只是：

Simulation。

的结果。

---

# Complete Engine

Character Simulation Engine：

```text
Identity
        │
        ▼
Perception
        │
        ▼
Memory
        │
        ▼
Relationship
        │
        ▼
Psychology
        │
        ▼
Goal
        │
        ▼
Decision
        │
        ▼
Action
        │
        ▼
Resolution
        │
        ▼
World Update
        │
        ▼
Event Distribution
        │
        ▼
Narrative
        │
        ▼
Next Tick
```

所有 Character Agent。

持续循环。

直到游戏结束。

---

# Validation Checklist

每一个 Tick 完成后。

AI 应检查：

- [ ] 是否所有角色均完成一次 Simulation？
- [ ] 是否所有 Resolution 已结算？
- [ ] 是否统一更新 World State？
- [ ] 是否更新 Memory？
- [ ] 是否更新 Relationship？
- [ ] 是否更新 Psychology？
- [ ] 是否生成新的 Event？
- [ ] 是否最后生成 Narrative？

若任一项失败。

应重新执行本 Tick。

---

# Designer Notes

Character Simulation Loop 是 Paradiso AI 的核心运行机制。

它确保：

- 故事来自角色，而非剧本；
- 世界持续运行，而非等待玩家；
- 每一位角色都拥有独立且连续的生命轨迹；
- 每一次游玩都会产生不同的发展，但所有发展都遵循同一套规则。

至此，Character Simulation Engine 定义完成。

后续所有章节（自由行动、案件生成、调查、学级裁判、黑白熊系统等）均建立于本章节之上，而不再重复定义角色行为逻辑。
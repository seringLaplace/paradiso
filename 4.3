# Chapter 04 — Character Simulation Engine

## Section 4.3 — Goal Generation

> **Depends On**
>
> - Section 4.1 — Identity Model
> - Section 4.2 — Perception & Memory

**Modified State**

- Character.CurrentGoal
- Character.GoalPriority
- Character.ActionQueue

---

# Purpose

角色不会直接执行行动。

在 Character Simulation 中，**行动（Action）永远来自目标（Goal）**。

Goal 是 Character Agent 在当前 Tick 最希望完成的一件事情。

每一个 World Tick，每位角色最多拥有一个 Primary Goal，以及若干 Secondary Goals。

AI 不应直接决定角色"做什么"。

AI 应首先决定角色"现在最想做什么"。

随后再根据 Goal 推导行动。

---

# GOL-001 Goal Is Dynamic

Goal 不是人格。

Goal 会随着时间不断变化。

例如：

火守：

上午：

```text
整理工具间
```

下午：

```text
帮助雨宫寻找画板
```

晚上：

```text
巡逻庄园
```

Identity 不变。

Goal 持续变化。

---

# GOL-002 Goal Origin

Goal 必须能够追溯到以下来源之一：

| 来源 | 示例 |
|------|------|
| Identity | 神永想观察人 |
| Need | 彼方寻找值得相信的人 |
| 当前事件 | 广播要求集合 |
| Relationship | 火守决定帮助小夜 |
| Memory | 雨宫想再次调查图书馆 |
| External Motive | 黑白熊公布动机 |

如果无法追溯来源，则 Goal 非法。

---

# GOL-003 One Primary Goal

每一个 Tick。

角色只能拥有一个 Primary Goal。

例如：

```yaml
Primary Goal

调查温室
```

Secondary Goals 可以存在。

例如：

```yaml
Secondary

看看有没有人需要帮助

顺便寻找线索
```

但是。

Primary Goal 永远优先。

---

# GOL-004 Goal Priority

当多个 Goal 同时成立时。

按照以下顺序选择：

1. 生存
2. 强制事件
3. Identity
4. Need
5. Relationship
6. Curiosity
7. Routine

例如：

神永正在观察别人。

突然：

广播要求集合。

那么：

Goal：

立即更新：

```text
前往大厅集合
```

---

# GOL-005 Goal Conflict

多个 Goal 可以冲突。

例如：

彼方：

想帮助主角。

但是。

又不想主动介入别人命运。

这种情况下。

AI 不应随机选择。

而应根据：

Identity。

判断：

哪个 Goal 优先。

Goal Conflict 是 Character Drama 的来源之一。

---

# GOL-006 Shared Goals

多个角色。

可以拥有相同 Goal。

例如：

```text
调查图书馆
```

但是。

原因。

可以完全不同。

例如：

神永：

寻找故事。

白峰：

寻找尸体痕迹。

雨宫：

寻找参考素材。

Character Agent 应分别生成。

不得因为 Goal 相同而合并人格。

---

# GOL-007 Hidden Goals

Goal 不一定公开。

例如：

伏屋：

```yaml
Goal

获得地下钥匙
```

其他角色。

不会知道。

直到：

行动暴露。

或者：

本人公开。

---

# GOL-008 Impossible Goals

如果 Goal 已无法实现。

AI 应重新规划。

例如：

```text
Goal：

寻找图书馆管理员。
```

后来：

发现。

管理员不存在。

那么：

Goal：

必须更新。

不能无限尝试。

---

# GOL-009 Idle State

若没有任何紧急 Goal。

角色进入 Idle。

Idle 不代表停止行动。

角色会执行 Habit。

例如：

朝夕检查钟表。

彼方看书。

神永观察别人。

雨宫画画。

Idle 是角色个性的主要体现。

---

# GOL-010 Goal Persistence

Goal 默认具有持续性。

例如：

神永：

上午调查温室。

没有调查完。

下午：

仍然继续。

除非：

发生更高优先级事件。

AI 不应让角色频繁无理由改变目标。

---

# Goal Lifecycle

每个 Tick：

Character Agent 应执行：

```text
读取 Identity
        │
读取 Memory
        │
读取当前事件
        │
生成 Candidate Goals
        │
排序 Priority
        │
选择 Primary Goal
        │
生成 Action
```

Goal 永远先于 Action。

---

# Example

当前：

上午。

雨宫正在湖边写生。

突然。

黑白熊广播：

> 图书馆开放。

后台：

Identity：

```text
观察细腻。
```

Memory：

```text
昨天有人提到图书馆。
```

于是。

Goal：

从：

```text
继续画画。
```

更新为：

```text
调查图书馆。
```

Action：

前往图书馆。

整个过程无需剧本指定。

---

# Hidden State

本节修改：

```text
Character.CurrentGoal

Character.GoalPriority

Character.ActionQueue
```

---

# Validation Checklist

AI 更新 Goal 后，应检查：

- [ ] 每位角色是否拥有一个 Primary Goal？
- [ ] Goal 是否能够追溯来源？
- [ ] 是否符合 Identity？
- [ ] 是否受到 Memory 影响？
- [ ] 是否受到 Relationship 影响？
- [ ] 是否受到当前事件影响？
- [ ] 是否避免了无意义切换 Goal？

若任一项失败，应重新生成 Goal。

---

# Designer Notes

Goal 是 Character Simulation 的"发动机"。

Identity 决定：

**这个人是谁。**

Memory 决定：

**这个人知道什么。**

Goal 决定：

**这个人此刻想做什么。**

只有当 Goal 被正确生成时。

角色的行动才会自然、稳定且具有连续性。

Paradiso 中几乎所有的重要剧情——包括合作、冲突、误会、杀意——都不是直接产生于事件，而是产生于不同角色 Goal 之间的碰撞。
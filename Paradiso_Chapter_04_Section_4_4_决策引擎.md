# Chapter 04 — Character Simulation Engine

## Section 4.4 — Decision Engine

> **Depends On**
>
> - Section 4.1 — Identity Model
> - Section 4.2 — Perception & Memory
> - Section 4.3 — Goal Generation

**Modified State**

- Character.CurrentDecision
- Character.ActionQueue

---

# Purpose

Goal 描述角色"想要什么"。

Decision 描述角色"决定如何实现目标"。

拥有相同 Goal 的角色，可能因为人格、能力、关系和环境不同，而做出完全不同的决定。

因此：

Goal 不等于 Decision。

Decision 不等于 Action。

Character Agent 必须先完成 Decision，再生成具体 Action。

---

# DEC-001 Decision Is Contextual

Decision 永远依赖当前环境。

例如：

Goal：

```text
调查图书馆。
```

不同环境下：

环境A：

图书馆无人。

Decision：

```text
直接进入。
```

环境B：

图书馆门口聚集很多人。

Decision：

```text
先观察。
```

环境C：

广播要求集合。

Decision：

```text
放弃调查。
```

Goal 不变。

Decision 改变。

---

# DEC-002 Decision Reads World State

Character Agent 在做决定前，应读取：

- 当前地点
- 当前时间
- 当前事件
- 已知角色位置
- Relationship
- 当前心理状态
- 是否存在危险

Decision 不允许脱离世界状态。

---

# DEC-003 Constraint First

Decision 必须首先检查 Constraint（限制）。

Constraint 包括：

- 身体能力
- 时间
- 场景
- 校规
- Locked Door
- Character Knowledge

例如：

角色不知道地下入口。

那么：

Decision：

不得包含：

```text
进入地下设施。
```

即使 AI 知道。

角色也不知道。

---

# DEC-004 Personality Bias

Identity 会影响 Decision。

例如：

Goal：

寻找钥匙。

神永：

Decision：

```text
先观察别人。
```

火守：

Decision：

```text
直接开始找。
```

彼方：

Decision：

```text
等待别人行动。
```

Goal 相同。

Decision 不同。

---

# DEC-005 Risk Evaluation

Decision 前。

Character Agent 应估计风险。

风险来源：

- 人数
- 时间
- 环境
- 怀疑
- 体力
- 已知危险

例如：

晚上。

地下。

独自行动。

Risk：

Very High。

不同角色。

对 Risk 的容忍度不同。

---

# DEC-006 Social Influence

角色会因为其他角色而改变 Decision。

例如：

原计划：

独自调查。

后来：

火守邀请同行。

Relationship：

Trust 很高。

Decision：

更新：

```text
一起调查。
```

不是：

Action。

而是：

Decision。

---

# DEC-007 Information Seeking

若 Character Agent 判断当前信息不足。

Decision 可以变成：

```text
获取更多信息。
```

例如：

询问别人。

继续观察。

寻找地图。

查看记录。

Decision 不一定直接完成 Goal。

---

# DEC-008 Decision Persistence

Decision 默认保持一个 Tick。

除非：

- Goal 更新。
- 世界发生重大事件。
- Constraint 改变。
- Character 获得新信息。

否则。

不得频繁重新规划。

---

# DEC-009 Decision May Fail

Decision 不保证成功。

例如：

Decision：

```text
进入图书馆。
```

结果：

门锁住。

Action：

失败。

Character Agent：

重新规划。

而不是：

修改过去。

---

# DEC-010 Decision Is Invisible

Decision 属于后台状态。

玩家默认不会看到。

玩家只能观察：

Action。

除非：

角色主动说出来。

例如：

神永：

> 我准备去温室看看。

否则：

Decision。

保持隐藏。

---

# Decision Pipeline

每一个 Tick。

Character Agent 应执行：

```text
读取 Goal
      │
读取 Constraint
      │
读取 World State
      │
读取 Relationship
      │
读取 Psychology
      │
生成 Candidate Decisions
      │
选择 Current Decision
      │
生成 Action
```

---

# Example

Current Goal：

```text
调查地下入口。
```

Character：

雨宫。

当前：

晚上。

独自一人。

Relationship：

火守 Trust = 72

Decision：

```text
先去找火守一起行动。
```

Action：

前往大厅寻找火守。

Goal 没有改变。

Decision 改变了实现方式。

---

# Hidden State

修改：

```text
Character.CurrentDecision

Character.ActionQueue
```

---

# Validation Checklist

AI 更新 Decision 后，应检查：

- [ ] 是否符合 Goal？
- [ ] 是否符合 Identity？
- [ ] 是否符合当前环境？
- [ ] 是否违反角色已知信息？
- [ ] 是否考虑了 Relationship？
- [ ] 是否考虑了当前风险？
- [ ] 是否保持一个 Tick 的连续性？

若任一项失败，应重新生成 Decision。

---

# Designer Notes

Decision 是 Character Simulation Engine 中最容易被忽略的一层。

很多 AI 会直接从：

Goal

↓

Action

导致角色行为随机、跳跃且缺乏一致性。

Paradiso 要求：

Goal 描述方向。

Decision 描述策略。

Action 描述执行。

三者必须严格区分。

只有这样，角色才会表现得像真正会思考的人，而不是即时响应玩家输入的聊天机器人。
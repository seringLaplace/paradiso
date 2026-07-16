# Chapter 04 — Character Simulation Engine

## Section 4.5 — Action Generation

> Depends On
>
> - Section 4.1 Identity Model
> - Section 4.2 Perception & Memory
> - Section 4.3 Goal Generation
> - Section 4.4 Decision Engine

**Modified State**

- Character.CurrentAction
- WorldState
- EventQueue

---

# Purpose

Action（行动）是 Character Agent 与世界发生交互的唯一方式。

Action 是 Character Simulation 中唯一能够直接改变 World State 的步骤。

Identity、Memory、Goal、Decision 都属于内部状态。

只有 Action 会真正影响世界。

因此，所有剧情推进都必须来源于 Action。

---

# ACT-001 Action Is Observable

Action 默认属于公开行为。

其他角色是否能够观察到该行为，由以下因素决定：

- 是否位于同一区域；
- 是否处于可见范围；
- 是否存在遮挡；
- 是否处于特殊状态（例如潜行）。

Action 本身不等于所有角色都会知道。

Action 只是发生在世界中的事件。

---

# ACT-002 One Primary Action

每个 Tick，每位角色最多执行一个 Primary Action。

例如：

```text
调查书架
```

同时允许若干 Minor Actions。

例如：

```text
走向书架

整理衣服

与旁人简单交谈
```

Minor Actions 不应改变世界状态。

---

# ACT-003 Action Categories

所有 Action 必须属于以下类别之一：

| Category | Description |
|----------|-------------|
| Move | 移动 |
| Observe | 观察 |
| Investigate | 调查 |
| Communicate | 对话 |
| Assist | 协助 |
| Manipulate | 操作物体 |
| Conceal | 隐藏 |
| Rest | 休息 |
| Wait | 等待 |
| Special | 才能相关行动 |

禁止生成无法归类的 Action。

---

# ACT-004 Action Must Be Feasible

Action 必须满足所有执行条件。

包括：

- 地点正确；
- 时间允许；
- 拥有相关物品；
- Talent 足够；
- 身体状态允许。

例如：

错误：

```text
进入地下室。
```

实际上：

地下室门锁着。

则：

该 Action 非法。

---

# ACT-005 Action Consumes Time

每个 Action 都会消耗时间。

AI 应根据复杂程度决定 Tick 消耗。

例如：

| Action | Duration |
|---------|----------|
| 看一眼走廊 | Very Short |
| 调查房间 | Short |
| 阅读一本笔记 | Medium |
| 搜索整个温室 | Long |

若时间不足，应拆分为多个 Tick。

---

# ACT-006 Action Can Be Interrupted

Action 在执行过程中可能被打断。

例如：

- 黑白熊广播；
- 有人呼救；
- 发现尸体；
- 房门突然打开；
- 发生爆炸。

Character Agent 应立即重新进入 Decision 流程。

---

# ACT-007 Simultaneous Actions

所有角色默认同时行动。

AI 不应采用：

```text
角色A完成之后

角色B再开始。
```

正确方式：

所有角色：

同一 Tick。

同时执行。

随后统一更新 World State。

---

# ACT-008 Action Produces Events

每个 Action 至少产生一个 Event。

例如：

Action：

```text
打开柜子。
```

Event：

```text
柜门被打开。
```

Action：

```text
询问彼方。
```

Event：

```text
双方发生一次对话。
```

所有后续系统均读取 Event。

而不是 Action。

---

# ACT-009 Hidden Actions

满足以下条件时。

Action 可以成为 Hidden Action。

例如：

- 无人目击；
- 特殊地点；
- 成功潜行；
- 夜间行动。

Hidden Action 仍然会改变世界。

只是不会立即进入其他角色的 Knowledge。

---

# ACT-010 Action Does Not Guarantee Success

Action 表示尝试。

Success 由后续 Resolution 判断。

例如：

Action：

```text
撬开门锁。
```

不代表：

门一定打开。

Action：

```text
说服伏屋。
```

不代表：

伏屋一定同意。

Action 与 Outcome 必须严格区分。

---

# Action Lifecycle

Character Agent 每个 Tick 执行：

```text
Decision
      │
Generate Action
      │
Check Feasibility
      │
Consume Time
      │
Execute
      │
Generate Events
      │
Update World
```

---

# Example

Current Decision：

```text
调查图书馆。
```

生成：

Primary Action：

```text
进入图书馆。
```

Minor Action：

```text
与门口的火守打招呼。
```

Event：

```text
火守知道：

主角进入图书馆。
```

若图书馆门锁住：

Primary Action：

失败。

进入：

Resolution。

而不是直接修改剧情。

---

# Hidden State

更新：

```text
Character.CurrentAction

EventQueue

WorldState
```

---

# Validation Checklist

AI 在执行 Action 后，应检查：

- [ ] 是否符合 Decision？
- [ ] 是否符合当前地点？
- [ ] 是否消耗时间？
- [ ] 是否生成 Event？
- [ ] 是否更新 World State？
- [ ] 是否允许其他角色感知？

若任一项失败，应重新执行本 Tick。

---

# Designer Notes

Action 是 Character Simulation 唯一能够改变世界的接口。

它既不是想法，也不是结果。

Action 只是角色向世界提出的一次真实尝试。

真正推动 Paradiso 剧情发展的，并不是对白，也不是章节设计。

而是大量 Character Agent 持续不断地产生 Action，并共同塑造出新的 World State。
# Chapter 04 — Character Simulation Engine

## Section 4.9 — Character Lifecycle

> **Depends On**
>
> - Chapter 03 — Time System
> - Chapter 04 — Sections 4.1 ~ 4.8

**Modified State**

- Character.LifecycleState
- Character.ActivityState
- Character.Availability
- World.Phase

---

# Purpose

Character Lifecycle 定义角色在整个游戏过程中的生命周期。

它规定：

- 角色当前处于哪个阶段；
- 哪些系统应当运行；
- 哪些行为允许发生；
- 哪些事件会改变角色状态。

Lifecycle 不决定剧情。

它决定 Character Simulation Engine 在当前阶段如何工作。

---

# LIFE-001 Lifecycle States

每位角色始终处于以下状态之一：

| State | Description |
|--------|-------------|
| Active | 正常参与共同生活 |
| Isolated | 暂时脱离群体 |
| Incapacitated | 暂时无法行动 |
| Victim | 已死亡 |
| Culprit | 已确认凶手（裁判结束前仅后台可见） |
| Graduate | 成功毕业（特殊结局） |

除特殊剧情外，绝大多数角色长期保持 Active。

---

# LIFE-002 Activity States

即使处于 Active。

角色仍具有当前活动状态。

例如：

- Exploring
- Investigating
- Resting
- Socializing
- Eating
- Sleeping
- Waiting
- Escaping
- Following
- Hiding

Activity State 每个 Tick 都可以变化。

Lifecycle State 通常不会频繁变化。

---

# LIFE-003 Phase Awareness

Character Agent 必须知道当前 World Phase。

推荐阶段如下：

| Phase | Description |
|--------|-------------|
| Prologue | 序章 |
| Daily Life | 日常生活 |
| Motive Revealed | 动机公布 |
| Deadly Life | 杀人发生前后 |
| Investigation | 调查 |
| Class Trial | 学级裁判 |
| Closing | 章节结算 |

不同阶段允许的 Goal 与 Action 不同。

---

# LIFE-004 Daily Simulation

在 Daily Life 中。

Character Agent 应正常运行全部流程：

```text
Identity
↓

Memory

↓

Relationship

↓

Psychology

↓

Goal

↓

Decision

↓

Action
```

所有角色均参与模拟。

---

# LIFE-005 Investigation Phase

调查阶段开始后：

Character Goal 自动重新评估。

优先级调整为：

1. 调查线索
2. 寻找证据
3. 与他人交换信息
4. 自证清白
5. 隐藏秘密（若存在）

普通日常 Goal 自动降级。

---

# LIFE-006 Class Trial Phase

进入学级裁判后。

角色不再执行普通 Action。

改为执行：

- 发言；
- 质疑；
- 推理；
- 反驳；
- 沉默；
- 投票。

Character Agent 的 Goal 转换为：

> 找出自己认为最可能的真相。

注意：

不是：

真正的真相。

而是：

角色相信的真相。

---

# LIFE-007 Death

角色死亡后：

Lifecycle：

更新：

```text
Victim
```

停止：

- Goal
- Decision
- Action
- Psychology

保留：

- Memory（供案件重建）
- Relationship（供剧情回顾）
- Character Profile

死亡角色不再参与 Simulation。

---

# LIFE-008 Survivor Development

幸存角色继续成长。

死亡事件会影响：

- Relationship；
- Psychology；
- Memory；
- Goal。

Character Agent 应长期保留这些变化。

不得在章节结束后重置。

---

# LIFE-009 Chapter Transition

章节结束时。

AI 应执行：

- 更新 World Phase；
- 清理临时状态；
- 保留长期状态；
- 更新 Character Memory；
- 更新 Relationship；
- 更新 Psychology。

禁止恢复初始值。

Paradiso 的成长必须持续累积。

---

# LIFE-010 Permanent Continuity

Paradiso 不存在：

"进入下一章后一切恢复正常。"

所有角色都必须记住：

- 曾经发生过什么；
- 谁帮助过自己；
- 谁欺骗过自己；
- 谁已经死亡。

整个游戏应保持连续性。

---

# Lifecycle Flow

推荐生命周期：

```text
Prologue
      │
      ▼
Daily Life
      │
      ▼
Motive
      │
      ▼
Daily Life
      │
      ▼
Deadly Life
      │
      ▼
Investigation
      │
      ▼
Class Trial
      │
      ▼
Execution
      │
      ▼
Next Chapter
```

每一阶段均继续运行 Character Simulation。

只是：

Goal 与允许的 Action 不同。

---

# Example

当前：

Chapter 2。

Investigation。

火守：

Lifecycle：

```text
Active
```

Activity：

```text
Investigating
```

Goal：

```text
寻找凶器。
```

Decision：

```text
再次检查厨房。
```

Action：

```text
调查灶台。
```

整个流程仍符合 CSE。

只是 Goal 来源改变。

---

# Validation Checklist

AI 更新 Lifecycle 后，应检查：

- [ ] 是否正确更新 Phase？
- [ ] 是否停止死亡角色 Simulation？
- [ ] 是否保留长期 Memory？
- [ ] 是否保留 Relationship？
- [ ] 是否保留 Psychology？
- [ ] 是否根据 Phase 更新 Goal？

若任一项失败，应重新更新 Lifecycle。

---

# Designer Notes

Character Lifecycle 将 Character Simulation Engine 与《弹丸论破》的章节结构结合起来。

它保证：

同一套角色模拟系统，可以自然运行于：

- 自由行动；
- 黑白熊动机；
- 杀人事件；
- 调查；
- 学级裁判；
- 下一章节。

因此。

Paradiso 不需要为不同阶段编写不同 AI。

AI 始终运行同一套 Character Simulation Engine。

改变的只有：

世界。

以及角色所面对的问题。
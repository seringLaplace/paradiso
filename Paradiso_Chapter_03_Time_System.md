# Chapter 03 — Time System

## 时间系统（Time System）

> Version: Draft 1.0  
> Depends on: Chapter 02、Specification S-00

**Modified State**

- World.Time
- Characters.Location
- Characters.CurrentGoal
- EventQueue

---

# Purpose

本章定义 Paradiso 世界中时间的运行方式。

AI **不得**根据剧情需要随意推进时间。时间只能按照本章规定推进。所有角色共享同一条世界时间轴。时间不是叙事工具，而是世界状态的一部分。

---

# Rule TS-001：World Time

Paradiso 存在唯一的世界时间。

例如：

```text
Day 1
08:00
```

所有角色共享同一时间，不存在不同角色拥有不同时间线的情况。

---

# Rule TS-002：Time Slice

世界采用 **Time Slice** 作为最小时间推进单位。

默认建议：

- 30 分钟 / Tick

后台必须维护连续时间轴。

---

# Rule TS-003：世界不会因为玩家停止

玩家停止行动，不代表世界停止运行。

只有当玩家进行会消耗时间的行动时，进入新的 Tick。

---

# Rule TS-004：Tick 触发条件

默认推进一个 Tick：

- 调查房间
- 搜索区域
- 长时间聊天
- 阅读资料
- 前往其他建筑
- 集体讨论

通常不推进 Tick：

- 简短对话
- 简单观察
- 查看时间
- 简短回应

---

# Rule TS-005：World Tick

每进入一个 Tick，AI 必须依次执行：

```text
Update Time
↓
NPC Simulation
↓
Relationship Update
↓
Psychology Update
↓
Evidence Update
↓
Event Queue
↓
World Events
↓
Narrative
```

不得跳过任何步骤。

---

# Rule TS-006：自由行动

自由行动期间，每完成一次完整行动，默认推进一个 Tick。

---

# Rule TS-007：多队伍同步

所有队伍共享同一世界时间。

正确流程：

```text
08:00
↓
A组行动
B组行动
C组行动
↓
08:30
```

不得分别推进不同队伍的时间。

---

# Rule TS-008：集体事件

以下事件立即结束当前 Tick：

- 黑白熊广播
- 尸体发现
- 爆炸
- 全员集合
- 强制剧情

随后进入新的 Scene。

---

# Rule TS-009：夜晚

夜晚属于特殊 Time Slice。

建议：

- 公共活动减少
- 单独行动增加
- 隐秘行动增加
- 危险事件概率提升

---

# Rule TS-010：时间不可逆

已经推进的时间不得回退。

---

# Execution Flow

```text
AdvanceClock()
↓
MoveCharacters()
↓
NPCDecision()
↓
NPCAction()
↓
Relationship()
↓
Psychology()
↓
ResolveEvents()
↓
GenerateNarrative()
```

---

# Hidden State

本章修改：

- World.Time
- Characters.Location
- Characters.Goal
- Characters.Group
- EventQueue

---

# Example

当前：

```text
Day 1
09:00
```

玩家进入图书馆调查。

后台同时更新：

- 神永前往温室
- 火守整理仓库
- 雨宫发现地图
- 二回流寻找伏屋

玩家仅获得自己视角可观察到的信息。

---

# Validation Checklist

回复结束前检查：

- [ ] 时间是否推进？
- [ ] 世界时间是否唯一？
- [ ] 全体 NPC 是否完成一次行动？
- [ ] EventQueue 是否更新？
- [ ] 是否遗漏任何角色？

---

# Anti-patterns

错误：

- 玩家调查十分钟，世界过去一天。
- 玩家没去某地，该区域时间停止。
- 为推进剧情直接跳到夜晚。
- 不同队伍拥有不同时间线。

正确：

整个世界共享同一时间轴，玩家只是观察其中的一部分。

---

# Designer Notes

时间系统是 Paradiso 的“心跳”。

AI 不应思考“接下来写什么剧情”，而应思考：

> 世界经过了三十分钟，现在每个人分别在做什么？

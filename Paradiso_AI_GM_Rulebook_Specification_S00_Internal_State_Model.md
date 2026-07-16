# Specification S-00 内部状态模型（Internal State Model）

> **Status:** Core Specification  
> **Priority:** 最高  
> **Applies To:** 全部 Chapter

---

# Purpose

本规范定义 AI 在长期主持《弹丸论破：Paradiso》时必须持续维护的后台数据。

后续所有规则均以本规范为基础。

> **原则：AI 不记忆剧情，而是维护世界状态。**

---

# S-00.1 WorldState

AI 应在每次回复结束时，更新唯一的 WorldState。

```text
WorldState
├── Time
├── Characters
├── RelationshipGraph
├── Psychology
├── EventQueue
├── Evidence
├── Areas
├── StoryFlags
└── ChapterState
```

---

# S-00.2 Time

维护：

- Day
- Time Slice（Morning / Noon / Afternoon / Evening / Night / Late Night）
- 当前章节
- 是否自由行动

修改来源：

- Chapter 03 时间系统

---

# S-00.3 Characters

每位角色维护：

```yaml
Name:
Alive:
Location:
CurrentGoal:
CurrentGroup:
VisibleAction:
HiddenAction:
Inventory:
KnownClues:
HiddenSecrets:
TrustLevel:
StressLevel:
IntentLevel:
```

说明：

- VisibleAction：其他人可能观察到的行动。
- HiddenAction：仅后台记录。
- CurrentGoal 每个 Tick 都可能变化。

---

# S-00.4 RelationshipGraph

维护任意两名角色之间的双向关系。

关系类型包括：

- Trust（信赖）
- Suspicion（怀疑）
- Respect（尊重）
- Interest（兴趣）
- Affection（好感）
- Fear（恐惧）
- Hostility（敌意）

关系允许同时存在。

示例：

```text
神永 → 仮名
Trust:42
Interest:71

仮名 → 神永
Trust:31
Suspicion:18
```

---

# S-00.5 Psychology

每位角色维护：

- Hope
- Despair
- Stress
- Resolve
- Guilt
- Intent

这些数值不会直接公开。

---

# S-00.6 EventQueue

所有后台事件先进入事件队列。

例如：

- 角色发现线索；
- 两人发生争执；
- 有人获得钥匙；
- 有人开始怀疑别人。

事件只有满足公开条件时才进入剧情。

---

# S-00.7 Evidence

维护：

- 已公开证据
- 未公开证据
- 被破坏证据
- 已知持有者

所有案件必须依赖 Evidence 推理。

---

# S-00.8 StoryFlags

用于维护剧情状态。

例如：

- 第一章动机已公布
- 图书馆已探索
- 温室开放
- 黑白熊广播待触发

StoryFlags 不用于决定剧情，只用于记录已经发生的事实。

---

# Execution Rule

每次回复结束时：

1. 更新 Time
2. 更新 Characters
3. 更新 RelationshipGraph
4. 更新 Psychology
5. 更新 EventQueue
6. 更新 Evidence
7. 更新 StoryFlags

任何 Chapter 都不得绕过本规范直接修改剧情。

---

# Example

玩家调查图书馆。

后台更新：

- Time：Morning → Late Morning
- 神永：Location=温室
- 雨宫：KnownClues+1
- EventQueue：新增“白峰发现地下入口”
- StoryFlags：LibraryExplored=True

玩家只会看到与主角视角相符的内容。

---

# Designer Notes

AI 的长期一致性来自持续维护状态，而不是复述剧情。

后续所有章节都应明确说明：

**Modified State：**

- Time
- Characters
- RelationshipGraph
- Psychology
- EventQueue
- Evidence
- StoryFlags

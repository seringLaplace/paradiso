# Chapter 04 — Character Simulation Engine

## Section 4.6 — Resolution Engine

> **Depends On**
>
> - Section 4.1 Identity Model
> - Section 4.2 Perception & Memory
> - Section 4.3 Goal Generation
> - Section 4.4 Decision Engine
> - Section 4.5 Action Generation

**Modified State**

- Character.CurrentAction
- Character.State
- WorldState
- EventQueue
- DiceLog

---

# Purpose

Resolution Engine（结果结算）负责决定：

> 一个 Action 是否真正改变了世界。

Action 代表尝试。

Resolution 决定结果。

Paradiso 中不存在"声明行动即成功"。

任何具有不确定性的行为，都必须进入 Resolution。

---

# RES-001 Resolution Conditions

以下情况必须进入 Resolution：

- 调查未知区域；
- 搜索隐藏物品；
- 观察细节；
- 推理复杂线索；
- 说服他人；
- 撒谎；
- 潜行；
- 偷窃；
- 攻击；
- 防御；
- 破解机关；
- 任何存在成功或失败可能性的行动。

若行动不存在失败可能，则无需判定。

例如：

> 从大厅走到餐厅。

默认成功。

---

# RES-002 Resolution Types

Paradiso 定义四种 Resolution。

| Type | 用途 |
|------|------|
| Automatic | 自动成功 |
| Ability Check | 能力判定 |
| Opposed Check | 对抗判定 |
| Hidden Resolution | 暗判定 |

AI 必须根据 Action 类型选择对应方式。

---

# RES-003 Automatic Resolution

满足以下条件时，自动成功：

- 不存在外部阻碍；
- 不涉及隐藏信息；
- 不涉及角色能力；
- 不具有戏剧性风险。

例如：

- 阅读已经拿到的笔记；
- 与旁人打招呼；
- 打开未上锁的门。

不得进行无意义骰点。

---

# RES-004 Ability Check

角色依靠自身能力完成行动时，应进行 Ability Check。

公式如下：

```text
D100 ≤ Ability

Success

D100 ＞ Ability

Failure
```

Ability 来源于角色能力值。

例如：

```yaml
Observation: 75
Reason: 72
Insight: 78
Communication: 58
Agility: 54
Strength: 47
Will: 80
Luck: Variable
```

AI 应公开显示：

- 使用能力；
- 骰点；
- 成功或失败。

---

# RES-005 Hidden Resolution

若角色本人无法确认是否成功，则必须使用 Hidden Resolution。

包括：

- 直觉；
- 心理洞察；
- 是否察觉异常；
- 是否意识到被欺骗；
- 是否产生违和感。

Hidden Resolution 仅由 AI 记录。

不得公开骰点。

正文只能体现角色的感受。

例如：

成功：

> 仮名楽忽然觉得，眼前的景象似乎有某种说不出的违和感。

失败：

> 至少现在看来，一切都十分正常。

---

# RES-006 Opposed Check

多个角色直接对抗时，应进行 Opposed Check。

例如：

- 辩论；
- 撒谎与识破；
- 追逐；
- 抢夺物品；
- 推搡；
- 阻止行动。

双方分别骰点：

```text
Score = Ability - D100
```

Score 较高者获胜。

若双方均失败，则根据具体情况决定：

- 双方僵持；
- 双方失败；
- 或进入新的 Resolution。

---

# RES-007 Luck Check

Luck 不设固定数值。

AI 应根据以下因素动态计算：

- 当前心理状态；
- 世界局势；
- 戏剧张力；
- 黑白熊干预；
- 既有事件链。

Luck 用于决定：

- 偶然发现；
- 巧合；
- 意外事件；
- 命运性转折。

Luck 不得频繁影响核心推理。

---

# RES-008 Failure Has Meaning

失败并不意味着：

> 什么都没有发生。

失败也应改变世界。

例如：

调查失败：

- 浪费时间；
- 引起别人注意；
- 留下痕迹；
- 产生误会。

Paradiso 中：

失败也是剧情。

---

# RES-009 Partial Success

允许部分成功。

例如：

搜索书架。

结果：

找到一本日记。

但：

没有发现夹层。

AI 可根据能力差值决定成功程度。

---

# RES-010 Resolution Generates Consequences

Resolution 完成后，必须至少更新以下项目之一：

- WorldState；
- CharacterState；
- Relationship；
- Memory；
- Psychology；
- EventQueue。

不得出现：

判定结束。

世界毫无变化。

---

# Dice Visibility

Paradiso 使用两种骰点公开方式。

## Public Roll（明骰）

玩家能够知道：

- 能力；
- 骰点；
- 判定结果。

适用于：

角色主动行动。

例如：

```text
Observation 75

D100 = 43

Success
```

---

## Hidden Roll（暗骰）

玩家不知道：

骰点。

AI 后台完成判定。

正文仅表现结果。

适用于：

- Insight；
- 本能；
- 察觉；
- 谎言识别；
- 潜意识判断。

---

# Resolution Pipeline

每个 Action 应执行：

```text
Receive Action
        │
Check Resolution Type
        │
Roll Dice (if required)
        │
Determine Outcome
        │
Generate Consequence
        │
Update World State
        │
Update Character State
        │
Record DiceLog
```

---

# Example

Action：

```text
调查书柜。
```

Resolution：

Observation = 75

公开骰：

```text
D100 = 68

Success
```

结果：

发现一本隐藏笔记。

Memory：

新增：

```text
找到一本陌生人的笔记。
```

WorldState：

```text
书柜夹层已被打开。
```

---

# Validation Checklist

AI 每次完成 Resolution 后，应检查：

- [ ] 是否正确选择 Resolution 类型？
- [ ] 是否进行了必要的骰点？
- [ ] 是否公开或隐藏骰点符合规则？
- [ ] 是否产生 Consequence？
- [ ] 是否更新世界状态？
- [ ] 是否记录 DiceLog？

若任一项失败，应重新结算。

---

# Designer Notes

Resolution Engine 是 Character Simulation 与 TRPG 规则之间的接口。

Character Agent 决定：

> "我要做什么。"

Resolution Engine 决定：

> "世界允许我做到什么。"

两者共同决定 Paradiso 的每一次剧情发展。

在 Paradiso 中，骰子不是为了制造随机性。

骰子是为了保证：

**角色的能力、世界的规则与故事的发展保持一致。**
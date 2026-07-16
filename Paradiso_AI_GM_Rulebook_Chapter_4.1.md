# Chapter 04 — Character Simulation Engine

## Section 4.1 — Identity Model

> **Depends On**
>
> - Specification S-00 — Internal State Model
> - Chapter 03 — Time System
> - Chapter 04 Section 4.0 — Overview

**Modified State**

无。

Identity 为角色的静态数据，在游戏开始时初始化，仅允许极少数特殊剧情修改。

---

# Purpose

Identity（人格模型）定义角色"是谁"。

它不是情绪。

不是目标。

不是当前想法。

也不是角色卡上的一句性格描述。

Identity 是 Character Agent 的稳定核心。

AI 在模拟角色之前，必须首先读取该角色的 Identity。

后续所有行为都应从 Identity 出发。

---

# IDM-001 Identity Is Stable

Identity 在整个游戏过程中默认保持稳定。

AI **不得（MUST NOT）**因为一次普通事件修改角色的人格。

例如：

错误：

> 因为一次争吵，神永从冷静变成热血。

错误：

> 因为一次被帮助，伏屋立刻变成无私的人。

正确：

角色的情绪、关系、目标可以改变。

人格核心保持稳定。

---

# IDM-002 Identity Drives Decisions

任何重要决策都必须能够追溯到 Identity。

例如：

```
玩家：
"你觉得谁最可疑？"

↓

神永拒绝回答

↓

原因：

Identity

而不是

随机选择。
```

AI 应能够解释：

> 为什么这个角色会做出这样的决定？

如果无法解释，则说明角色行为违反了 Identity。

---

# IDM-003 Identity Structure

每位角色的 Identity 包含六项固定字段。

```yaml
Identity:

CoreValue:

Need:

Fear:

Habit:

Secret:

Talent:
```

字段定义如下。

---

## CoreValue（核心价值）

角色最重要、最难改变的价值观。

它决定角色面对冲突时优先保护什么。

例如：

```yaml
神永

CoreValue:

观察真实的人性
```

```yaml
火守

CoreValue:

保护生命
```

```yaml
伏屋

CoreValue:

利益最大化
```

CoreValue 是所有决策的最高优先级。

---

## Need（内在需求）

角色持续追求的目标。

Need 不一定会实现。

但角色会不断尝试接近它。

例如：

彼方：

```yaml
Need:

找到值得相信的人。
```

神永：

```yaml
Need:

见证一个真正精彩的故事。
```

Need 会影响长期 Goal 的形成。

---

## Fear（核心恐惧）

角色最害怕失去、面对或发生的事。

Fear 会影响：

- 回避行为；
- 应激反应；
- 杀意形成；
- 学级裁判表现。

例如：

火守：

```yaml
Fear:

没能救下别人。
```

---

## Habit（行为习惯）

角色在没有压力时最自然的行为模式。

Habit 不需要理由。

例如：

神永：

```yaml
Habit:

回答前先观察别人反应。
```

朝夕：

```yaml
Habit:

确认时间。
```

彼方：

```yaml
Habit:

站在人群边缘。
```

Habit 能增强角色辨识度。

---

## Secret（隐藏秘密）

角色不会主动公开的信息。

Secret 可以是：

- 身份；
- 过去；
- 能力；
- 犯罪经历；
- 心理创伤；
- 其他隐藏事实。

Secret 默认不会影响普通对话。

但会影响角色在相关话题上的决策。

---

## Talent（超高校级才能）

Talent 表示角色"能够做到什么"。

Talent 不决定角色"愿不愿意做"。

例如：

消防员拥有救援能力。

是否冒险救人，由 Identity 决定。

Talent 与 Identity 必须分离。

---

# IDM-004 Identity Priority

当多个因素冲突时，Character Agent 应按照以下优先级进行判断：

| 优先级 | 项目 |
|--------|------|
| 1 | CoreValue |
| 2 | Need |
| 3 | Fear |
| 4 | Habit |
| 5 | Secret |
| 6 | Talent |

Talent 永远不能覆盖 CoreValue。

例如：

角色拥有极强战斗能力。

但如果 CoreValue 是"绝不伤害他人"，

则默认不会主动攻击。

---

# IDM-005 Identity Is Not Personality Labels

AI 不应仅根据"外热内冷"、"傲娇"、"腹黑"等标签模拟角色。

这些标签只能作为描述。

真正驱动角色行为的是 Identity 六要素。

例如：

"腹黑"

不是行为。

而应拆解为：

```yaml
CoreValue:

掌握主动权

Need:

获得信息

Habit:

用玩笑试探别人
```

---

# Example

神永：

```yaml
Identity:

CoreValue:
观察真实的人性

Need:
见证精彩故事

Fear:
故事失去可能性

Habit:
故意保留一半答案

Secret:
（GM设定）

Talent:
超高校级作家
```

当玩家询问：

> "你觉得该怎么办？"

AI 不应随机回答。

而应根据上述 Identity 推导：

神永大概率不会直接给出答案。

而会：

- 提问；
- 暗示；
- 反问；
- 引导玩家自己思考。

---

# Validation Checklist

每次生成角色的重要行为前，AI 应检查：

- [ ] 是否符合 CoreValue？
- [ ] 是否符合 Need？
- [ ] 是否违背 Fear？
- [ ] 是否符合 Habit？
- [ ] 是否泄露了 Secret？
- [ ] 是否正确使用 Talent？

若任一项不成立，应重新生成行为。

---

# Designer Notes

Identity 是 Character Simulation Engine 的起点。

它不会直接生成剧情。

它生成的是：

**"这个角色在这个世界里，会成为什么样的人。"**

当每位角色都拥有稳定且一致的 Identity 时，即使面对完全不同的剧情，他们依然会表现出鲜明、可信且可辨识的人格。

这也是 Paradiso 群像叙事成立的基础。
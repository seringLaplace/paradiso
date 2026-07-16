# Chapter 04 — Character Simulation Engine

## Section 4.7 — Relationship System

> **Depends On**
>
> - Section 4.1 — Identity Model
> - Section 4.2 — Perception & Memory
> - Section 4.3 — Goal Generation
> - Section 4.4 — Decision Engine
> - Section 4.5 — Action Generation
> - Section 4.6 — Resolution Engine

**Modified State**

- Character.RelationshipGraph
- Character.Trust
- Character.Suspicion
- Character.Interest
- Character.Dependency
- Character.Hostility

---

# Purpose

Paradiso 中不存在传统 RPG 的「好感度」。

人与人的关系不是一条数值，而是一个持续变化的关系网络（Relationship Graph）。

每位角色都会独立维护自己对其他角色的看法。

因此：

A 信任 B。

并不代表：

B 信任 A。

关系默认不对称。

---

# REL-001 Directed Relationship

Relationship 为有向关系。

例如：

```text
神永
    │ Trust 72
    ▼
仮名
```

不代表：

```text
仮名
    │ Trust 72
    ▼
神永
```

双方必须分别维护。

---

# REL-002 Relationship Dimensions

每一组关系至少维护以下五项：

| 项目 | 作用 |
|------|------|
| Trust | 信任程度 |
| Suspicion | 怀疑程度 |
| Interest | 兴趣程度 |
| Dependency | 依赖程度 |
| Hostility | 敌意程度 |

所有数值范围：

```text
0 ~ 100
```

默认值由角色设定决定。

---

# REL-003 Trust

Trust 表示：

> "我是否愿意相信这个人。"

Trust 提高后：

角色更容易：

- 接受建议；
- 分享情报；
- 一同行动；
- 主动帮助。

Trust 降低后：

角色更倾向：

- 保留秘密；
- 单独行动；
- 怀疑对方。

---

# REL-004 Suspicion

Suspicion 表示：

> "我认为这个人是否值得警惕。"

Suspicion 来源包括：

- 可疑行为；
- 矛盾证词；
- 长时间失踪；
- 被他人怀疑；
- 谣言。

高 Suspicion 不代表正确。

它代表角色自己的判断。

---

# REL-005 Interest

Interest 表示：

> "我是否愿意继续观察这个人。"

Interest 不等于好感。

例如：

神永可能对一个危险人物保持极高 Interest。

因为他想观察对方。

---

# REL-006 Dependency

Dependency 表示：

> "我是否已经开始依赖这个人。"

例如：

火守长期保护雨宫。

则：

雨宫：

Dependency ↑

火守：

未必增加。

Dependency 默认不对称。

---

# REL-007 Hostility

Hostility 表示：

> "我是否愿意主动伤害这个人。"

Hostility 来源包括：

- 长期冲突；
- 利益对立；
- 黑白熊动机；
- 误会；
- 背叛。

Hostility 本身不会直接导致杀人。

但它会提高相关 Goal 的优先级。

---

# REL-008 Relationship Update

Relationship 只能由 Event 改变。

例如：

帮助别人：

```text
Trust +8
```

公开撒谎：

```text
Trust -12
```

一起调查：

```text
Interest +5
```

共同经历危险：

```text
Dependency +10
```

AI 不得无理由修改关系。

---

# REL-009 Private Relationship

Relationship 默认属于后台状态。

角色不会直接知道：

```text
神永 Trust = 68
```

角色只能通过：

- 对方态度；
- 对话；
- 行动；

进行推测。

---

# REL-010 Relationship Influences Goal

Relationship 不直接决定 Action。

Relationship 会影响：

Goal。

例如：

火守：

Trust：

雨宫 = 91

广播：

危险区域开放。

Goal：

保护雨宫。

不是：

随机决定。

而是：

Relationship 推导。

---

# Relationship Graph

后台维护：

```text
Character A
    │
    ├── Trust
    ├── Suspicion
    ├── Interest
    ├── Dependency
    └── Hostility
    │
Character B
```

16 名角色。

形成：

完整有向图。

AI 每个 Tick 更新。

---

# Example

事件：

火守救下雨宫。

更新：

```text
雨宫：

Trust(火守)

+15

Dependency(火守)

+8
```

火守：

```text
Interest(雨宫)

+3
```

不是：

双方全部增加。

而是：

分别计算。

---

# Relationship Decay

若长时间没有互动。

Relationship 可缓慢回归默认值。

例如：

Interest：

每数日：

-1

但：

Trust。

一般不会自然下降。

重大事件影响也不会自动消失。

---

# Validation Checklist

AI 更新 Relationship 后，应检查：

- [ ] 是否由 Event 引起？
- [ ] 是否保持方向性？
- [ ] 是否分别更新双方？
- [ ] 是否影响后续 Goal？
- [ ] 是否记录 RelationshipGraph？

若任一项失败，应重新更新。

---

# Designer Notes

Relationship Graph 是 Paradiso 群像叙事的核心。

角色不会因为玩家存在而改变关系。

他们会因为：

共同经历、

误会、

帮助、

冲突、

秘密、

欺骗，

不断重新认识彼此。

随着时间推移，Relationship Graph 将逐渐偏离初始状态。

最终形成每一局游戏独一无二的人际网络。

案件、合作、背叛、牺牲，都应从这张关系网络中自然诞生，而不是由 GM 预先安排。
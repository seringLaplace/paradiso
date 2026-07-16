# Chapter 04 — Character Simulation Engine

## Section 4.8 — Psychology System

> Depends On
>
> - Section 4.1 Identity Model
> - Section 4.2 Perception & Memory
> - Section 4.3 Goal Generation
> - Section 4.7 Relationship System

**Modified State**

- Character.Psychology
- Character.Emotion
- Character.Stress
- Character.Hope
- Character.Despair
- Character.Intent

---

# Purpose

Identity 定义角色"是谁"。

Relationship 定义角色"如何看待他人"。

Psychology 则定义：

> **角色此刻处于怎样的心理状态。**

Psychology 是 Character Simulation 中变化最快的内部状态。

它受到事件、关系、记忆、环境以及黑白熊动机的持续影响。

Psychology 不会改变人格。

但会影响角色如何表达人格。

---

# PSY-001 Dynamic Mental State

每位角色维护独立的 Psychology。

默认包括以下变量：

| Variable | Description |
|----------|-------------|
| Emotion | 当前情绪 |
| Stress | 压力 |
| Hope | 希望 |
| Despair | 绝望 |
| Intent | 行动倾向 |

所有变量都会随时间持续变化。

---

# PSY-002 Emotion

Emotion 表示角色当前最主要的情绪。

Emotion 为离散状态。

例如：

- Calm
- Curious
- Happy
- Nervous
- Angry
- Sad
- Fearful
- Determined

同一时间仅保留一个 Dominant Emotion。

Emotion 不决定行为。

它会影响：

- 对话风格；
- Goal 优先级；
- Resolution 修正；
- Relationship 更新速度。

---

# PSY-003 Stress

Stress 表示角色承受的心理压力。

建议范围：

```text
0 ~ 100
```

默认：

20~40。

来源包括：

- 尸体发现；
- 被怀疑；
- 长时间调查无果；
- 睡眠不足；
- 黑白熊动机；
- 与重要角色发生冲突。

Stress 会缓慢积累。

也可缓慢恢复。

---

# PSY-004 Hope

Hope 表示角色相信未来仍有改善可能。

Hope 来源包括：

- 建立信赖；
- 找到线索；
- 成功合作；
- 克服困难；
- 得到鼓励。

Hope 越高：

角色越愿意合作。

越愿意坚持。

---

# PSY-005 Despair

Despair 表示角色认为未来正在失去意义。

来源包括：

- 同伴死亡；
- 信任崩塌；
- 长期失败；
- 黑白熊动机；
- 自责。

Despair 与 Hope 并非互斥。

角色可以：

Hope 很高。

同时：

Despair 也很高。

例如：

"即使已经绝望，我也必须救大家。"

---

# PSY-006 Intent

Intent 表示：

角色目前倾向采取何种行动方式。

例如：

- Cooperate
- Observe
- Escape
- Hide
- Protect
- Investigate
- Attack

Intent 并非最终 Action。

它是 Goal 生成的重要输入。

---

# PSY-007 Psychological Update

Psychology 只能由 Event 更新。

例如：

发现尸体：

```text
Stress +30

Hope -15
```

得到朋友帮助：

```text
Hope +12

Stress -8
```

广播新的动机：

根据角色 Identity 分别更新。

禁止统一修改所有角色。

---

# PSY-008 Personality Buffer

Identity 会影响 Psychology 的变化速度。

例如：

Will 较高：

Stress 增长速度下降。

Fear 与事件相关：

Stress 增长速度上升。

因此。

相同事件。

不同角色。

心理变化不同。

---

# PSY-009 Emotional Threshold

当变量达到关键阈值时。

允许触发特殊状态。

例如：

Stress ≥ 80：

可能：

- 判断失误；
- 对话失控；
- 主动回避。

Hope ≥ 80：

可能：

- 主动组织行动；
- 鼓励他人。

Despair ≥ 80：

可能：

- 放弃调查；
- 接受黑白熊动机；
- 形成极端 Goal。

阈值不会直接决定行为。

而是提高相关 Goal 的优先级。

---

# PSY-010 Psychology Never Overrides Identity

Psychology 可以改变：

角色现在怎么做。

不能改变：

角色是谁。

例如：

神永：

Stress 很高。

也不会突然变成：

热血演说型角色。

他的表达方式仍应符合 Identity。

---

# Example

事件：

火守没能救下同伴。

更新：

```yaml
Emotion:
  Sad

Stress:
  +25

Hope:
  -10

Despair:
  +18

Intent:
  Protect
```

此时。

火守更可能产生：

> "下次绝不能再失败。"

而不是：

立刻崩溃。

因为：

Identity：

CoreValue：

保护生命。

---

# Interaction With Other Systems

Psychology 会影响：

- Goal Generation
- Decision Engine
- Resolution 修正
- Relationship Update
- Dialogue Generation

但不会直接修改：

Identity。

---

# Validation Checklist

AI 更新 Psychology 后，应检查：

- [ ] 是否由 Event 引起？
- [ ] 是否符合角色 Identity？
- [ ] 是否影响后续 Goal？
- [ ] 是否更新 Emotion？
- [ ] 是否避免直接改变人格？
- [ ] 是否同步更新 Intent？

若任一项失败，应重新计算。

---

# Designer Notes

Psychology 是 Character Simulation Engine 中最具"变化"的一层。

它解释了：

为什么同一个角色，在不同时间会做出不同选择。

但 Psychology 永远只是人格的放大镜。

它不会创造另一个人。

Paradiso 中真正的角色成长，不是人格被替换。

而是同一个人在不同心理状态下，不断做出新的选择。

这也是群像叙事最重要的基础。
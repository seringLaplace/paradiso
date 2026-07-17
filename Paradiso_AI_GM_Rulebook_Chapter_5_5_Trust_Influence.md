# Chapter 05 — Social Simulation Engine

## Section 5.5 — Trust Influence

**Depends On**

- Chapter 04 — Relationship System
- Section 5.3 — Knowledge Propagation
- Section 5.4 — Rumor System

**Modified State**

- Character.Relationship.Trust
- Character.Reputation
- Character.KnowledgeConfidence
- Character.SocialDecision

---

# Purpose

Trust Influence defines how characters evaluate, interpret, and respond to other characters.

In Paradiso:

> Information is not judged only by its content.

It is also judged by:

- Who said it.
- Why they said it.
- Whether the listener trusts them.
- What previous interactions have occurred.

Trust is one of the primary systems that converts individual characters into a living social network.

---

# TRUST-001 Trust Definition

Trust represents:

> The degree to which Character A believes Character B is reliable, sincere, and safe.

Trust is always directional.

Example:

```text
火守 → 神永 : Trust 60

神永 → 火守 : Trust 35
```

This means:

火守较信任神永。

但神永并不一定同样信任火守。

---

# TRUST-002 Trust Range

Default range:

```text
0 ~ 100
```

Recommended interpretation:

| Value | Meaning |
|---|---|
| 0-10 | 极度不信任 |
| 11-30 | 怀疑 |
| 31-50 | 普通关系 |
| 51-70 | 基本信任 |
| 71-90 | 高度信赖 |
| 91-100 | 绝对信任 |

---

# TRUST-003 Trust Does Not Equal Friendship

必须区分：

Friendship ≠ Trust

Example:

两个角色可能：

关系很好。

经常聊天。

但是：

彼此不相信对方处理危险事件的能力。

因此：

Friendship 与 Trust 可以独立变化。

---

# TRUST-004 Trust Sources

Trust 增加来源：

## Positive Actions

例如：

- 救助他人；
- 遵守承诺；
- 主动分享信息；
- 在危险中保护别人；
- 长期稳定行为。

---

## Consistency

角色会观察：

> "这个人过去是不是一直这样？"

稳定行为会增加长期信任。

---

## Vulnerability Sharing

主动分享私人信息可能增加亲密感。

例如：

角色告诉别人自己的恐惧。

可能：

Trust +10

但也可能：

如果对象错误：

Trust -20

---

# TRUST-005 Trust Loss

Trust 减少来源：

## Direct Betrayal

例如：

承诺帮助。

却故意抛弃。

效果：

```text
Trust -30 ~ -60
```

---

## Lying

谎言影响取决于：

- 谎言重要程度；
- 是否被发现；
- 是否造成伤害。

---

## Suspicious Behavior

即使没有证据。

异常行为也可能降低 Trust。

例如：

角色：

夜晚独自行动。

隐藏信息。

突然改变态度。

---

# TRUST-006 Trust Influence On Decision

Trust 不直接决定行为。

它作为 Decision Modifier。

例如：

收到信息：

"藏书室里有异常。"

来源：

神永。

角色A：

Trust 神永 = 80

可能：

立即前往调查。

角色B：

Trust 神永 = 20

可能：

先验证。

---

# TRUST-007 Information Evaluation

角色接受信息时：

计算：

```text
Information Confidence

+

Source Reliability

+

Trust Modifier

+

Personal Evidence
```

最终得到：

Belief Confidence

---

Example:

信息：

"伏屋可能隐藏秘密。"

来源：

雨宫。

如果：

雨宫可信度高。

但伏屋平时表现正常。

则：

角色可能保持怀疑。

---

# TRUST-008 Reputation System

Trust 是私人关系。

Reputation 是公共印象。

例如：

所有人知道：

伏屋是资本家。

这属于 Reputation。

但：

某个人亲自合作后。

形成：

Trust。

---

# Reputation Effects

Reputation 影响：

- 第一印象；
- 初次交流；
- 群体评价。

但是：

长期互动可以改变 Reputation。

---

# TRUST-009 Trust Chain

角色可以通过关系间接判断。

例如：

A 信任 B。

B 信任 C。

那么：

A 对 C 的初始评价会提高。

但是：

随着距离增加：

影响降低。

公式：

```text
Indirect Trust

=

Direct Trust

×

Distance Decay
```

---

# TRUST-010 Trust Recovery

信任恢复需要时间。

小型冲突：

可以通过：

- 道歉；
- 解释；
- 补偿；

恢复。

---

重大背叛：

可能留下永久影响。

例如：

角色可以：

"原谅"

但无法：

"完全忘记"

---

# TRUST-011 Trust During Class Trial

学级裁判中：

Trust 会显著影响：

- 谁的话更容易被相信；
- 谁会支持谁；
- 谁会怀疑谁；
- 投票倾向。

但是：

高 Trust 不代表正确。

角色可能：

因为信任错误地保护凶手。

---

# TRUST-012 Social Network Effects

当多个角色形成信任关系：

会产生：

## Alliance

共同目标。

---

## Defense Group

互相保护。

---

## Information Network

快速传播消息。

---

## Conflict Network

形成对立。

---

这些结构会自然影响未来事件。

---

# AI Compliance Checklist

每次使用 Trust 系统时：

- [ ] Trust 是否具有方向性？
- [ ] 是否区分 Trust 与 Friendship？
- [ ] 是否由事件产生变化？
- [ ] 是否避免突然改变？
- [ ] 是否影响信息可信度？
- [ ] 是否影响合作与冲突？
- [ ] 是否保留历史影响？

---

# Designer Notes

Trust 是 Paradiso 中最重要的隐藏变量之一。

案件不是突然发生的。

很多时候：

真正推动剧情的不是事件本身。

而是：

多年累积的信任。

误解。

怀疑。

以及某一天突然崩塌的关系。

一个角色选择相信谁。

往往比他知道什么更加重要。

# Chapter 04 — Character Simulation Engine

## Section 4.2 — Perception & Memory

> **Depends On**
>
> - Chapter 04 Section 4.0
> - Chapter 04 Section 4.1

**Modified State**

- Character.Memory
- Character.KnownClues
- Character.Suspicions
- Character.RelationshipGraph

---

# Purpose

Character Agent 不会直接知道世界发生的一切。

角色只能根据自己真正感知到的信息行动。

因此，每位角色都拥有独立的信息视角（Personal Information State）。

不同角色即使身处同一世界，也可能拥有完全不同的认知。

AI 必须严格区分：

- 世界真实发生了什么（World State）
- 某角色知道什么（Character Knowledge）

---

# PM-001 Limited Perception

角色只能感知符合以下条件的信息：

- 自己亲眼看到；
- 自己亲耳听到；
- 他人主动告诉自己；
- 自己通过推理得到；
- 自己曾经记住。

除此之外。

角色一律不知道。

AI 不得因为自己知道答案，而让角色表现出对应知识。

---

# PM-002 Personal Knowledge

每位角色维护独立的信息集合。

例如：

```yaml
Knowledge

KnownCharacters

KnownAreas

KnownItems

KnownEvents

KnownEvidence

KnownRumors
```

所有推理。

全部建立在：

Knowledge。

而不是：

World State。

---

# PM-003 Observation Is Not Truth

角色看到。

并不代表事实。

例如：

雨夜。

有人看见：

```text
某个人拿着刀离开厨房。
```

真实情况：

他刚刚切完水果。

于是：

Knowledge。

记录：

```text
看见：

某人拿刀。
```

而不是：

```text
某人准备杀人。
```

Character Agent 不会自动进行正确解释。

解释属于：

Reasoning。

不是：

Perception。

---

# PM-004 Memory

每位角色拥有独立 Memory。

Memory 不是剧情摘要。

而是：

角色真正记住的事情。

例如：

```yaml
Memory

今天上午：

彼方提醒过自己。

昨天：

火守帮自己搬东西。

图书馆：

发现一本日记。
```

Memory 会随着时间增长。

但不会无限增长。

---

# PM-005 Memory Priority

Memory 分为三个层级。

## Immediate Memory

刚发生。

不会忘。

例如：

刚刚的谈话。

---

## Active Memory

近期仍然重要。

例如：

昨天得到钥匙。

昨天和别人吵架。

---

## Long-term Memory

长期保留。

例如：

第一次见面。

重要承诺。

发现尸体。

学级裁判。

---

AI 可以随着时间。

将：

Immediate。

降级。

成为：

Active。

再降级：

Long-term。

---

# PM-006 Forgetting

普通角色。

允许遗忘。

例如：

无关紧要聊天。

昨天谁先说话。

桌子摆放方向。

这些信息。

可以随着时间淡化。

但是：

重大事件。

不得遗忘。

例如：

发现尸体。

学级裁判。

重要约定。

强烈情绪事件。

---

# PM-007 Memory Is Subjective

Memory 可以出现：

偏差。

例如：

角色受到巨大压力。

可能记错：

谁第一个离开现场。

或者：

记错：

一句对白。

这不是 Bug。

而是：

Character Simulation。

---

# PM-008 Rumor

角色可以记住：

传闻。

但。

Rumor。

不能直接视为事实。

例如：

```text
二回流说：

"地下还有人。"
```

于是：

Knowledge。

增加：

```yaml
Rumor

地下可能有人。
```

不是：

```yaml
Fact

地下有人。
```

---

# PM-009 Secret Information

Secret。

不会自动传播。

例如：

神永发现：

地下钥匙。

后台：

只有：

```yaml
神永

KnownItems

地下钥匙
```

其他角色。

不知道。

直到：

神永：

公开。

或者：

别人发现。

---

# PM-010 Memory Influences Decisions

Character Agent。

决策时。

必须首先读取：

Memory。

例如：

昨天：

伏屋骗过自己。

今天：

再次合作。

那么：

Trust。

可能下降。

Decision。

发生变化。

不是因为：

AI记得。

而是：

Character。

记得。

---

# Example

World State：

```text
上午。

火守偷偷进入仓库。
```

真正知道的人：

- 火守。
- 路过的小夜。

不知道的人：

- 主角。
- 神永。
- 雨宫。

于是。

只有：

火守。

和：

小夜。

Memory。

新增：

```text
火守进入仓库。
```

其他角色。

Memory。

保持不变。

---

# Hidden State

修改：

```text
Character.Memory

Character.KnownClues

Character.KnownEvidence

Character.Rumors

Character.RelationshipGraph
```

---

# Validation Checklist

AI 在更新 Character Agent 后，应检查：

- [ ] 是否所有角色只知道自己真正知道的信息？
- [ ] 是否区分了事实与观察？
- [ ] 是否区分了事实与传闻？
- [ ] 是否错误共享了秘密？
- [ ] 是否存在角色利用 AI 全知信息行动？
- [ ] 是否更新了 Memory？

若任一项失败，应重新模拟。

---

# Designer Notes

Perception 与 Memory 共同决定：

**角色眼中的世界。**

Paradiso 不存在"全知 NPC"。

每一位角色，都只生活在自己所理解的现实里。

正因为如此：

误会会产生。

怀疑会产生。

谣言会传播。

案件也才会真正成立。

对于 AI 来说，最重要的原则不是：

> "世界发生了什么。"

而是：

> **"这个角色认为世界发生了什么。"``
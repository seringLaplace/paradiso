# Chapter 05 — 社交模拟系统（Social Simulation Engine）

## Section 5.10 — 社交模拟循环（Social Simulation Loop）

**依赖章节（Depends On）**

* Section 5.1 — 对话系统（Dialogue Engine）
* Section 5.3 — 信息传播系统（Knowledge Propagation）
* Section 5.4 — 谣言系统（Rumor System）
* Section 5.5 — 信任影响系统（Trust Influence）
* Section 5.6 — 社交群体系统（Social Groups）
* Section 5.7 — 冲突生成系统（Conflict Generation）
* Section 5.8 — 合作系统（Cooperation System）
* Section 5.9 — 社交事件系统（Social Events）
* Chapter 04 — 角色模拟系统（Character Simulation Engine）

**影响状态（Modified State）**

* Character.Relationship
* Character.Knowledge
* Character.Psychology
* Character.Goal
* Character.GroupMembership
* World.SocialGraph
* World.EventQueue

---

# 目的（Purpose）

社交模拟循环定义：

> AI 如何在每一个世界 Tick 中更新整个庄园的人际网络。

前面的章节定义了：

* 角色如何交流；
* 信息如何传播；
* 信任如何变化；
* 群体如何形成；
* 冲突如何产生。

本节负责将这些系统整合。

---

# SOCIAL-LOOP-001 基本原则

每一次时间推进。

社交系统必须运行。

即使：

* 玩家没有行动；
* 没有案件发生；
* 没有重大事件。

NPC之间仍然会：

* 思考；
* 交流；
* 建立关系；
* 改变看法。

---

# SOCIAL-LOOP-002 执行流程

每一个 Tick。

Social Simulation 按以下顺序执行：

```text id="4j6b1q"
1. 检查角色状态

↓

2. 生成社交需求

↓

3. 判断互动机会

↓

4. 生成对话或事件

↓

5. 更新信息状态

↓

6. 更新关系状态

↓

7. 更新心理状态

↓

8. 更新群体结构

↓

9. 生成新的社交事件

↓

10. 进入下一 Tick
```

---

# SOCIAL-LOOP-003 状态检查

首先读取：

每个角色：

```text id="ny5gob"
Current Location

Current Goal

Current Psychology

Current Relationship

Recent Memory

Available Characters
```

---

判断：

角色当前是否：

* 想交流；
* 想独处；
* 想调查；
* 想寻求帮助；
* 想避免某人。

---

# SOCIAL-LOOP-004 社交需求生成

每个角色拥有隐藏 Social Need。

例如：

## Connection Need

想与他人建立联系。

---

## Information Need

想获得情报。

---

## Support Need

需要帮助或安慰。

---

## Expression Need

想表达观点。

---

## Avoidance Need

想远离某人。

---

不同角色权重不同。

---

例如：

彼方凪纱：

可能：

Connection 较低。

Observation 较高。

---

火守朱音：

可能：

Support 较高。

---

神永追记：

可能：

Information 较高。

---

# SOCIAL-LOOP-005 互动机会判断

角色判断：

是否有合适对象。

条件：

```text id="5m0plz"
Same Location

OR

Shared Goal

OR

Recent Event

OR

Need Compatibility
```

---

例如：

角色 A：

需要情报。

角色 B：

刚发现线索。

可能产生交流。

---

# SOCIAL-LOOP-006 互动选择

AI 根据：

```text id="q2tv3s"
Personality

+

Relationship

+

Goal

+

Risk

+

Trust
```

决定：

行为类型。

可能：

* 主动聊天；
* 等待别人；
* 观察；
* 回避；
* 争论；
* 帮助。

---

# SOCIAL-LOOP-007 信息更新

互动结束后。

更新：

## Knowledge

谁知道了什么。

---

## Confidence

相信程度。

---

## Source

信息来源。

---

## Memory

事件记录。

---

注意：

知道 ≠ 相信。

---

# SOCIAL-LOOP-008 关系更新

根据互动结果：

调整：

```text id="q8g7dt"
Trust

+

Friendship

+

Respect

+

Suspicion

+
 
Interest
```

---

一次对话影响较小。

长期积累产生重大变化。

---

# SOCIAL-LOOP-009 群体更新

检查：

是否产生：

* 新群体；
* 新联盟；
* 群体分裂；
* 成员退出。

---

例如：

三个角色连续合作调查。

可能形成：

调查小组。

---

# SOCIAL-LOOP-010 社交记忆

重要互动必须记录。

例如：

```text id="o6wn2w"
Event:

火守保护了雨宫。

Result:

雨宫 Trust +15

Memory:

"火守在危险时帮助了我。"
```

---

未来行为必须参考这些记忆。

---

# SOCIAL-LOOP-011 隐藏影响

部分社交变化不公开。

例如：

角色可能：

* 开始怀疑某人；
* 对某人产生兴趣；
* 改变态度。

但玩家暂时不知道。

---

这些隐藏变化会影响未来剧情。

---

# SOCIAL-LOOP-012 与案件系统连接

社交模拟不会直接制造案件。

但是会影响：

* 杀意；
* 动机；
* 选择；
* 证词；
* 调查方向。

例如：

长期冲突。

↓

信任下降。

↓

压力增加。

↓

黑白熊动机出现。

↓

角色可能做出极端选择。

---

# SOCIAL-LOOP-013 主角视角限制

玩家默认跟随：

仮名 楽。

因此：

社交模拟产生的信息需要经过：

```text id="7z5zq5"
事件发生

↓

角色感知

↓

主角是否知道
```

---

AI 不得因为后台模拟完成。

就直接告诉玩家。

---

# AI执行检查（AI Compliance Checklist）

每个 Tick 后：

* [ ] NPC 是否独立行动？
* [ ] 是否更新信息状态？
* [ ] 是否更新关系？
* [ ] 是否考虑心理状态？
* [ ] 是否允许误解？
* [ ] 是否允许沉默？
* [ ] 是否产生自然社交事件？
* [ ] 是否保持玩家视角限制？

---

# Designer Notes

Social Simulation Loop 是 Chapter 05 的核心。

它让 Paradiso 从：

"角色列表"

变成：

"一个正在运行的社会。"

十六个人被困在庄园中。

他们不会等待剧情。

他们会：

互相认识。

互相信任。

互相怀疑。

互相影响。

最终：

所有案件、选择与结局。

都会建立在这些长期积累的社会关系之上。

---

# Chapter 05 完成

本章定义：

* 对话系统；
* 信息传播；
* 谣言系统；
* 信任系统；
* 社交群体；
* 冲突；
* 合作；
* 日常事件；
* 社交循环。

下一章将进入：

# Chapter 06 — 黑白熊系统与动机生成系统（Monokuma & Motivation Engine）

该章节将定义：

* 黑白熊如何发布动机；
* 动机如何影响心理状态；
* 杀意如何产生；
* 为什么有人杀人；
* 为什么有人选择不杀；
* 案件发生前的隐藏模拟。

# Chapter 05 — 社交模拟系统（Social Simulation Engine）

## Section 5.9 — 社交事件系统（Social Events）

**依赖章节（Depends On）**

* Section 5.1 — 对话系统（Dialogue Engine）
* Section 5.2 — 对话流程（Conversation Flow）
* Section 5.6 — 社交群体系统（Social Groups）
* Section 5.7 — 冲突生成系统（Conflict Generation）
* Section 5.8 — 合作系统（Cooperation System）
* Chapter 03 — 时间系统（Time System）

**影响状态（Modified State）**

* World.EventQueue
* Character.Relationship
* Character.Psychology
* Character.Memory
* Character.GroupMembership
* World.SocialAtmosphere

---

# 目的（Purpose）

社交事件系统用于模拟：

> 即使没有案件发生，角色之间也会自然产生的生活事件。

Paradiso 不应成为：

"等待黑白熊发布事件，然后所有人行动。"

真正的共同生活中。

角色会：

* 聊天；
* 举办活动；
* 产生争执；
* 分享兴趣；
* 发现新的关系；
* 创造共同回忆。

---

# EVENT-001 社交事件定义

社交事件（Social Event）指：

> 由角色行为、环境变化或关系发展自然产生的非核心剧情事件。

它们通常不会直接推动主线。

但会影响：

* 人物关系；
* 心理状态；
* 未来选择；
* 后续剧情。

---

# EVENT-002 社交事件类型

Paradiso 将社交事件分为：

---

# 日常事件（Daily Event）

最常见。

例如：

* 一起吃饭；
* 聊天；
* 散步；
* 练习技能；
* 分享兴趣。

特点：

低危险。

高角色塑造价值。

---

# 兴趣事件（Interest Event）

来自角色才能。

例如：

## 超高校级园艺师

未香椎瑠璃香：

可能邀请其他人：

* 参观温室；
* 学习植物知识。

---

## 超高校级魔术师

黑羽運：

可能：

* 展示魔术；
* 组织小型表演。

---

## 超高校级芭蕾舞者

日曜日雪月花：

可能：

* 练习舞蹈；
* 邀请观看。

---

# GROUP-003 集体事件（Group Event）

由多个角色参与。

例如：

* 集体晚餐；
* 搜索新区域；
* 讨论庄园；
* 共同修理设施。

集体事件可以形成：

* 新关系；
* 新群体；
* 新冲突。

---

# CONFLICT-004 冲突事件（Conflict Event）

由关系或压力产生。

例如：

* 两人争论调查方法；
* 因误会产生矛盾；
* 对资源分配产生分歧。

冲突事件必须符合：

已有 Relationship。

不可无理由制造。

---

# COOP-005 合作事件（Cooperation Event）

角色主动合作完成某件事。

例如：

* 修复设备；
* 寻找物品；
* 准备活动。

合作事件可以提高：

* Trust；
* Group Stability；
* Shared Memory。

---

# EVENT-006 事件生成条件

社交事件生成概率受到：

```text
Location

+

Time

+

Character Availability

+

Relationship

+

Psychology

+

Recent Events

+

Personal Goals
```

影响。

---

# EVENT-007 主动发起者

社交事件应有：

Initiator。

发起者根据：

* Personality；
* Goal；
* Mood；
* Relationship。

决定。

---

例如：

火守朱音：

高概率：

* 邀请大家训练；
* 组织安全检查。

---

神永追记：

高概率：

* 发起讨论；
* 提出观察问题。

---

彼方凪纱：

较低概率。

但可能：

在关键时刻主动帮助某人。

---

# EVENT-008 事件规模

事件分为：

---

## Personal Event

参与：

1-2人。

例如：

私下谈话。

---

## Small Group Event

参与：

3-5人。

例如：

共同调查。

---

## Public Event

参与：

多数角色。

例如：

全员晚餐。

---

# EVENT-009 事件影响

每个事件结束后。

必须检查：

## Relationship

例如：

一起完成活动：

Trust +5

---

## Memory

记录：

"曾经一起经历某件事。"

---

## Psychology

例如：

开心事件：

Stress -10

Hope +5

---

## Social Graph

可能形成：

新关系。

新群体。

---

# EVENT-010 社交事件与主线

社交事件不是填充内容。

它们承担：

## 人物塑造

让玩家理解角色。

---

## 关系建设

让未来冲突更有影响。

---

## 案件准备

例如：

某次日常互动可能成为未来案件线索。

---

## 情感积累

死亡或背叛发生时。

玩家才会感受到重量。

---

# EVENT-011 随机性原则

社交事件需要随机。

但不是完全随机。

使用：

```text
Random Chance

+

Character Preference

+

Current Situation
```

共同决定。

---

禁止：

随机让两个毫无关系的人突然产生深厚友情。

---

# AI执行检查（AI Compliance Checklist）

生成社交事件时：

* [ ] 是否有合理发起原因？
* [ ] 是否符合角色性格？
* [ ] 是否考虑当前关系？
* [ ] 是否考虑时间地点？
* [ ] 是否影响未来状态？
* [ ] 是否避免所有事件围绕主角？
* [ ] 是否允许NPC主动创造事件？

---

# Designer Notes

社交事件是 Paradiso 与普通推理游戏最大的区别之一。

案件之间的空白时间。

不应该是暂停。

而应该是真正的生活。

角色会：

笑。

争吵。

合作。

误解。

成长。

因此，当危险真正降临时。

玩家面对的不是：

"一个NPC死亡。"

而是：

"一个曾经真实生活在这个世界中的人消失了。"

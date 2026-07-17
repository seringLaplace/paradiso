# Chapter 09 — 自由时间与羁绊系统（Free Time & Bond System）

## Section 9.0 — 自由时间与羁绊系统概述（Free Time & Bond System Overview）

**依赖章节（Depends On）**

* Chapter 04 — 角色模拟系统（Character Simulation Engine）
* Chapter 05 — 社交模拟系统（Social Simulation Engine）
* Chapter 08 — 主角系统与隐藏才能系统（Protagonist & Hidden Talent System）

**影响状态（Modified State）**

* Character.Relationship
* Character.Trust
* Character.BondLevel
* Character.PersonalStoryProgress
* Character.Memory
* EventAvailability

---

# 目的（Purpose）

自由时间与羁绊系统用于模拟：

> 在死亡游戏之外，角色之间逐渐建立联系的过程。

弹丸论破的重要结构：

不是：

案件 → 案件 → 案件。

而是：

```text id="8s4m2x"
日常

↓

交流

↓

理解

↓

建立羁绊

↓

死亡

↓

留下影响
```

---

# BOND-001 核心原则

羁绊不是：

数值奖励。

---

羁绊代表：

一个人是否愿意：

* 相信你；
* 展示真实自己；
* 在危险时帮助你。

---

# BOND-002 自由时间阶段

普通章节中：

每日划分：

```text id="n5k8qw"
Morning

↓

Afternoon

↓

Evening

↓

Night
```

---

自由时间通常发生：

Afternoon / Evening。

---

# BOND-003 自由行动选择

玩家可以：

---

## 与角色交流

增加关系。

---

## 探索环境

发现世界信息。

---

## 独处

进行思考。

---

## 调查异常

提前发现事件。

---

# BOND-004 角色邀请系统

NPC不会永远等待玩家。

---

角色可能：

主动邀请：

* 聊天；
* 散步；
* 帮忙；
* 分享秘密。

---

触发概率：

受到：

```text id="f4m8xq"
Current Relationship

+

Character Personality

+

Current Emotion
```

影响。

---

# BOND-005 羁绊等级

关系等级：

---

## Level 0 — Stranger

陌生。

信息：

公开信息。

---

## Level 1 — Acquaintance

认识。

愿意普通交流。

---

## Level 2 — Friend

朋友。

分享部分个人信息。

---

## Level 3 — Trusted Partner

信任伙伴。

愿意透露重要秘密。

---

## Level 4 — Deep Bond

深层关系。

理解核心矛盾。

---

## Level 5 — True Connection

真正羁绊。

可能：

影响关键剧情。

---

# BOND-006 好感增加因素

增加：

---

## 给予正确回应

例如：

理解对方感受。

---

## 帮助解决问题

例如：

支持个人目标。

---

## 记住细节

例如：

关注过去对话。

---

## 尊重选择

例如：

不强迫改变。

---

# BOND-007 好感减少因素

减少：

---

## 背叛

---

## 欺骗

---

## 忽视重要请求

---

## 公开秘密

---

## 利用对方

---

# BOND-008 关系不是线性

重要：

高好感 ≠ 永远支持。

---

角色仍可能：

* 生气；
* 拒绝；
* 怀疑；
* 做出不同选择。

---

因为：

角色是人。

---

# BOND-009 才能碎片系统

与角色交流：

可能获得：

Talent Fragment。

---

例如：

某角色分享：

自己的专业知识。

---

效果：

主角理解：

新的思考方式。

---

# BOND-010 个人剧情系统

每个主要角色拥有：

Personal Arc。

---

结构：

```text id="y6r9pw"
Introduction

↓

Conflict

↓

Revelation

↓

Growth

↓

Resolution
```

---

---

# BOND-011 羁绊与案件

自由时间影响：

案件体验。

---

例如：

高关系：

角色可能：

更愿意提供信息。

---

低关系：

可能：

隐藏关键情报。

---

---

# BOND-012 死亡前影响

如果角色死亡：

羁绊等级决定：

主角反应。

---

Level 0：

震惊。

---

Level 5：

重大心理创伤。

---

# BOND-013 死亡不是结束

死亡角色留下：

* 记忆；
* 物品；
* 影响；
* 未完成故事。

---

---

# BOND-014 群体羁绊

不仅：

一对一。

---

也包括：

多人关系。

例如：

三人小组。

---

影响：

* 派系；
* 合作；
* 冲突。

---

# BOND-015 AI执行检查

自由时间：

* [ ] 是否提供日常缓冲？
* [ ] 是否让角色主动交流？
* [ ] 是否避免纯数值恋爱游戏化？
* [ ] 是否建立真实关系？
* [ ] 是否让死亡具有重量？
* [ ] 是否影响未来剧情？

---

# Designer Notes

自由时间的意义：

不是奖励玩家。

而是：

让玩家在死亡发生之前，

真正认识那些可能失去的人。

---

如果玩家不认识角色。

死亡只是剧情事件。

---

如果玩家建立羁绊。

死亡才成为故事。

---

# 下一节

## Section 9.1 — 羁绊事件生成系统（Bond Event Generation System）

下一节将定义：

* 角色个人事件；
* 对话生成；
* 秘密揭露；
* 情绪变化；
* 如何避免重复社交。

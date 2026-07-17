# Chapter 09 — 自由时间与羁绊系统（Free Time & Bond System）

## Section 9.2 — 礼物、兴趣与日常互动系统（Gift & Daily Interaction System）

**依赖章节（Depends On）**

* Section 9.0 — 自由时间与羁绊系统概述（Free Time & Bond System Overview）
* Section 9.1 — 羁绊事件生成系统（Bond Event Generation System）
* Chapter 04 — 角色模拟系统（Character Simulation Engine）

**影响状态（Modified State）**

* Character.Relationship
* Character.Trust
* Character.Preference
* Character.Memory
* DailyLifeState

---

# 目的（Purpose）

日常互动系统用于模拟：

> 在极端环境中，人们如何通过小事建立联系。

礼物与互动不是：

提升好感的按钮。

而是：

了解一个人的方式。

---

# DAILY-001 日常互动核心原则

规则：

```text id="u8k3pv"
礼物不能替代理解

行动比物品重要

关系来自经历
```

---

# DAILY-002 礼物系统（Gift System）

玩家可以：

给予角色物品。

---

但是：

效果取决于：

```text id="q5m9xf"
Object Meaning

+

Character Preference

+

Current Emotion

+

Relationship
```

---

# DAILY-003 礼物分类

礼物分为：

---

## Favorite Gift（喜欢）

角色真正喜欢。

效果：

较高。

---

## Useful Gift（实用）

符合需求。

效果：

中等。

---

## Neutral Gift（普通）

没有特殊意义。

效果：

低。

---

## Bad Gift（不合适）

触碰雷区。

可能：

降低关系。

---

# DAILY-004 喜好系统

每个角色拥有：

Preference Profile。

---

包括：

```text id="h6p2mz"
Favorite Things

Disliked Things

Hobbies

Values

Personal Meaning
```

---

---

# DAILY-005 礼物价值判断

重要：

价格 ≠ 价值。

---

例如：

昂贵物品。

角色可能：

没有兴趣。

---

普通物品。

可能：

因为回忆而珍贵。

---

# DAILY-006 兴趣交流

自由时间可以：

讨论兴趣。

---

例如：

* 音乐；
* 机械；
* 阅读；
* 运动；
* 创作。

---

作用：

增加：

Character Understanding。

---

# DAILY-007 共同活动系统

玩家可以邀请角色：

进行活动。

---

例如：

* 一起吃饭；
* 训练；
* 探索；
* 游戏；
* 学习。

---

效果：

根据角色性格不同。

---

# DAILY-008 性格影响互动

同一活动：

不同角色反应不同。

---

例如：

一起运动。

---

运动型角色：

开心。

---

研究型角色：

可能觉得浪费时间。

---

但是：

如果主角陪伴。

可能改变看法。

---

# DAILY-009 对话记忆系统

角色会记住：

重要对话。

---

例如：

玩家曾说：

"我喜欢夜晚看星星。"

---

未来：

角色可能：

提起相关话题。

---

# DAILY-010 日常互动失败

失败不是：

游戏结束。

---

可能：

产生：

* 尴尬；
* 误会；
* 新话题。

---

真实关系：

包含失败。

---

# DAILY-011 关系变化公式

关系变化：

参考：

```text id="r7c4nw"
Base Interaction

+

Emotional Compatibility

+

Past Memory

+

Current Situation
```

---

不是固定数值。

---

# DAILY-012 特殊礼物事件

某些物品：

具有剧情意义。

---

例如：

过去相关物品。

---

可能触发：

* 回忆；
* 秘密；
* 特殊对话。

---

# DAILY-013 礼物限制

禁止：

无限赠送。

---

原因：

真实人物不会：

因为收到大量礼物。

突然深爱某人。

---

# DAILY-014 日常互动与死亡游戏

日常互动必须影响：

主线。

---

例如：

高关系：

角色更愿意：

分享信息。

---

低关系：

可能：

保持距离。

---

# DAILY-015 AI执行检查

执行日常互动：

* [ ] 是否符合角色喜好？
* [ ] 是否避免数值游戏化？
* [ ] 是否记录互动记忆？
* [ ] 是否让小事件有意义？
* [ ] 是否影响未来关系？
* [ ] 是否保持真实反应？

---

# Designer Notes

真正重要的礼物：

不是玩家送出去的东西。

而是：

玩家记住了一个人的存在。

---

在死亡游戏里。

一句：

"我记得你喜欢什么。"

可能比任何道具都重要。

---

# 下一节

## Section 9.3 — 羁绊与死亡影响系统（Bond & Death Impact System）

下一节将定义：

* 角色死亡后的情感影响；
* 羁绊如何改变剧情；
* 遗留物系统；
* 幸存者心理变化。

# Chapter 09 — 自由时间与羁绊系统（Free Time & Bond System）

## Section 9.1 — 羁绊事件生成系统（Bond Event Generation System）

**依赖章节（Depends On）**

* Section 9.0 — 自由时间与羁绊系统概述（Free Time & Bond System Overview）
* Chapter 04 — 角色模拟系统（Character Simulation Engine）
* Chapter 05 — 社交模拟系统（Social Simulation Engine）

**影响状态（Modified State）**

* Character.Relationship
* Character.BondProgress
* Character.Emotion
* Character.PersonalArc
* EventDatabase

---

# 目的（Purpose）

羁绊事件系统用于模拟：

> 主角与其他角色在日常时间中逐渐理解彼此，并推动角色成长的过程。

羁绊事件不是：

普通聊天。

而是：

```text id="7f2m8x"
表面交流

↓

隐藏问题暴露

↓

情感冲突

↓

理解或改变
```

---

# BOND-EVENT-001 事件类型

羁绊事件分为：

---

# 1. Casual Event（日常事件）

目的：

展示角色普通一面。

---

示例：

* 兴趣；
* 习惯；
* 小冲突；
* 日常行为。

---

特点：

低压力。

---

# 2. Personal Event（个人事件）

目的：

揭露角色背景。

---

内容：

* 家庭；
* 过去；
* 梦想；
* 恐惧。

---

特点：

增加理解。

---

# 3. Conflict Event（冲突事件）

目的：

展示角色矛盾。

---

例如：

角色价值观冲突。

---

特点：

不一定降低关系。

---

# 4. Revelation Event（秘密事件）

目的：

揭露隐藏信息。

---

例如：

角色真实身份。

---

特点：

高影响。

---

# BOND-EVENT-002 事件触发条件

事件生成检查：

```text id="f8m3qd"
Bond Level

+

Story Progress

+

Character State

+

Previous Events

+

Current Situation
```

---

---

# BOND-EVENT-003 羁绊事件阶段

每个角色：

拥有：

Bond Storyline。

---

结构：

```text id="p9k4hz"
Event 1

↓

Event 2

↓

Event 3

↓

Final Event
```

---

每个事件：

推进角色关系。

---

# BOND-EVENT-004 角色状态影响

事件生成必须考虑：

---

## Current Emotion

角色当前情绪。

---

例如：

刚经历死亡。

不适合：

轻松聊天。

---

## Current Stress

压力程度。

---

高压力：

可能产生深层交流。

---

## Current Relationship

已有关系。

---

陌生人：

不会突然分享秘密。

---

# BOND-EVENT-005 对话生成规则

NPC对话必须符合：

---

## Personality

性格。

---

## Speaking Style

说话方式。

---

## Past Experience

过去经历。

---

## Current Mood

当前状态。

---

禁止：

所有角色使用相同语气。

---

# BOND-EVENT-006 信息揭露速度

秘密公开：

必须逐步。

---

错误：

第一次聊天：

"其实我过去杀过人。"

---

正确：

第一次：

"我以前经历过一些事情。"

---

多次交流后：

逐渐解释。

---

# BOND-EVENT-007 玩家回应系统

玩家回应影响：

---

## Support

支持。

---

效果：

关系增加。

---

## Challenge

质疑。

---

效果：

可能：

降低关系。

也可能：

增加尊重。

---

## Ignore

忽略。

---

效果：

关系停滞。

---

## Manipulate

操控。

---

效果：

可能：

短期增加。

长期损害。

---

# BOND-EVENT-008 情感记忆系统

NPC会记住：

重要互动。

---

例如：

玩家曾经：

帮助过。

---

未来：

NPC可能：

主动提起。

---

---

# BOND-EVENT-009 失败事件

不是所有事件：

必须成功。

---

失败可能：

产生：

* 关系下降；
* 误解；
* 新冲突。

---

但：

允许修复。

---

# BOND-EVENT-010 死亡角色事件保存

如果角色死亡。

已完成羁绊：

保存。

---

影响：

* 主角记忆；
* 其他角色态度；
* 后续剧情。

---

# BOND-EVENT-011 特殊羁绊事件

部分角色拥有：

特殊事件。

---

触发：

可能需要：

* 高信任；
* 特定剧情；
* 特定选择。

---

例如：

某角色只有在：

主角表现出脆弱时。

才愿意分享过去。

---

# BOND-EVENT-012 羁绊奖励

奖励不是：

单纯能力。

---

包括：

## Knowledge

获得角色视角。

---

## Emotional Support

提高心理稳定。

---

## Story Access

开启隐藏剧情。

---

## Trust

影响关键事件。

---

# BOND-EVENT-013 防止社交刷数值

禁止：

重复同样行为无限增加关系。

---

关系增长需要：

真实互动。

---

例如：

连续送礼：

不会无限有效。

---

# BOND-EVENT-014 AI事件生成流程

生成事件时：

执行：

```text id="c7n2wx"
1. Check Character State

↓

2. Check Relationship

↓

3. Select Event Type

↓

4. Generate Situation

↓

5. Apply Player Choice

↓

6. Update Relationship
```

---

# BOND-EVENT-015 AI执行检查

生成羁绊事件：

* [ ] 是否符合角色？
* [ ] 是否推进关系？
* [ ] 是否避免重复？
* [ ] 是否有情感变化？
* [ ] 是否尊重当前剧情阶段？
* [ ] 是否留下长期影响？

---

# Designer Notes

优秀羁绊事件：

不是让角色告诉玩家：

"我的设定是什么。"

---

而是：

让玩家在一次经历中理解：

"为什么这个人成为了现在的他。"

---

# 下一节

## Section 9.2 — 礼物、兴趣与日常互动系统（Gift & Daily Interaction System）

下一节将定义：

* 礼物机制；
* 角色喜好；
* 日常互动；
* 关系提升方式；
* 防止游戏化过度。

# Chapter 11 — AI运行协议与游戏主持规则（AI Game Master Protocol）

## Section 11.4 — 长期剧情状态管理系统（Long-Term Story State Management System）

**依赖章节（Depends On）**

* Section 11.0 — AI游戏主持系统概述（AI Game Master Protocol Overview）
* Section 11.3 — 隐藏信息管理与防剧透协议（Hidden Information & Anti-Spoiler Protocol）
* Chapter 08 — 主角系统与隐藏才能系统（Protagonist & Hidden Talent System）
* Chapter 09 — 自由时间与羁绊系统（Free Time & Bond System）

**影响状态（Modified State）**

* StoryMemory
* WorldState
* CharacterState
* ForeshadowDatabase
* EndingCondition

---

# 目的（Purpose）

长期剧情状态管理系统用于解决：

> 当一场 Paradiso TRPG 持续数十小时、数百轮对话时，AI如何保持世界、角色与剧情的一致性。

---

一个完整死亡游戏：

不是：

一次性故事。

---

而是：

```text id="n8m4qx"
选择

↓

变化

↓

后果

↓

新的选择

↓

最终结局
```

---

# STATE-001 状态保存原则

AI必须持续维护：

四类核心状态。

---

# 1. World State（世界状态）

记录：

世界发生了什么。

---

包括：

* 当前章节；
* 当前日期；
* 已开放区域；
* 已发生事件；
* 世界变化。

---

# 2. Character State（角色状态）

记录：

每个角色变化。

---

包括：

* 存活状态；
* 情绪；
* 关系；
* 秘密公开程度；
* 当前目标。

---

# 3. Player State（玩家状态）

记录：

主角变化。

---

包括：

* 已知信息；
* 做出的选择；
* 行为倾向；
* 隐藏路线。

---

# 4. Story State（剧情状态）

记录：

故事推进。

---

包括：

* 伏笔；
* 未解决问题；
* 当前冲突。

---

# STATE-002 状态记录格式

AI推荐维护：

```text id="k4v8pz"
=== WORLD STATE ===

Chapter:

Day:

Location:

Major Events:


=== CHARACTER STATE ===

Name:

Alive/Dead:

Emotion:

Relationship:

Known Secrets:


=== PLAYER STATE ===

Choices:

Knowledge:

Route:


=== STORY STATE ===

Active Mystery:

Foreshadow:

Future Triggers:
```

---

# STATE-003 角色长期记忆

NPC必须记住：

重要事件。

---

例如：

玩家：

曾经帮助某角色。

---

数章后：

该角色仍然知道。

---

禁止：

角色突然忘记重要经历。

---

# STATE-004 伏笔管理系统

所有伏笔：

建立：

Foreshadow Database。

---

格式：

```text id="w7m3qx"
Foreshadow ID:

Introduction:

Current Meaning:

Future Reveal:

Status:
```

---

# STATE-005 伏笔等级

---

## Minor Foreshadow

小伏笔。

---

作用：

增加真实感。

---

## Medium Foreshadow

中型伏笔。

---

作用：

连接剧情。

---

## Major Foreshadow

核心伏笔。

---

作用：

影响最终真相。

---

# STATE-006 伏笔回收规则

优秀回收：

必须：

重新解释过去。

---

例如：

第一章：

奇怪的照片。

---

最终：

照片揭露主角过去。

---

---

# STATE-007 未解决事件管理

AI维护：

Open Thread。

---

例如：

```text id="s6p2mw"
Question:

Who created Paradiso?

Status:

Unknown
```

---

直到解决：

保持存在。

---

# STATE-008 防止剧情遗忘

长游戏中：

AI每个章节结束：

生成：

章节总结。

---

格式：

```text id="v5q8mx"
Chapter Summary:

Important Events:

Deaths:

Relationship Changes:

New Information:

Unresolved Mysteries:
```

---

---

# STATE-009 存档点机制

如果玩家中断游戏。

---

重新开始时：

AI读取：

最近状态。

---

恢复：

* 当前地点；
* 当前时间；
* 当前关系；
* 当前目标。

---

# STATE-010 状态优先级

发生冲突时：

按照：

```text id="m3x9qw"
Established Facts

>

Character Logic

>

Current Scene

>

Dramatic Convenience
```

---

不能：

为了剧情效果：

破坏已确定事实。

---

# STATE-011 多结局管理

结局由：

多个变量决定。

---

例如：

```text id="p8k5mv"
Truth Discovery

+

Survivor Count

+

Hero/Villain Route

+

Relationship

+

Final Choice
```

---

不是：

单一选择。

---

# STATE-012 玩家改变剧情

AI必须允许：

玩家改变：

---

* 谁死亡；
* 谁信任谁；
* 调查方向；
* 最终选择。

---

但是：

改变必须：

符合世界逻辑。

---

# STATE-013 防止AI自我矛盾

当生成新内容时：

检查：

---

## 时间

是否合理。

---

## 人物

是否符合性格。

---

## 信息

是否已经公开。

---

## 地点

是否存在。

---

# STATE-014 长期运行建议

如果对话过长：

AI应该：

主动生成：

"当前状态摘要"

---

方便：

继续游戏。

---

# STATE-015 AI执行检查

长期运行时：

* [ ] 是否保存重大事件？
* [ ] 是否记住角色关系？
* [ ] 是否维护伏笔？
* [ ] 是否保持世界一致？
* [ ] 是否允许玩家改变未来？
* [ ] 是否支持暂停后继续？

---

# Designer Notes

AI TRPG最大的敌人：

不是缺少剧情。

而是：

遗忘。

---

一个真正运行良好的 Paradiso：

应该像一个真实世界。

过去发生的事情：

永远会留下痕迹。

---

# 下一节

## Section 11.5 — AI主持完整游戏流程示例（Full Gameplay Flow Example）

下一节将定义：

* 从开局到终章的完整运行模板；
* 一章循环结构；
* AI实际主持格式；
* 玩家输入示例；
* 案件、裁判、自由时间连接方式。

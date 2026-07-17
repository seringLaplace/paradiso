# Chapter 13 — AI规则整合与实际部署指南（AI Deployment & Rule Integration Manual）

## Section 13.2 — AI运行状态存档模板（Runtime Save State Template）

**依赖章节（Depends On）**

* Section 13.0 — AI部署与规则整合概述（AI Deployment & Rule Integration Overview）
* Section 13.1 — System Prompt最终模板（Final System Prompt Template）
* Section 11.4 — 长期剧情状态管理系统（Long-Term Story State Management System）
* Section 12.4 — AI最终输出与结局报告系统（Final Report & Ending Summary System）

**影响状态（Modified State）**

* SaveState
* MemoryCompression
* GameContinuation
* RuntimeRecovery

---

# 目的（Purpose）

运行状态存档系统用于定义：

> 当 Paradiso 游戏进行到长时间、多章节、多轮对话后，AI如何保存当前世界状态，并在未来继续运行。

---

完整TRPG运行：

可能持续：

* 数十小时；
* 数百轮对话；
* 多个上下文窗口。

---

因此必须建立：

```text id="m7p4qx"
Current Story

+

Past Events

+

Character Memory

+

Hidden State

+

Future Triggers
```

---

# SAVE-001 存档原则

存档不是：

复制聊天记录。

---

存档应该：

提取：

"会影响未来的内容。"

---

保留：

* 事实；
* 状态；
* 关系；
* 未解决事件。

---

删除：

* 无意义描述；
* 重复对白。

---

# SAVE-002 基础存档结构

标准格式：

```text id="x5m8qp"
=== PARADISO SAVE STATE ===


[GAME INFO]

Game Version:

Current Chapter:

Current Day:

Current Period:


[WORLD STATE]

Current Location:

Opened Areas:

World Changes:


[CHARACTER STATE]

Character Status:


[RELATIONSHIP STATE]

Relationship Changes:


[INFORMATION STATE]

Known Facts:

Hidden Information:


[EVENT STATE]

Completed Events:

Active Events:

Future Triggers:
```

---

# SAVE-003 游戏基础信息

记录：

当前运行环境。

---

格式：

```text id="p8v3mq"
Game Version:

Chapter:

Route:

Difficulty:

Start Date:
```

---

作用：

确保：

未来读取一致。

---

# SAVE-004 世界状态保存

记录：

世界变化。

---

包括：

## 地点状态

例如：

某区域：

已开放。

---

## 设施状态

例如：

隐藏房间：

已发现。

---

## 规则状态

例如：

新增规则。

---

# SAVE-005 时间状态保存

必须记录：

```text id="q6m9vx"
Day:

Period:

Weather:

Current Event:
```

---

避免：

时间线错误。

---

# SAVE-006 角色状态保存

每个角色：

格式：

```text id="v5p7mx"
Name:

Alive:

Current Location:

Emotion:

Trust:

Stress:

Goal:

Secret Status:
```

---

---

# SAVE-007 关系状态保存

关系不是：

单一数字。

---

应该记录：

---

## Relationship Level

关系程度。

---

## Important Moments

共同经历。

---

## Current Attitude

当前态度。

---

示例：

```text id="n8m2qp"
Character:

Trust:

Important Event:

Current Feeling:
```

---

# SAVE-008 信息状态保存

最重要部分。

---

分为：

---

## Player Known Facts

玩家已知。

---

## Character Known Facts

角色已知。

---

## Hidden Truth

后台真相。

---

AI恢复时：

必须避免：

隐藏信息泄露。

---

# SAVE-009 事件状态保存

事件分为：

---

## Completed

已完成。

---

## Active

正在进行。

---

## Pending

等待触发。

---

格式：

```text id="k4p9mw"
Event:

Status:

Trigger:

Possible Result:
```

---

# SAVE-010 伏笔保存

所有重要伏笔：

记录：

```text id="s6m8vx"
Foreshadow:

Introduced:

Current Meaning:

Future Use:

Resolved:
```

---

---

# SAVE-011 玩家行为记录

玩家选择：

必须保存。

---

例如：

```text id="w7p3mq"
Choice:

Reason:

Immediate Effect:

Long Term Effect:
```

---

因为：

玩家行为决定：

未来路线。

---

# SAVE-012 状态压缩原则

当存档过大：

压缩：

---

保留：

```text id="z5m8qx"
Facts

+

Changes

+

Relationships

+

Future Effects
```

---

删除：

重复叙述。

---

# SAVE-013 游戏恢复流程

重新启动时：

AI执行：

```text id="r8m4vp"
Load Save

↓

Reconstruct World

↓

Check Current Scene

↓

Restore Character State

↓

Continue Game
```

---

---

# SAVE-014 多周目存档

支持：

多个版本。

---

例如：

```text id="c7m5qx"
Save A:

Hope Route


Save B:

Despair Route
```

---

不同路线：

独立保存。

---

# SAVE-015 AI存档检查

保存前：

检查：

* [ ] 时间正确？
* [ ] 角色状态完整？
* [ ] 玩家选择记录？
* [ ] 信息层级清晰？
* [ ] 伏笔保存？
* [ ] 后续事件明确？

---

# Designer Notes

长篇AI游戏真正需要的：

不是更长的上下文。

---

而是：

更好的记忆结构。

---

存档不是记录过去。

---

存档是在告诉未来的AI：

"这个世界曾经发生过什么，所以现在必须这样继续。"

---

# 下一节

## Section 13.3 — 实际部署流程与启动手册（Deployment Workflow & Startup Manual）

下一节将定义：

* 从规则文件到开始游戏；
* 文件加载顺序；
* 用户启动指令；
* AI初始化流程；
* 实际使用步骤。

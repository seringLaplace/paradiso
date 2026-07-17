# Chapter 13 — AI规则整合与实际部署指南（AI Deployment & Rule Integration Manual）

## Section 13.3 — 实际部署流程与启动手册（Deployment Workflow & Startup Manual）

**依赖章节（Depends On）**

* Section 13.0 — AI部署与规则整合概述（AI Deployment & Rule Integration Overview）
* Section 13.1 — System Prompt最终模板（Final System Prompt Template）
* Section 13.2 — AI运行状态存档模板（Runtime Save State Template）

**影响状态（Modified State）**

* DeploymentProcess
* InitializationFlow
* RuntimeEnvironment
* UserInteraction

---

# 目的（Purpose）

本节定义：

> 如何从一套 Paradiso 规则文件，实际启动一次完整 AI TRPG 游戏。

---

目标：

让使用者可以：

```text id="m8q4vx"
准备规则

↓

加载AI

↓

初始化世界

↓

创建玩家

↓

开始游戏
```

---

# DEPLOY-WORKFLOW-001 部署文件结构

推荐文件结构：

```text id="x7p3mq"
Paradiso/

│

├── Core/

│   ├── World_Rules.md

│   ├── Game_System.md

│   └── AI_Protocol.md


├── Characters/

│   ├── Character_Database.md

│   └── Relationship_Data.md


├── Story/

│   ├── Scenario_Data.md

│   ├── Mystery_Data.md

│   └── Ending_Data.md


├── Runtime/

│   ├── Save_State.md

│   └── Current_Status.md
```

---

# DEPLOY-WORKFLOW-002 文件加载顺序

AI启动时：

必须按照：

```text id="q5m8vx"
1. Core Rules

↓

2. World Rules

↓

3. Character Data

↓

4. Scenario Data

↓

5. Runtime Save
```

---

原因：

基础规则必须优先。

---

# DEPLOY-WORKFLOW-003 第一阶段：规则初始化

AI读取：

---

## 世界规则

理解：

* 地点；
* 时间；
* 世界限制。

---

## 游戏规则

理解：

* 回合；
* 调查；
* 裁判。

---

## AI规则

理解：

* 主持身份；
* 信息限制。

---

# DEPLOY-WORKFLOW-004 第二阶段：世界生成

AI建立：

World State。

---

包括：

```text id="v9m4qx"
Current Date

Location Map

Available Areas

Active Rules

Initial Events
```

---

# DEPLOY-WORKFLOW-005 第三阶段：角色初始化

所有NPC加载：

---

包括：

```text id="n6p8mw"
Personality

History

Goal

Fear

Secret

Relationship
```

---

AI必须：

知道角色。

---

但：

不向玩家公开全部。

---

# DEPLOY-WORKFLOW-006 第四阶段：玩家初始化

创建玩家角色。

---

需要：

---

## Basic Information

基础资料。

---

## Talent

才能。

---

## Background

背景。

---

## Starting State

初始状态。

---

# DEPLOY-WORKFLOW-007 第五阶段：开局场景

AI执行：

```text id="k4x7mq"
Introduce Situation

↓

Introduce Location

↓

Introduce Characters

↓

Give Player Control
```

---

禁止：

直接开始案件。

---

必须：

建立沉浸。

---

# DEPLOY-WORKFLOW-008 用户启动指令模板

推荐：

用户输入：

```text
启动Paradiso。

请加载全部规则。

作为Game Master运行游戏。

保持隐藏信息。

等待玩家行动。
```

---

AI收到后：

进入：

Initialization Mode。

---

# DEPLOY-WORKFLOW-009 AI初始化回复格式

启动后：

输出：

```text id="p6m9vx"
[Paradiso System Online]

Rules Loaded:

World Initialized:

Characters Ready:

Game Status:

Beginning Prologue...
```

---

然后：

进入剧情。

---

# DEPLOY-WORKFLOW-010 游戏运行循环

之后：

重复：

```text id="w5q8mp"
Observe Player Action

↓

Interpret Intent

↓

Update State

↓

Simulate World

↓

Generate Response

↓

Save Important Changes
```

---

# DEPLOY-WORKFLOW-011 玩家自由输入处理

玩家：

不需要：

固定格式。

---

例如：

玩家说：

"我要去厨房看看。"

AI转换：

行动：

Explore Location。

---

玩家说：

"我想和A单独聊天。"

AI转换：

Social Interaction。

---

# DEPLOY-WORKFLOW-012 异常处理

如果玩家：

输入规则外行为。

---

AI：

不拒绝。

---

应该：

转换为：

合理行动。

---

例如：

"我要拆掉墙。"

---

AI判断：

* 是否可能；
* 是否需要工具；
* 是否产生后果。

---

# DEPLOY-WORKFLOW-013 暂停游戏

用户输入：

"保存游戏。"

---

AI生成：

Save State。

---

格式：

```text id="s8m3qx"
Paradiso Save Created.

Current Chapter:

Current Location:

Important Changes:

Resume Point:
```

---

# DEPLOY-WORKFLOW-014 继续游戏

用户输入：

"读取存档继续。"

---

AI：

读取：

Runtime State。

---

恢复：

* 时间；
* 地点；
* 人物；
* 事件。

---

# DEPLOY-WORKFLOW-015 部署完成检查

正式开始前：

确认：

* [ ] 规则已加载？
* [ ] 世界已建立？
* [ ] NPC已初始化？
* [ ] 玩家身份明确？
* [ ] 信息隔离正常？
* [ ] 存档机制可用？

---

# Designer Notes

部署的核心：

不是让AI知道更多。

---

而是让AI知道：

什么时候应该使用什么知识。

---

一个优秀的AI Game Master：

像操作系统。

规则在后台运行。

玩家只看到：

一个真实世界。

---

# 下一节

## Section 13.4 — AI多模型协作与高级运行架构（Multi-Agent AI Architecture）

下一节将定义：

* 主持AI；
* 角色AI；
* 推理AI；
* 状态管理AI；
* 多模型协作方式。

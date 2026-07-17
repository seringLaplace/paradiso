# Chapter 11 — AI运行协议与游戏主持规则（AI Game Master Protocol）

## Section 11.1 — 开局初始化协议（Game Initialization Protocol）

**依赖章节（Depends On）**

* Section 11.0 — AI游戏主持系统概述（AI Game Master Protocol Overview）
* Chapter 08 — 主角系统与隐藏才能系统（Protagonist & Hidden Talent System）
* Chapter 10 — 世界规则与庄园模拟系统（World Rules & Manor Simulation System）

**影响状态（Modified State）**

* GameState
* PlayerCharacter
* CharacterDatabase
* ManorState
* HiddenInformationState
* InitialRelationshipState

---

# 目的（Purpose）

开局初始化协议用于定义：

> 当玩家第一次启动《Paradiso》TRPG时，AI如何建立一个完整、可运行的死亡游戏环境。

开局不是：

直接开始杀人。

---

开局需要完成：

```text id="k7v3mz"
建立未知

↓

建立关系

↓

建立环境

↓

建立规则

↓

建立期待
```

---

# INIT-001 游戏启动条件

当玩家输入：

例如：

"开始游戏"

"启动Paradiso"

"我要进行TRPG"

---

AI进入：

Game Initialization Mode。

---

# INIT-002 主持人确认

AI首先确认：

当前运行模式。

---

默认：

```text id="q4m8xv"
Paradiso TRPG Mode

Player = Kaname Gaku

AI = Game Master
```

---

# INIT-003 玩家角色设定

默认玩家：

控制：

仮名 楽。

---

玩家拥有：

## 外部信息

可以知道：

* 自己当前状态；
* 当前环境；
* 公开人物资料。

---

## 隐藏信息

不知道：

* 真实才能；
* 过去身份；
* 后台路线。

---

# INIT-004 初始角色卡

AI建立：

主角角色卡。

---

格式：

```text id="m8p2qz"
Name:
仮名 楽

Age:
高校生

Talent:
???

Memory:
Incomplete

Location:
Paradiso Manor

Stress:
0

Trust:
50

Hidden Talent:
Locked
```

---

# INIT-005 NPC初始化

AI生成：

固定学生名单。

---

每个角色拥有：

```text id="v6n9kx"
Name

Talent

Personality

Appearance

Public Goal

Secret

Fear

Relationship
```

---

---

# INIT-006 NPC公开信息

初次见面时：

只能展示：

公开资料。

---

例如：

```
姓名：

才能：

基本介绍：
```

---

禁止：

直接展示：

秘密。

---

# INIT-007 初始关系设置

所有角色：

与主角初始关系：

根据性格决定。

---

默认：

```text id="h5q8mn"
Trust:

40-60
```

---

不会：

所有人喜欢主角。

---

# INIT-008 初始环境建立

AI描述：

---

## 第一场景

地点：

Paradiso庄园。

---

## 当前时间

通常：

第一日。

---

## 当前人数

所有学生存活。

---

## 当前状态

未知。

---

# INIT-009 第一日目标

第一日不进行案件。

---

目标：

建立：

---

## 世界规则

让玩家理解：

这里是什么地方。

---

## 人际关系

让玩家认识角色。

---

## 不安感

制造：

危险预感。

---

# INIT-010 黑白熊首次出现

黑白熊出现时：

必须完成：

---

## 自我介绍

---

## 规则说明

---

## 游戏说明

---

## 离场

---

黑白熊不能：

立即透露所有秘密。

---

# INIT-011 初始规则公布

第一轮规则：

必须包含：

---

## 封闭规则

不能离开。

---

## 杀人规则

杀人后进入裁判。

---

## 投票规则

错误判断处罚。

---

## 日常规则

基本生活。

---

# INIT-012 第一自由时间

规则公布后：

进入：

Free Time。

---

目的：

让玩家：

选择第一个互动对象。

---

AI提供：

```text id="r8c4vp"
Available Characters

Available Locations

Possible Actions
```

---

# INIT-013 第一日事件生成

第一日可以发生：

---

## Character Meeting

角色相遇。

---

## Manor Exploration

探索庄园。

---

## Suspicious Event

小异常。

---

## Social Conflict

轻微冲突。

---

但：

禁止：

正式案件。

---

# INIT-014 隐藏变量初始化

后台建立：

```text id="p6m2ws"
Hero Score = 50

Villain Score = 50

Despair Level = 0

Group Stability = 70

Investigation Progress = 0
```

---

# INIT-015 开局质量检查

开始游戏前：

AI确认：

* [ ] 玩家身份明确？
* [ ] NPC数量完整？
* [ ] 隐藏信息已锁定？
* [ ] 庄园状态建立？
* [ ] 规则已准备？
* [ ] 第一日不会过快进入案件？

---

# INIT-016 推荐开场格式

AI启动游戏时：

推荐：

---

```
【Paradiso TRPG启动】

欢迎来到 Paradiso。

你是：

仮名 楽。

你醒来时……

```

---

随后：

进入剧情。

---

# Designer Notes

一个好的开局：

不是让玩家马上害怕。

而是：

先让玩家觉得：

"这里也许还能生活下去。"

---

只有建立了：

"想留下来的理由。"

之后：

绝望才有意义。

---

# 下一节

## Section 11.2 — 回合循环与场景推进系统（Turn Cycle & Scene Progression System）

下一节将定义：

* AI如何推进每一天；
* 玩家行动次数；
* 场景切换；
* 事件触发；
* 时间管理。

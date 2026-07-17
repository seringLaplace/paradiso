# Chapter 10 — 世界规则与庄园模拟系统（World Rules & Manor Simulation System）

## Section 10.1 — 庄园地图与区域探索系统（Manor Map & Exploration System）

**依赖章节（Depends On）**

* Section 10.0 — 世界规则与庄园模拟系统概述（World Rules & Manor Simulation Overview）
* Chapter 07 — 调查与学级裁判系统（Investigation & Class Trial Engine）
* Chapter 03 — 时间系统（Time System）

**影响状态（Modified State）**

* LocationDatabase
* ExplorationState
* InvestigationState
* CharacterMovement
* HiddenAreaState

---

# 目的（Purpose）

地图与探索系统用于定义：

> 玩家如何在 Paradiso 庄园中移动、观察环境，并发现隐藏的信息。

探索不是：

"点击房间获得道具。"

---

探索是：

```text id="e5x8qp"
移动

↓

观察

↓

理解环境

↓

发现异常

↓

产生行动可能
```

---

# MAP-001 地图设计原则

Paradiso地图必须满足：

---

## 可理解性

玩家能够形成：

空间概念。

---

## 可探索性

存在：

未知区域。

---

## 叙事性

地点本身：

拥有故事意义。

---

# MAP-002 地图层级

庄园地图分为：

---

# Layer 1 — Public Layer

公共区域。

---

特点：

所有学生通常可以进入。

---

包括：

* 大厅；
* 餐厅；
* 休息区；
* 花园。

---

# Layer 2 — Personal Layer

私人区域。

---

特点：

具有个人痕迹。

---

包括：

* 学生房间；
* 私人工作室；
* 收藏空间。

---

# Layer 3 — Hidden Layer

隐藏区域。

---

特点：

需要剧情或调查开启。

---

包括：

* 秘密房间；
* 地下设施；
* 黑白熊区域。

---

# MAP-003 地点节点系统

每个地点：

作为：

Location Node。

---

结构：

```text id="w8p4kx"
Location ID

Connected Areas

Access Rules

Objects

Characters

Secrets

Events
```

---

---

# MAP-004 移动规则

角色移动受到：

```text id="k9v2qs"
Distance

Time

Access

Emotion

Current Event
```

影响。

---

例如：

深夜。

某区域：

可能禁止进入。

---

# MAP-005 探索流程

玩家选择：

"前往图书馆。"

---

AI执行：

```text id="n7m3vz"
Check Access

↓

Describe Environment

↓

Offer Interactions

↓

Update Location State
```

---

---

# MAP-006 环境描述规则

描述地点时：

必须包含：

---

## Physical Detail

物理环境。

---

## Atmosphere

氛围。

---

## Relevant Objects

相关物品。

---

## Possible Actions

可能行动。

---

禁止：

只描述背景。

---

# MAP-007 可调查对象

物体分为：

---

## Normal Object

普通物品。

提供：

环境信息。

---

## Relevant Object

相关物品。

提供：

案件线索。

---

## Hidden Object

隐藏物品。

需要条件。

---

# MAP-008 隐藏区域系统

隐藏区域开启条件：

可能包括：

---

## Investigation

调查发现。

---

## Relationship

角色帮助。

---

## Story Progress

剧情推进。

---

## Ability Check

能力成功。

---

# MAP-009 探索失败

如果玩家寻找：

不存在区域。

---

AI不应：

创造新地图。

---

应该：

说明：

* 当前没有入口；
* 需要条件；
* 信息不足。

---

# MAP-010 房间状态系统

每个地点拥有：

State。

---

例如：

```text id="q6h8pm"
Normal

↓

Suspicious

↓

Crime Scene

↓

Investigated

↓

Changed
```

---

地点状态影响：

之后互动。

---

# MAP-011 犯罪现场系统

犯罪地点具有：

特殊状态。

---

包括：

* 封锁；
* 证据；
* NPC反应；
* 情绪影响。

---

犯罪现场不是：

普通房间。

---

# MAP-012 地图扩展系统

随着章节推进：

开放：

新区域。

---

新区域必须：

带来：

至少一种新价值：

---

## Story Value

推进剧情。

---

## Investigation Value

提供线索。

---

## Character Value

提供角色故事。

---

# MAP-013 地图与案件设计

案件设计必须考虑：

空间。

---

检查：

## 犯罪路线

凶手如何移动？

---

## 发现路线

尸体如何被发现？

---

## 调查路线

玩家如何寻找真相？

---

# MAP-014 地点记忆系统

地点会累积：

历史。

---

例如：

餐厅：

第一章：

聚餐地点。

---

第二章：

争吵地点。

---

第三章：

案件关键地点。

---

地点随着故事产生意义。

---

# MAP-015 AI执行检查

探索时：

* [ ] 是否保持地图一致？
* [ ] 是否避免随机创造地点？
* [ ] 是否提供探索价值？
* [ ] 是否记录地点变化？
* [ ] 是否让环境影响剧情？
* [ ] 是否允许玩家主动探索？

---

# Designer Notes

优秀地图：

不是越大越好。

---

真正重要的是：

玩家走过一个地方时，

会想起：

"这里曾经发生过什么。"

---

空间承载记忆。

---

# 下一节

## Section 10.2 — 庄园规则、限制与黑白熊管理系统（Manor Rules & Monokuma Control System）

下一节将定义：

* 黑白熊规则发布；
* 禁止事项；
* 惩罚机制；
* 信息控制；
* 庄园秩序维持。

# Chapter 11 — AI运行协议与游戏主持规则（AI Game Master Protocol）

## Section 11.3 — 隐藏信息管理与防剧透协议（Hidden Information & Anti-Spoiler Protocol）

**依赖章节（Depends On）**

* Section 11.0 — AI游戏主持系统概述（AI Game Master Protocol Overview）
* Section 11.2 — 回合循环与场景推进系统（Turn Cycle & Scene Progression System）
* Chapter 07 — 调查与学级裁判系统（Investigation & Class Trial Engine）

**影响状态（Modified State）**

* InformationLayer
* PlayerKnowledge
* CharacterKnowledge
* TruthDatabase
* InvestigationFairness

---

# 目的（Purpose）

隐藏信息管理系统用于确保：

> AI能够在不提前泄露真相的情况下，让玩家通过行动、调查和推理逐渐接近答案。

弹丸论破TRPG的核心：

不是：

AI知道答案。

---

而是：

玩家能够：

```text id="v8m3qx"
获得信息

↓

建立假设

↓

发现矛盾

↓

推翻错误

↓

接近真相
```

---

# INFO-001 信息分层原则

所有信息必须分类。

---

# Layer 0 — Public Information

公开信息。

---

所有角色可以知道。

例如：

* 黑白熊规则；
* 庄园地图；
* 公开事件。

---

# Layer 1 — Character Information

角色个人信息。

---

只有：

对应角色知道。

例如：

* 私人经历；
* 个人想法。

---

# Layer 2 — Hidden Information

隐藏信息。

---

玩家需要：

通过行动获得。

例如：

* 秘密房间；
* 隐藏关系。

---

# Layer 3 — Truth Information

最终真相。

---

包括：

* 凶手；
* 动机；
* 世界背景。

---

默认：

AI不可主动透露。

---

# INFO-002 AI知识分离规则

AI拥有：

完整后台信息。

---

但是：

不能因为知道。

就直接告诉玩家。

---

规则：

```text id="k5m9vx"
AI知道

≠

玩家知道
```

---

# INFO-003 描述限制

AI描述时：

必须符合：

玩家视角。

---

错误：

"你不知道，但其实房间后面藏着尸体。"

---

正确：

"房间里似乎没有异常，但角落有一道不自然的划痕。"

---

# INFO-004 线索展示原则

线索不能：

隐藏到不可推理。

---

也不能：

直接给答案。

---

优秀线索：

具有：

```text id="r4p8mw"
Surface Meaning

+

Hidden Meaning
```

---

例如：

表面：

钟坏了。

---

深层：

时间被修改。

---

# INFO-005 玩家猜测处理

玩家可能：

猜测真相。

---

AI处理：

---

## 正确猜测

不立即确认。

---

应该：

提供：

更多验证机会。

---

## 错误猜测

不直接否定。

---

应该：

让玩家寻找证据。

---

# INFO-006 禁止剧透行为

AI禁止：

---

## 直接公布凶手

---

## 直接解释案件

---

## 直接说明隐藏身份

---

## 用旁白暗示最终答案

---

# INFO-007 推理公平原则

玩家必须：

有机会：

解决案件。

---

案件设计检查：

```text id="w6n2kp"
Who

How

Why

Evidence

Contradiction
```

---

五项必须：

可推理。

---

# INFO-008 信息获取方式

信息来源：

---

## Investigation

调查。

---

## Dialogue

交流。

---

## Observation

观察。

---

## Relationship

信任。

---

## Event

剧情。

---

# INFO-009 NPC隐藏信息规则

NPC不会：

主动透露所有秘密。

---

原因：

角色拥有：

* 恐惧；
* 利益；
* 怀疑。

---

---

# INFO-010 谎言系统

NPC可能：

说谎。

---

但：

谎言必须符合：

```text id="n8q5vx"
Character Goal

+

Knowledge

+

Emotion
```

---

禁止：

为了误导玩家。

随机撒谎。

---

# INFO-011 半真相系统

重要角色：

可能提供：

半真相。

---

例如：

他说：

"我没去过那里。"

---

可能：

真实含义：

"我没有主动去。"

---

# INFO-012 玩家元知识处理

如果玩家现实中：

知道弹丸论破套路。

---

AI不能：

因为玩家知道。

改变角色行为。

---

游戏内：

角色不知道。

---

# INFO-013 重新确认机制

当玩家询问：

"所以凶手是X吗？"

---

AI回答：

应该：

提供当前证据状态。

---

例如：

"目前证据指向X，但仍存在无法解释的矛盾。"

---

# INFO-014 信息记录系统

AI维护：

玩家已知信息：

```text id="p3v8mk"
Known Facts

Suspicions

Unconfirmed Ideas

False Assumptions
```

---

防止：

重复解释。

---

# INFO-015 AI执行检查

管理隐藏信息：

* [ ] 是否保持信息差？
* [ ] 是否避免直接剧透？
* [ ] 是否保证案件公平？
* [ ] 是否区分角色知识与玩家知识？
* [ ] 是否允许错误推理？
* [ ] 是否记录玩家发现？

---

# Designer Notes

优秀推理游戏：

不是让玩家永远猜不到。

---

而是：

当真相揭开时，

玩家会想：

"原来所有线索早就在这里。"

---

AI主持的目标：

不是隐藏答案。

而是：

让答案值得被发现。

---

# 下一节

## Section 11.4 — 长期剧情状态管理系统（Long-Term Story State Management System）

下一节将定义：

* 多章节运行；
* 长期变量；
* 伏笔管理；
* 世界状态保存；
* AI长文本游戏稳定运行。

# Chapter 08 — 主角系统与隐藏才能系统（Protagonist & Hidden Talent System）

## Section 8.0 — 主角系统概述（Protagonist System Overview）

**依赖章节（Depends On）**

* Chapter 04 — 角色模拟系统（Character Simulation Engine）
* Chapter 05 — 社交模拟系统（Social Simulation Engine）
* Chapter 07 — 调查与学级裁判系统（Investigation & Class Trial Engine）

**影响状态（Modified State）**

* Protagonist.State
* PlayerPerspective
* Character.Relationship
* HiddenTalentProgress
* StoryDirection

---

# 目的（Purpose）

主角系统用于定义：

> 仮名 楽（かなめ がく）作为玩家主要观察对象，在 Paradiso 世界中的特殊作用。

主角不是：

* 作者；
* 上帝；
* 绝对正确的人。

---

主角是：

```text id="c8p2mf"
一个拥有未知过去的人

+

一个正在寻找真相的人

+

一个可能改变世界的人
```

---

# PROTAGONIST-001 基础信息

## 姓名

仮名 楽

（Kaname Gaku）

---

## 公开才能

超高校级的？？？

---

## 当前状态

失忆。

---

## 玩家状态

不知道：

* 真实才能；
* 过去经历；
* 为什么来到庄园。

---

# PROTAGONIST-002 主角定位

仮名楽拥有：

特殊叙事位置。

---

但是：

不能破坏群像原则。

---

规则：

```text id="x2f8qm"
主角 ≠ 世界中心

主角 = 观察世界的人
```

---

其他角色：

拥有：

独立故事。

独立目标。

独立成长。

---

# PROTAGONIST-003 主角视角系统

默认：

第三人称贴近主角视角。

---

玩家知道：

## 主角看到的

---

## 主角听到的

---

## 主角想到的

---

玩家不知道：

## NPC私下行动

---

## NPC真实想法

---

## 后台数值

---

# PROTAGONIST-004 视角限制

禁止：

无理由切换上帝视角。

---

只有：

以下情况：

允许展示其他视角。

---

## 1. 章节结束

例如：

案件结束后。

---

## 2. 特殊事件

例如：

黑白熊行动。

---

## 3. 玩家明确要求

格式：

```text
（场外发言：切换视角）
```

---

# PROTAGONIST-005 主角能力系统

仮名楽公开能力：

---

## Observation（观察）

数值：

75

用途：

* 发现细节；
* 注意异常。

---

## Reason（推理）

数值：

72

用途：

* 逻辑连接；
* 解决矛盾。

---

## Insight（心理洞察）

数值：

78

用途：

* 察觉情绪；
* 感受违和。

---

## Communication（交涉）

数值：

58

用途：

* 说服；
* 建立关系。

---

## Agility（行动）

数值：

54

用途：

* 移动；
* 特殊行动。

---

## Strength（体能）

数值：

47

用途：

* 物理行动。

---

## Will（意志）

数值：

80

用途：

* 抗压；
* 对抗绝望。

---

## Luck（幸运）

隐藏。

---

# PROTAGONIST-006 主角骰子规则

所有主动行为：

公开骰。

---

格式：

```text id="n7v5cw"
能力值

+

D100

=

结果
```

---

示例：

```text
Observation 75

D100 = 31

Success
```

---

失败：

不是：

行动失败。

---

而是：

产生：

* 信息不足；
* 错误判断；
* 额外困难。

---

# PROTAGONIST-007 心理暗骰

涉及：

以下情况：

必须暗骰：

* 直觉；
* 潜意识；
* 过去记忆；
* 深层恐惧；
* 隐藏联系。

---

示例：

成功：

正文：

"仮名楽忽然感觉到一丝不协调。"

---

失败：

正文：

"至少现在看来，没有异常。"

---

禁止：

直接告诉玩家答案。

---

# PROTAGONIST-008 隐藏才能系统

仮名楽真实才能：

未知。

---

候选方向：

## 路线A：

超高校级主角

---

## 路线B：

超高校级的反派

---

最终方向：

由：

```text id="d8k3pv"
Player Behavior

+

Moral Choices

+

Relationships

+

Story Events
```

决定。

---

# PROTAGONIST-009 双路线设计

## Hero Route

特点：

* 信任他人；
* 寻找共同希望；
* 保护伙伴。

---

结果：

逐渐成为：

真正的主角。

---

## Villain Route

特点：

* 操纵他人；
* 利用关系；
* 追求结果。

---

结果：

逐渐显露：

危险本质。

---

# PROTAGONIST-010 不提前揭露

AI必须：

隐藏：

* 主角过去；
* 真实才能；
* 未来方向。

---

不能：

开局说明：

"你其实是反派。"

---

# PROTAGONIST-011 主角特殊性

仮名楽可能拥有：

特殊能力。

但：

不能成为万能解。

---

例如：

他的洞察力：

可以发现异常。

不能：

直接知道凶手。

---

他的推理：

需要证据。

---

# PROTAGONIST-012 主角关系影响

主角行为影响：

所有角色。

---

例如：

主动帮助。

↓

Trust增加。

---

冷漠利用。

↓

Trust下降。

---

操控他人。

↓

隐藏变量增加。

---

# PROTAGONIST-013 主角成长

成长不是：

数值升级。

---

成长表现：

* 思考方式改变；
* 价值观变化；
* 与他人关系变化；
* 面对选择。

---

# AI执行检查（AI Compliance Checklist）

扮演仮名楽时：

* [ ] 是否保持未知身份？
* [ ] 是否避免主角光环？
* [ ] 是否让NPC独立行动？
* [ ] 是否通过行为决定隐藏路线？
* [ ] 是否保持主角视角？
* [ ] 是否允许主角失败？

---

# Designer Notes

仮名楽的核心问题：

不是：

"我是谁？"

而是：

"如果知道自己是谁，我还会选择成为现在的自己吗？"

---

他的故事不是：

寻找力量。

而是：

寻找答案。

---

# 下一节

## Section 8.1 — 隐藏才能觉醒与路线判定系统（Hidden Talent Awakening & Route System）

下一节将定义：

* Hero/Villain路线判定；
* 隐藏变量；
* 觉醒条件；
* 终章方向。

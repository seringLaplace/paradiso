# Chapter 08 — 主角系统与隐藏才能系统（Protagonist & Hidden Talent System）

## Section 8.1 — 隐藏才能觉醒与路线判定系统（Hidden Talent Awakening & Route System）

**依赖章节（Depends On）**

* Section 8.0 — 主角系统概述（Protagonist System Overview）
* Chapter 04 — 角色模拟系统（Character Simulation Engine）
* Chapter 05 — 社交模拟系统（Social Simulation Engine）
* Chapter 06 — 黑白熊系统与动机生成系统（Monokuma & Motivation Engine）

**影响状态（Modified State）**

* HiddenTalentProgress
* HeroRouteScore
* VillainRouteScore
* Protagonist.Identity
* StoryDirection
* EndingCondition

---

# 目的（Purpose）

隐藏才能系统用于模拟：

> 仮名 楽真实身份逐渐浮现，以及玩家行为如何决定他最终成为怎样的人。

核心问题：

不是：

"主角原本是什么？"

而是：

"当拥有过去的自己回来时，现在的自己是否还会选择相同道路？"

---

# TALENT-001 真实才能设定

仮名 楽真实才能：

```text
超高校级主角

OR

超高校级的反派
```

---

该结果：

不是固定。

由游戏过程决定。

---

# TALENT-002 双身份设计

## 表层身份

玩家当前看到的：

```text
超高校级的？？？
```

---

## 深层身份

隐藏：

```text
Past Identity
```

---

## 最终身份

由：

现在的选择。

决定。

---

# TALENT-003 隐藏变量系统

后台维护：

---

## Hero Score（主角倾向）

范围：

0-100。

---

## Villain Score（反派倾向）

范围：

0-100。

---

初始：

```text
Hero Score = 50

Villain Score = 50
```

---

# TALENT-004 Hero Score增加条件

以下行为增加：

---

## 保护他人

例如：

冒险救人。

---

## 主动相信

例如：

给予第二次机会。

---

## 分享信息

例如：

公开关键线索。

---

## 承担责任

例如：

承认自己的错误。

---

## 寻求合作

例如：

建立共同目标。

---

# TALENT-005 Villain Score增加条件

以下行为增加：

---

## 操控他人

例如：

故意利用信任。

---

## 隐瞒关键事实

例如：

为了个人目标隐藏信息。

---

## 牺牲他人利益

例如：

认为结果比过程重要。

---

## 欺骗

例如：

制造错误方向。

---

## 将人视为工具

例如：

只关注效率。

---

# TALENT-006 灰色行为处理

不是所有冷酷行为都是反派。

---

例如：

为了救更多人。

选择牺牲少数。

---

系统判断：

考虑：

```text id="w7n4kx"
Motivation

+

Method

+

Consequence

+

Reflection
```

---

行为本身不是唯一标准。

---

# TALENT-007 路线判定

最终：

比较：

```text
Hero Score

VS

Villain Score
```

---

但是：

不是简单高低。

---

还考虑：

* 关键选择；
* 终章行动；
* 对伙伴态度；
* 面对过去的反应。

---

# TALENT-008 Hero Route

触发倾向：

主角逐渐成为：

超高校级主角。

---

特点：

## 信任

相信：

人与人可以改变。

---

## 责任

愿意承担：

领导角色。

---

## 希望

即使面对绝望：

仍选择前进。

---

# TALENT-009 Villain Route

触发倾向：

主角逐渐成为：

超高校级的反派。

---

特点：

## 控制

希望掌握局势。

---

## 利用

认为人性可以计算。

---

## 结果优先

为了目标：

接受牺牲。

---

# TALENT-010 反派路线限制

重要：

反派路线不是：

坏人路线。

---

优秀反派：

可能：

* 理解他人；
* 保护某些人；
* 拥有自己的正义。

---

区别：

不是善恶。

而是：

选择方式。

---

# TALENT-011 才能觉醒事件

真实才能不会突然出现。

---

觉醒阶段：

---

## Stage 0

未知。

---

## Stage 1

出现异常表现。

例如：

超出普通能力的判断。

---

## Stage 2

过去碎片出现。

---

## Stage 3

部分记忆恢复。

---

## Stage 4

面对真实身份。

---

## Stage 5

主动选择：

成为谁。

---

# TALENT-012 记忆恢复规则

记忆恢复：

必须通过：

* 剧情事件；
* 心理触发；
* 黑白熊安排；
* 关键人物关系。

---

禁止：

突然恢复全部记忆。

---

# TALENT-013 过去身份影响

过去身份会：

解释：

为什么拥有某些能力。

---

但：

不能决定现在。

---

例如：

过去是反派。

现在仍可以选择帮助别人。

---

# TALENT-014 NPC对主角身份反应

不同角色：

反应不同。

---

例如：

彼方凪纱：

可能关注：

"现在的你是什么样。"

---

神永追记：

可能关注：

"过去的你是否真的改变。"

---

伏屋金紫：

可能关注：

"这个身份有什么价值。"

---

# TALENT-015 终局判定

最终身份影响：

但不完全决定结局。

---

结局由：

```text id="y6f9cz"
Hidden Talent Route

+

World Truth

+

Survivor State

+

Player Choices
```

共同决定。

---

# AI执行检查（AI Compliance Checklist）

执行隐藏才能系统时：

* [ ] 不提前揭露身份？
* [ ] 不把反派等同于邪恶？
* [ ] 根据行为变化？
* [ ] 保留灰色选择？
* [ ] 让过去与现在产生冲突？
* [ ] 让玩家主动决定最终身份？

---

# Designer Notes

仮名楽真正的才能：

不是：

"主角"

或者：

"反派"。

---

真正的才能是：

他拥有改变故事方向的能力。

---

问题不是：

"他过去是谁。"

而是：

"在知道过去之后，他选择成为谁。"

---

# 下一节

## Section 8.2 — 主角记忆、秘密与真相揭露系统（Memory, Secret & Revelation System）

下一节将定义：

* 失忆机制；
* 主角过去信息管理；
* 记忆碎片；
* 黑白熊如何利用主角秘密；
* 最终身份揭露流程。

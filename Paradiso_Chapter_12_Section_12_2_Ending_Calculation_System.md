# Chapter 12 — 终局、结局与多路线系统（Ending & Branching Route System）

## Section 12.2 — 多结局生成与结局演算系统（Ending Calculation System）

**依赖章节（Depends On）**

* Section 12.0 — 终局与多路线系统概述（Ending & Branching Route System Overview）
* Section 12.1 — 最终章节与真相揭露系统（Final Chapter & Truth Revelation System）
* Chapter 09 — 自由时间与羁绊系统（Free Time & Bond System）
* Chapter 11 — AI运行协议与游戏主持规则（AI Game Master Protocol）

**影响状态（Modified State）**

* EndingScore
* RouteProbability
* FinalNarrative
* CharacterResolution
* WorldOutcome

---

# 目的（Purpose）

结局演算系统用于定义：

> AI如何根据玩家整个游戏过程，而不是单一选择，生成最终结局。

---

结局计算不是：

```text id="m4x8qp"
最后选择 = 结局
```

---

而是：

```text id="k7p3vz"
整个旅程

↓

累计变量

↓

最终选择

↓

结局生成
```

---

# END-CALC-001 核心变量

最终结局由：

六类变量决定。

---

```text id="w8n5mq"
Truth

Hope

Despair

Bond

Choice

Consequence
```

---

# END-CALC-002 Truth Score（真相值）

代表：

玩家追求真相的程度。

---

增加：

* 调查隐藏区域；
* 完成推理；
* 发现过去；
* 挑战谎言。

---

降低：

* 放弃调查；
* 接受错误解释；
* 回避事实。

---

# END-CALC-003 Hope Score（希望值）

代表：

玩家是否相信人与关系。

---

增加：

* 建立羁绊；
* 帮助他人；
* 选择合作；
* 接受差异。

---

降低：

* 背叛；
* 利用他人；
* 孤立行动。

---

# END-CALC-004 Despair Score（绝望值）

代表：

玩家受到环境影响程度。

---

增加：

* 极端选择；
* 放弃他人；
* 接受黑白熊逻辑。

---

降低：

* 保持信念；
* 建立连接；
* 寻找意义。

---

# END-CALC-005 Bond Score（羁绊值）

不是：

所有角色好感总和。

---

而是：

重要关系质量。

---

计算：

```text id="q5m8vx"
Depth

+

Trust

+

Shared Experience

+

Final Loyalty
```

---

# END-CALC-006 Choice Score（选择倾向）

记录：

玩家关键选择。

---

例如：

面对冲突：

选择：

---

## Punishment

惩罚。

---

## Understanding

理解。

---

## Sacrifice

牺牲。

---

## Escape

逃避。

---

---

# END-CALC-007 Consequence Score（后果变量）

记录：

玩家行为造成的世界变化。

---

例如：

* 谁死亡；
* 谁幸存；
* 哪些关系破裂；
* 哪些秘密公开。

---

# END-CALC-008 路线判断公式

AI参考：

```text id="z6p2mw"
Route =
Truth

+

Hope

+

Bond

+

Choice

-

Despair
```

---

注意：

不是数学计算。

---

而是：

叙事判断模型。

---

# END-CALC-009 Hope Route条件

希望路线通常需要：

---

## High Truth

知道真相。

---

## High Bond

相信他人。

---

## Low Despair

拒绝绝望逻辑。

---

结果：

寻找离开的方式。

---

# END-CALC-010 Truth Route条件

真相路线：

通常：

---

## Highest Truth

完整理解。

---

## Medium Bond

关系不一定完美。

---

## Rational Choice

选择面对现实。

---

结果：

接受残酷答案。

---

# END-CALC-011 Despair Route条件

绝望路线：

可能：

---

## Low Trust

不相信他人。

---

## High Despair

接受黑白熊价值观。

---

## Repeated Negative Choices

持续选择破坏。

---

结果：

玩家成为游戏的一部分。

---

# END-CALC-012 特殊结局条件

特殊结局：

来自：

非标准行为。

---

例如：

---

## All Bond Route

完成全部重要羁绊。

---

## Survivor Route

最大化幸存。

---

## Sacrifice Route

主动承担代价。

---

## Unknown Route

AI根据行为生成。

---

# END-CALC-013 结局演出生成

生成结局时：

必须包含：

---

## Immediate Result

即时结果。

---

## Character Fate

角色未来。

---

## World Change

世界变化。

---

## Emotional Closure

情感收束。

---

# END-CALC-014 防止机械结局

AI禁止：

直接输出：

"你获得A结局。"

---

应该：

通过故事表现。

---

例如：

不是：

"这是希望结局。"

---

而是：

展示：

幸存者如何走向未来。

---

# END-CALC-015 AI执行检查

生成结局时：

* [ ] 是否考虑整个旅程？
* [ ] 是否响应玩家选择？
* [ ] 是否解释变量变化？
* [ ] 是否给予角色未来？
* [ ] 是否避免简单评分？
* [ ] 是否具有情感结束感？

---

# Designer Notes

结局不是奖励。

---

结局是：

玩家一路以来所有选择的回声。

---

一个玩家选择相信别人。

和一个玩家选择独自生存。

即使面对同一个真相，

也应该看到不同的未来。

---

# 下一节

## Section 12.3 — 角色终局与个人命运系统（Character Final Resolution System）

下一节将定义：

* 幸存角色结局；
* 死亡角色遗产；
* NPC未来；
* 羁绊收束；
* 角色弧线完成。

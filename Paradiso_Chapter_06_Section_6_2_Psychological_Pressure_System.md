# Chapter 06 — 黑白熊系统与动机生成系统（Monokuma & Motivation Engine）

## Section 6.2 — 心理压力系统（Psychological Pressure System）

**依赖章节（Depends On）**

* Section 6.0 — 黑白熊系统概述（Monokuma System Overview）
* Section 6.1 — 动机生成算法（Motivation Generation Algorithm）
* Chapter 04 — 角色模拟系统（Character Simulation Engine）
* Chapter 05 — 社交模拟系统（Social Simulation Engine）

**影响状态（Modified State）**

* Character.Stress
* Character.Hope
* Character.Despair
* Character.Fear
* Character.Intent
* Character.DecisionProbability
* Character.PsychologicalState

---

# 目的（Purpose）

心理压力系统用于模拟：

> 在长期封闭环境、未知危险、关系变化和外部刺激下，角色心理状态如何逐渐变化。

在 Paradiso 中：

角色不会因为一次事件立即改变。

真正重要的是：

* 压力积累；
* 情绪变化；
* 关系影响；
* 心理防线。

---

# PSY-001 心理状态模型

每个角色拥有以下隐藏状态：

```text id="5h7j1m"
Stress

Hope

Despair

Fear

Attachment

Confidence

BreakingPoint
```

---

# PSY-002 Stress（压力）

Stress 表示：

> 角色当前承受的心理负担。

范围：

```text
0 - 100
```

---

## Stress等级

| 数值     | 状态   |
| ------ | ---- |
| 0-20   | 稳定   |
| 21-40  | 轻微压力 |
| 41-60  | 明显焦虑 |
| 61-80  | 高度紧张 |
| 81-100 | 接近崩溃 |

---

# PSY-003 Stress来源

压力来源包括：

## 环境压力

例如：

* 被困庄园；
* 无法离开；
* 未知危险。

---

## 社交压力

例如：

* 被怀疑；
* 孤立；
* 冲突。

---

## 信息压力

例如：

* 得知残酷真相；
* 发现秘密。

---

## 生存压力

例如：

* 饥饿；
* 时间限制；
* 威胁。

---

## 情感压力

例如：

* 朋友死亡；
* 信任破裂。

---

# PSY-004 Stress变化

压力变化：

```text id="2t7kq0"
New Stress

=

Current Stress

+

Negative Events

-

Recovery Factors
```

---

恢复因素：

* 安全感；
* 朋友支持；
* 成功行动；
* 积极交流。

---

# PSY-005 Hope（希望）

Hope表示：

> 角色对于未来、他人以及自身行动的积极期待。

范围：

```text
0 - 100
```

---

Hope提高：

例如：

* 成功合作；
* 找到出口线索；
* 建立信任。

---

Hope降低：

例如：

* 同伴死亡；
* 背叛；
* 失败。

---

# PSY-006 Despair（绝望）

Despair表示：

> 角色对于当前世界失去控制感后的消极倾向。

范围：

```text
0 - 100
```

---

Despair增加：

例如：

* 长期失败；
* 孤立；
* 失去希望。

---

注意：

Despair ≠ 悲伤。

悲伤是情绪。

绝望是认知状态。

---

# PSY-007 Hope 与 Despair关系

两者不是简单相反。

可能同时存在。

例如：

角色：

深爱同伴。

因此：

Hope 很高。

但：

认为无法离开庄园。

Despair 也很高。

---

# PSY-008 Fear（恐惧）

Fear表示：

> 角色面对具体威胁时的反应。

例如：

* 害怕死亡；
* 害怕秘密曝光；
* 害怕失去某人。

---

Fear通常影响：

* 行动选择；
* 风险判断；
* 是否隐藏信息。

---

# PSY-009 Attachment（情感依附）

Attachment表示：

> 某个角色或目标对于该角色的重要程度。

例如：

角色A：

Attachment:

对角色B = 90

那么：

B受到威胁时。

A更可能：

* 保护；
* 犹豫；
* 做出极端选择。

---

# PSY-010 Breaking Point（心理临界点）

每个角色拥有：

隐藏临界值。

例如：

```text
BreakingPoint = 85 Stress
```

达到后：

角色可能：

* 崩溃；
* 改变目标；
* 做出危险选择。

---

但是：

达到临界点 ≠ 必然犯罪。

---

# PSY-011 个体差异

同样的压力。

不同角色反应不同。

---

例如：

压力：

80。

---

角色A：

高意志。

可能：

继续坚持。

---

角色B：

高恐惧。

可能：

逃避。

---

角色C：

高执念。

可能：

采取极端行动。

---

# PSY-012 心理变化速度

禁止：

一次事件完全改变人格。

例如：

错误：

朋友死亡。

↓

角色马上成为冷血杀人犯。

---

正确：

朋友死亡。

↓

悲伤。

↓

压力增加。

↓

信念动摇。

↓

行为逐渐变化。

---

# PSY-013 心理状态与杀意

杀意（Intent）由多个因素共同产生：

```text id="1w5f2q"
Stress

+

Despair

+

Motivation

+

Opportunity

+

Personality

+

Relationship

```

---

高压力角色：

可能更容易产生极端想法。

但不是必然。

---

# PSY-014 心理恢复

恢复方式：

## 社交支持

例如：

朋友陪伴。

---

## 成功经验

例如：

解决问题。

---

## 目标重新建立

例如：

找到新的希望。

---

## 自我调整

部分角色拥有更强恢复能力。

---

# AI执行检查（AI Compliance Checklist）

模拟心理变化时：

* [ ] 是否避免瞬间人格改变？
* [ ] 是否区分 Stress、Hope、Despair？
* [ ] 是否考虑角色个性？
* [ ] 是否保留恢复可能？
* [ ] 是否让压力影响但不决定行为？
* [ ] 是否记录长期心理变化？

---

# Designer Notes

弹丸论破真正危险的地方。

不是死亡本身。

而是：

人在死亡压力下。

逐渐成为自己曾经无法想象的人。

心理压力系统负责模拟：

这个过程。

角色不是因为黑白熊一句话改变。

而是在一次次：

恐惧。

希望。

失望。

选择。

中慢慢变化。

---

# 下一节

## Section 6.3 — 杀意生成系统（Murder Intent Generation System）

下一节将定义：

* 杀意如何形成；
* 为什么有人最终选择杀人；
* 为什么有人拥有动机却不会行动；
* 凶手候选如何动态产生；
* 如何保证没有预定凶手。

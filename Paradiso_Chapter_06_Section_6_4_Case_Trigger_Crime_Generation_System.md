# Chapter 06 — 黑白熊系统与动机生成系统（Monokuma & Motivation Engine）

## Section 6.4 — 案件触发与犯罪生成系统（Case Trigger & Crime Generation System）

**依赖章节（Depends On）**

* Section 6.1 — 动机生成算法（Motivation Generation Algorithm）
* Section 6.2 — 心理压力系统（Psychological Pressure System）
* Section 6.3 — 杀意生成系统（Murder Intent Generation System）
* Chapter 05 — 社交模拟系统（Social Simulation Engine）
* Chapter 07 — 调查与学级裁判系统（Investigation & Class Trial System）

**影响状态（Modified State）**

* World.CaseState
* Character.Status
* Character.Relationship
* World.EvidencePool
* World.EventQueue
* InvestigationState

---

# 目的（Purpose）

案件触发与犯罪生成系统用于模拟：

> 当一个角色最终选择犯罪时，一个完整案件如何自然产生。

核心原则：

案件不是：

"章节开始 → GM安排死亡 → 玩家调查"

而应该是：

```text id="g6b0xi"
长期模拟

↓

心理变化

↓

犯罪选择

↓

案件发生

↓

调查与裁判
```

---

# CASE-001 案件生成原则

AI必须遵守：

## 案件必须有原因。

每个案件需要回答：

* 为什么现在发生？
* 为什么是这个人？
* 为什么选择这个方法？
* 为什么其他方案失败？

---

## 案件必须可推理。

所有案件：

必须存在：

* 动机；
* 手段；
* 时间线；
* 物证；
* 矛盾点。

---

## 案件不能为了震撼而违反逻辑。

---

# CASE-002 案件触发检查

每个时间循环。

后台检查：

```text id="0k3j8k"
Murder Intent

+

Opportunity

+

Motivation State

+

Psychological Condition

+

Random Factor
```

---

只有满足条件：

案件才进入生成阶段。

---

# CASE-003 犯罪生成流程

案件生成：

```text id="k2s8n5"
1. 确认犯罪者候选

↓

2. 确认目标对象

↓

3. 分析犯罪原因

↓

4. 生成犯罪计划

↓

5. 生成时间线

↓

6. 生成证据

↓

7. 检查逻辑漏洞

↓

8. 案件正式发生
```

---

# CASE-004 凶手选择

凶手不是：

最高杀意者。

---

选择依据：

```text id="w8e0bq"
Intent

+

Opportunity

+

Personality

+

Goal

+

Risk Calculation

+

Random
```

---

例如：

角色A：

杀意90。

但是：

没有机会。

---

角色B：

杀意65。

拥有：

机会。

最终B更可能犯罪。

---

# CASE-005 被害者选择

被害者不是随机选择。

影响因素：

---

## 关系因素

例如：

冲突对象。

---

## 动机因素

例如：

掌握秘密的人。

---

## 机会因素

例如：

容易接近。

---

## 剧情因素

例如：

死亡会改变群体结构。

---

但：

禁止为了剧情强行选择。

---

# CASE-006 犯罪计划生成

犯罪计划必须考虑：

## 犯罪者能力

例如：

工匠：

可能利用工具。

---

## 场所条件

例如：

庄园设施。

---

## 时间安排

例如：

夜晚。

---

## 目标行为

例如：

目标是否会独处。

---

---

# CASE-007 犯罪时间线

每个案件必须生成完整时间线：

格式：

```text id="3h9g1t"
事件前：

角色行动

↓

准备阶段：

犯罪者行为

↓

执行阶段：

犯罪发生

↓

事后阶段：

隐藏行为

↓

发现阶段：

尸体发现
```

---

时间线必须：

内部闭合。

---

# CASE-008 证据生成原则

证据分为：

## 直接证据

例如：

物品。

痕迹。

记录。

---

## 间接证据

例如：

行为异常。

时间矛盾。

关系变化。

---

## 误导证据

例如：

看似指向错误方向。

---

误导证据必须：

最终可以解释。

---

# CASE-009 犯罪者失误

案件必须包含：

犯罪者弱点。

例如：

* 性格缺陷；
* 情绪失控；
* 知识不足；
* 意外变量。

---

完美犯罪禁止。

---

# CASE-010 案件复杂度

案件复杂度根据章节调整。

---

## 第一章

特点：

* 基础逻辑；
* 角色关系介绍；
* 玩家熟悉系统。

---

## 中期章节

特点：

* 多重线索；
* 更复杂关系；
* 心理误导。

---

## 后期章节

特点：

* 世界秘密；
* 角色隐藏身份；
* 高级推理。

---

# CASE-011 犯罪后状态变化

案件发生后：

立即更新：

```text id="0fy8k3"
Survivor Psychology

+

Relationship Change

+

Group Collapse

+

Suspicion

+

Hope/Despair
```

---

死亡不是事件结束。

而是新阶段开始。

---

# CASE-012 黑白熊处理

案件发生后：

黑白熊：

* 发现尸体；
* 宣布调查；
* 开启规则流程。

---

黑白熊不会：

提前泄露凶手。

---

# CASE-013 案件取消条件

案件可能不会发生。

例如：

角色：

* 放弃计划；
* 被别人影响；
* 找到替代方案。

---

AI必须允许：

"差一点发生的案件"

存在。

---

# AI执行检查（AI Compliance Checklist）

生成案件时：

* [ ] 是否由角色状态产生？
* [ ] 是否没有预设凶手？
* [ ] 是否有完整时间线？
* [ ] 是否所有证据可解释？
* [ ] 是否存在合理失误？
* [ ] 是否符合章节难度？
* [ ] 是否保留推理空间？

---

# Designer Notes

案件是 Paradiso 的高潮。

但案件不是游戏本身。

真正重要的是：

案件发生之前。

玩家已经认识这些人。

已经理解他们。

已经见过他们的选择。

所以当案件发生时。

玩家面对的不是：

"一个谜题。"

而是：

"一个曾经相信过的人，为什么走到了这一步。"

---

# 下一节

## Section 6.5 — 案件后果与社会崩溃系统（Post-Case Consequence System）

下一节将定义：

* 死亡后的群体变化；
* 信任崩塌；
* 生还者心理变化；
* 如何让每个案件永久影响世界。

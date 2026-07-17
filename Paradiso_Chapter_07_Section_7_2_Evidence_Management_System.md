# Chapter 07 — 调查与学级裁判系统（Investigation & Class Trial Engine）

## Section 7.2 — 证据管理系统（Evidence Management System）

**依赖章节（Depends On）**

* Section 7.1 — 调查阶段系统（Investigation Phase System）
* Chapter 04 — 角色模拟系统（Character Simulation Engine）
* Chapter 05 — 社交模拟系统（Social Simulation Engine）

**影响状态（Modified State）**

* EvidenceDatabase
* Character.Knowledge
* Character.Theory
* TrialState
* CaseTimeline

---

# 目的（Purpose）

证据管理系统用于定义：

> 案件中的信息如何被发现、保存、解释，并最终用于推理。

证据不是单纯的：

"找到物品。"

而是：

```text id="r4m8h2"
Information

↓

Interpretation

↓

Connection

↓

Truth
```

---

# EVIDENCE-001 证据核心原则

所有案件必须拥有：

## 完整证据链

即：

```text id="v8k4sd"
事件发生

↓

留下痕迹

↓

被发现

↓

被解释

↓

证明真相
```

---

禁止：

没有证据支持的推理。

---

禁止：

依靠作者提示。

---

# EVIDENCE-002 证据数据库结构

每个案件维护：

Evidence Database。

格式：

```text id="q5t0hz"
Evidence ID:

Name:

Category:

Discovery Location:

Found By:

Time Found:

Reliability:

Importance:

Known By:

Possible Interpretation:
```

---

示例：

```text id="a7k3m9"
Evidence ID:
E-001

Name:
Broken Watch

Category:
Physical Evidence

Location:
Library

Found By:
仮名楽

Reliability:
High

Importance:
Medium
```

---

# EVIDENCE-003 证据分类

证据分为：

---

# 1. Physical Evidence（物理证据）

现实存在。

例如：

* 物品；
* 痕迹；
* 文件；
* 工具。

---

特点：

可靠性通常较高。

---

# 2. Testimony（证词）

角色提供的信息。

例如：

* 看到了什么；
* 听到了什么；
* 做过什么。

---

特点：

可能：

真实。

错误。

隐藏。

---

# 3. Circumstantial Evidence（间接证据）

通过推理产生价值。

例如：

* 行为异常；
* 时间冲突；
* 关系变化。

---

# 4. Psychological Evidence（心理证据）

涉及：

* 情绪；
* 动机；
* 反应。

---

注意：

心理证据不能单独定罪。

---

# EVIDENCE-004 证据属性

每个证据拥有：

---

## Reliability（可靠性）

表示：

该信息是否准确。

范围：

0-100。

---

例如：

摄像记录：

95。

---

传闻：

30。

---

## Importance（重要性）

表示：

对于案件的重要程度。

---

## Visibility（可见性）

表示：

发现难度。

---

## Interpretation（解释）

表示：

可能被如何理解。

---

# EVIDENCE-005 证据不是答案

重要原则：

> 证据本身不会自动告诉玩家真相。

---

例如：

发现：

湿掉的地板。

---

可能解释：

* 有人清洁；
* 有人漏水；
* 有人伪造现场。

---

需要：

结合其他信息。

---

# EVIDENCE-006 多重解释系统

同一个证据。

允许：

多个理论。

---

例如：

证据：

"一把带血的刀。"

---

可能解释：

A：

凶器。

---

B：

被放置误导。

---

C：

其他事件留下。

---

直到更多证据出现。

---

# EVIDENCE-007 证据连接系统

证据之间存在：

Connection。

---

例如：

```text id="1z4x8p"
Broken Clock

+

Body Time

=

Time Contradiction
```

---

连接产生：

新的推理可能。

---

# EVIDENCE-008 证据发现顺序

案件必须考虑：

玩家发现顺序。

---

不能：

关键证据必须第一个找到。

---

允许：

不同调查路线。

---

但是：

最终必须能够闭环。

---

# EVIDENCE-009 证据隐藏机制

部分证据：

具有隐藏状态。

例如：

```text id="0n3k9a"
Visible:

普通观察无法发现。

Hidden:

需要特殊条件。
```

---

触发条件：

* 能力成功；
* 特定角色；
* 新信息出现；
* 再次调查。

---

# EVIDENCE-010 证据误导机制

优秀案件需要：

合理误导。

---

误导证据必须：

满足：

```text id="7c9p4d"
Looks Suspicious

+

Has Alternative Explanation
```

---

例如：

某人的指纹。

但：

他曾经帮助受害者。

---

# EVIDENCE-011 角色证据理解差异

不同角色：

对同一证据理解不同。

---

例如：

一张复杂机械图。

---

小夜织姬：

看到结构问题。

---

白峰真冬：

看到制作痕迹。

---

神永追记：

看到行为目的。

---

# EVIDENCE-012 证据公开规则

调查阶段：

证据不会自动共享。

---

角色可能：

* 分享；
* 隐瞒；
* 怀疑；
* 错误理解。

---

共享概率取决于：

```text id="k5j9x1"
Trust

+

Personality

+

Goal
```

---

# EVIDENCE-013 证据丢失与破坏

可能发生：

* 证据损坏；
* 错误保存；
* 被隐藏。

---

但：

核心证据不能因为随机事件消失。

---

除非：

存在合理替代路径。

---

# EVIDENCE-014 证据与学级裁判

裁判阶段：

证据用于：

* 反驳错误观点；
* 支持推理；
* 建立时间线。

---

不是：

直接点击正确答案。

---

# AI执行检查（AI Compliance Checklist）

管理证据时：

* [ ] 是否建立完整证据链？
* [ ] 是否区分证据和解释？
* [ ] 是否允许误导？
* [ ] 是否保证最终可推理？
* [ ] 是否考虑角色理解差异？
* [ ] 是否避免隐藏所有关键线索？
* [ ] 是否维护唯一真相？

---

# Designer Notes

证据系统的目标：

不是制造困难。

而是制造：

"理解过程。"

玩家真正享受的不是：

知道答案。

而是：

从碎片中拼出答案。

每一个证据。

都是故事留下的痕迹。

---

# 下一节

## Section 7.3 — 学级裁判流程系统（Class Trial Flow System）

下一节将定义：

* 裁判开始流程；
* 讨论阶段；
* 反驳系统；
* 矛盾发现；
* NPC发言逻辑；
* 投票机制。

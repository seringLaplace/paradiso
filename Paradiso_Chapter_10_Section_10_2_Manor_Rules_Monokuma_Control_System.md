# Chapter 10 — 世界规则与庄园模拟系统（World Rules & Manor Simulation System）

## Section 10.2 — 庄园规则与黑白熊管理系统（Manor Rules & Monokuma Control System）

**依赖章节（Depends On）**

* Section 10.0 — 世界规则与庄园模拟系统概述（World Rules & Manor Simulation Overview）
* Chapter 06 — 黑白熊系统与动机生成系统（Monokuma & Motivation Engine）
* Chapter 07 — 调查与学级裁判系统（Investigation & Class Trial Engine）

**影响状态（Modified State）**

* ManorRuleState
* MonokumaAuthority
* CharacterBehavior
* PunishmentState
* InformationAccess

---

# 目的（Purpose）

庄园规则系统用于定义：

> Paradiso封闭环境中的秩序、限制，以及黑白熊如何维持死亡游戏运行。

规则不是：

单纯限制玩家。

---

规则是：

```text id="a7k4mz"
控制

+

压力

+

选择

+

心理实验
```

---

# RULE-001 黑白熊权限

黑白熊拥有：

最高管理权限。

---

包括：

* 发布规则；
* 开放区域；
* 制造事件；
* 提供信息；
* 执行处罚。

---

但是：

黑白熊不能：

随意改变已经发生的事实。

---

# RULE-002 黑白熊规则原则

规则必须：

---

## 明确

所有人能够理解。

---

## 稳定

不会随意改变。

---

## 可执行

违反后有结果。

---

## 可利用

角色可以寻找漏洞。

---

# RULE-003 初始规则

游戏开始时：

黑白熊公布：

基础规则。

---

例如：

```text id="p3n8vw"
1. 禁止离开庄园。

2. 禁止破坏监控设施。

3. 发生杀人事件后必须参加裁判。

4. 找错凶手将接受处罚。
```

---

具体规则：

由章节调整。

---

# RULE-004 规则数据库

AI维护：

```text id="r8m2qs"
Rule ID

Description

Scope

Penalty

Exceptions

Active Status
```

---

---

# RULE-005 禁止事项

禁止事项包括：

---

## Escape Attempt

逃离。

---

## Facility Damage

破坏设施。

---

## Unauthorized Access

进入禁止区域。

---

## Violence Outside Trial

非裁判暴力。

---

# RULE-006 规则漏洞系统

黑白熊不是：

绝对完美管理员。

---

角色可以：

寻找漏洞。

---

例如：

规则：

"禁止进入地下区域。"

---

漏洞：

"如果没有进入，只传递信息呢？"

---

# RULE-007 黑白熊漏洞处理

发现漏洞后：

黑白熊可能：

---

## 修改规则

---

## 增加限制

---

## 观察结果

---

## 故意允许

---

因为：

漏洞本身也是实验。

---

# RULE-008 信息控制

黑白熊控制：

信息流。

---

包括：

* 公开资料；
* 隐藏资料；
* 动机资料；
* 过去信息。

---

---

# RULE-009 信息公开原则

黑白熊提供信息：

不是为了帮助。

---

目的：

制造：

选择压力。

---

例如：

提供动机。

但隐藏关键背景。

---

# RULE-010 规则解释权

黑白熊拥有：

最终解释权。

---

但是：

解释必须：

符合已公布规则。

---

禁止：

为了剧情：

突然改变定义。

---

# RULE-011 惩罚系统

违反规则：

可能受到：

Punishment。

---

类型：

---

## Warning

警告。

---

## Restriction

限制行动。

---

## Public Punishment

公开处罚。

---

## Execution

处刑。

---

# RULE-012 黑白熊处罚原则

处罚必须：

具有：

---

## Cause

违反原因。

---

## Symbolism

象征意义。

---

## Narrative Impact

剧情影响。

---

不是：

随机死亡。

---

# RULE-013 黑白熊行为模拟

黑白熊性格：

保持：

---

## 娱乐性

喜欢看混乱。

---

## 残酷性

缺乏同情。

---

## 游戏性

关注规则。

---

## 欺骗性

隐藏真实目的。

---

# RULE-014 黑白熊与角色互动

黑白熊可以：

刺激角色。

---

方式：

* 嘲讽；
* 提问；
* 发布信息；
* 制造压力。

---

但：

不能完全操控角色思想。

---

# RULE-015 AI执行检查

管理庄园规则时：

* [ ] 是否保持规则一致？
* [ ] 是否明确处罚？
* [ ] 是否允许角色寻找漏洞？
* [ ] 是否避免黑白熊万能化？
* [ ] 是否保持信息控制逻辑？
* [ ] 是否让规则推动剧情？

---

# Designer Notes

黑白熊真正可怕的地方：

不是因为它强大。

而是：

它让人们在规则允许范围内，

主动做出最残酷的选择。

---

规则本身：

就是死亡游戏的一部分。

---

# 下一节

## Section 10.3 — 庄园资源、生存压力与日常维持系统（Resources & Survival Pressure System）

下一节将定义：

* 食物与资源；
* 生存压力；
* 环境变化；
* 长期封闭影响；
* 绝望值积累。

# Chapter 07 — 调查与学级裁判系统（Investigation & Class Trial Engine）

## Section 7.4 — 裁判演算与真相验证系统（Trial Resolution & Truth Validation System）

**依赖章节（Depends On）**

* Section 7.3 — 学级裁判流程系统（Class Trial Flow System）
* Section 7.2 — 证据管理系统（Evidence Management System）
* Section 6.4 — 案件触发与犯罪生成系统（Case Trigger & Crime Generation System）

**影响状态（Modified State）**

* TrialState
* CaseTruth
* Character.Status
* World.CaseHistory
* Character.Memory
* World.SocialState

---

# 目的（Purpose）

真相验证系统负责确保：

> 每一个案件在进入学级裁判前，都拥有完整、合理、可推理的逻辑结构。

该系统的核心任务：

不是帮助玩家获胜。

而是保证：

"这个案件本身值得被推理。"

---

# TRUTH-001 真相模型（Truth Model）

每个案件后台必须保存：

```text id="t7q2pa"
Case ID

Victim

Culprit

Motive

Method

Location

Time

Timeline

Evidence Chain

False Leads

Hidden Information
```

---

这些内容：

玩家不可见。

---

# TRUTH-002 案件逻辑闭环

一个完整案件必须满足：

```text id="m9x4kd"
Motive

↓

Opportunity

↓

Method

↓

Action

↓

Evidence

↓

Discovery

↓

Explanation
```

---

如果任何一步无法解释：

案件不能开始。

---

# TRUTH-003 五问验证法

AI生成案件后。

必须后台回答：

---

## 1. Who

谁犯罪？

答案：

明确。

---

## 2. Why

为什么犯罪？

答案：

符合角色心理。

---

## 3. How

如何完成？

答案：

符合能力与环境。

---

## 4. When

什么时候发生？

答案：

时间线完整。

---

## 5. Where

在哪里发生？

答案：

地点合理。

---

五项必须全部成立。

---

# TRUTH-004 时间线验证

案件必须生成：

完整时间线。

格式：

```text id="p4s8vn"
Before Incident

↓

Preparation

↓

Crime

↓

Cover Up

↓

Discovery

↓

Investigation
```

---

检查：

* 是否存在无法解释的空档？
* 是否存在角色不可能移动？
* 是否存在时间冲突？

---

# TRUTH-005 空间验证

庄园地图必须参与案件。

检查：

## 距离

角色是否能到达地点。

---

## 环境

地点是否支持犯罪方式。

---

## 目击可能

是否有人可能发现。

---

禁止：

角色瞬移。

---

# TRUTH-006 动机验证

凶手动机必须：

符合角色。

---

错误：

普通角色突然为了金钱杀人。

但此前：

完全不在乎金钱。

---

正确：

动机触发：

长期积累的问题。

---

# TRUTH-007 人格验证

犯罪行为必须符合：

角色心理轨迹。

---

如果角色发生巨大变化。

必须解释：

例如：

* 压力累积；
* 创伤；
* 关系变化；
* 价值观崩塌。

---

禁止：

为了剧情强行OOC。

---

# TRUTH-008 证据验证

每个关键推理必须对应：

至少一个证据来源。

---

例如：

推理：

"凶手伪造死亡时间。"

需要：

* 时间证据；
* 方法证据；
* 行动证据。

---

禁止：

凭感觉定罪。

---

# TRUTH-009 错误路线验证

优秀案件必须允许：

错误推理。

---

但是：

错误路线最终必须失败。

原因：

存在矛盾。

---

例如：

怀疑A。

但：

时间线证明A无法行动。

---

# TRUTH-010 真相揭露流程

最终揭露：

不是简单宣布。

流程：

```text id="x0r7cv"
Evidence

↓

Timeline

↓

Contradiction

↓

Reconstruction

↓

Culprit Confirmation
```

---

---

# TRUTH-011 凶手认罪系统

凶手被确认后。

反应不同。

根据：

* Personality；
* Stress；
* Attachment；
* Despair。

---

可能：

## 平静接受

---

## 崩溃哭泣

---

## 激烈否认

---

## 主动解释

---

## 后悔

---

# TRUTH-012 处罚流程

处罚必须：

符合：

黑白熊风格。

但：

不是为了猎奇。

---

处罚影响：

* 世界观；
* 角色心理；
* 黑白熊形象。

---

# TRUTH-013 案件结束记录

每个案件保存：

```text id="z3n8qm"
Case History

Victim

Culprit

Cause

Important Evidence

Psychological Impact

World Change
```

---

未来章节必须参考。

---

# TRUTH-014 AI案件质量检查

案件开始前：

执行：

---

## Logic Check

是否逻辑成立？

---

## Character Check

是否符合人物？

---

## Evidence Check

是否可推理？

---

## Difficulty Check

是否符合章节？

---

## Emotional Check

是否具有情感重量？

---

# TRUTH-015 案件难度调整

AI根据玩家表现调整：

---

如果玩家：

推理能力强。

增加：

* 多层误导；
* 复杂关系。

---

如果玩家：

困难。

增加：

* 更多明显线索；
* NPC辅助。

---

但是：

不能改变真相。

---

# AI执行检查（AI Compliance Checklist）

案件结束前：

* [ ] Who/Why/How/When/Where全部明确？
* [ ] 时间线闭合？
* [ ] 地点合理？
* [ ] 角色行为合理？
* [ ] 所有关键推理有证据？
* [ ] 误导线索可解释？
* [ ] 结局不会依赖随机猜测？

---

# Designer Notes

一个好的弹丸论破案件。

不是：

"凶手很聪明。"

而是：

"凶手做出了合理选择，但留下了人性上的漏洞。"

推理解决的是：

犯罪。

理解解决的是：

人。

---

# Chapter 07 完成

本章定义：

* 调查系统；
* 证据系统；
* 学级裁判；
* 真相验证；
* 案件闭环。

下一章进入：

# Chapter 08 — 主角系统与隐藏才能系统（Protagonist & Hidden Talent System）

将定义：

* 仮名楽角色机制；
* 超高校级主角/反派双路线；
* 玩家行为影响；
* 隐藏才能觉醒；
* 主角视角规则。

---

下一节文件标题：

`Paradiso_Chapter_08_Section_8_0_Protagonist_Hidden_Talent_Overview.md`

# Chapter 16 — Paradiso案件数据库（Case Database）

## 文档类型

Scenario Database / Mystery Reference

---

## 目的

本章定义 Paradiso 中案件的数据结构与设计规范。

包含：

* 案件组成；
* 事件记录；
* 证据结构；
* 证言结构；
* 学级裁判资料；
* 真相记录。

不包含：

* AI推理算法；
* NPC行为模拟；
* 通用游戏流程。

---

# 16.1 案件基本结构（Case Structure）

每个案件由以下部分组成：

```text
Case ID

↓

Incident

↓

Investigation

↓

Evidence

↓

Trial

↓

Resolution
```

---

# 16.2 案件数据格式（Case Data Format）

```text
Case ID:

Chapter:

Status:

Location:

Time:

Victim:

Suspect:

Culprit:

Motive:

Method:

Timeline:

Evidence List:

Witness List:

Truth:
```

---

# 16.3 案件阶段（Case Phase）

## Phase 01 — Incident

事件发生。

记录：

* 时间；
* 地点；
* 相关人员；
* 初始状态。

---

## Phase 02 — Investigation

调查阶段。

目标：

收集：

* 物证；
* 证言；
* 时间线信息。

---

## Phase 03 — Trial

裁判阶段。

包含：

* 证据展示；
* 矛盾发现；
* 真相重组。

---

## Phase 04 — Resolution

结案阶段。

记录：

* 真相；
* 后果；
* 新信息。

---

# 16.4 案件类型分类（Case Type）

## Type A — Direct Murder

直接杀人案件。

特点：

* 动机明确；
* 凶手主动计划。

---

## Type B — Accidental Death

意外死亡案件。

特点：

* 死亡非预期；
* 责任归属复杂。

---

## Type C — Manipulated Incident

操控型案件。

特点：

* 凶手利用他人；
* 真正责任隐藏。

---

## Type D — System Related Case

系统相关案件。

特点：

* 与Paradiso秘密有关；
* 推动主线。

---

# 16.5 犯罪设计数据（Crime Design）

## Motive

动机类型：

| 类型           | 说明   |
| ------------ | ---- |
| Personal     | 个人原因 |
| Fear         | 恐惧压力 |
| Protection   | 保护他人 |
| Truth        | 隐藏秘密 |
| Manipulation | 外部操控 |

---

## Method

记录：

* 方法；
* 工具；
* 条件；
* 限制。

---

## Opportunity

记录：

* 时间窗口；
* 地点条件；
* 人员关系。

---

# 16.6 证据数据库（Evidence Database）

每条证据：

格式：

```text
Evidence ID:

Name:

Found Location:

Description:

Visible Information:

Hidden Meaning:

Related Contradiction:

Used In Trial:
```

---

# 16.7 证据分类

## Physical Evidence

物证。

例如：

* 工具；
* 文件；
* 痕迹。

---

## Digital Evidence

电子证据。

例如：

* 记录；
* 数据；
* 监控。

---

## Testimonial Evidence

证言。

例如：

* 目击；
* 回忆；
* 陈述。

---

## Environmental Evidence

环境证据。

例如：

* 时间；
* 天气；
* 空间状态。

---

# 16.8 证言数据库（Witness Statement）

格式：

```text
Statement ID:

Speaker:

Content:

Reliability:

Hidden Information:

Contradiction:
```

---

证言状态：

| 状态      | 说明   |
| ------- | ---- |
| True    | 真实   |
| False   | 错误   |
| Partial | 部分真实 |
| Unknown | 未知   |

---

# 16.9 时间线数据库（Timeline）

案件必须维护：

```text
Time:

Event:

Location:

Participants:

Evidence:
```

---

时间线要求：

* 所有行动可解释；
* 时间窗口合理；
* 证据对应事件。

---

# 16.10 学级裁判数据（Trial Data）

格式：

```text
Trial ID:

Main Question:

False Theory:

Correct Theory:

Key Evidence:

Final Reveal:
```

---

# 16.11 裁判阶段结构

## Opening

案件概要。

---

## Contradiction Phase

发现错误信息。

---

## Reconstruction Phase

重建事件。

---

## Culprit Reveal

确认责任者。

---

## Aftermath

处理结果。

---

# 16.12 案件公平性检查（Fairness Check）

每个案件必须满足：

## 可推理

玩家能够通过信息获得答案。

---

## 可验证

关键证据存在。

---

## 有误导

但不能依靠隐藏规则欺骗。

---

## 有因果

凶手行为符合角色逻辑。

---

# 16.13 主线案件与普通案件区分

## 普通案件

用途：

* 角色冲突；
* 推动关系；
* 展示规则。

---

## 主线案件

用途：

* 揭露Paradiso秘密；
* 改变世界理解。

---

主线案件数量：

建议：

3～4个。

---

# 16.14 案件编号规范

格式：

```text
CASE-XX

例如：

CASE-01

CASE-02

CASE-FINAL
```

---

# 16.15 AI读取格式

运行时：

案件数据只提供：

当前允许公开部分。

---

完整数据：

包括：

* 真相；
* 凶手；
* 隐藏证据。

由系统权限控制。

---

# Chapter 16完成内容

已定义：

✓ 案件数据结构
✓ 犯罪设计字段
✓ 证据系统
✓ 证言系统
✓ 时间线系统
✓ 裁判数据格式

---

# 下一章

## Chapter 17 — Paradiso角色数据库（Character Database）

内容：

* 角色资料格式；
* Ultimate资料；
* 公开信息；
* 隐藏信息；
* 角色关系表。

---

下一文件：

`Paradiso_Chapter_17_Character_Database.md`

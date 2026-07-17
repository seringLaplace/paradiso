# Chapter 06 — 黑白熊系统与动机生成系统（Monokuma & Motivation Engine）

## Section 6.0 — 黑白熊系统概述（Monokuma System Overview）

**依赖章节（Depends On）**

* Chapter 03 — 时间系统（Time System）
* Chapter 04 — 角色模拟系统（Character Simulation Engine）
* Chapter 05 — 社交模拟系统（Social Simulation Engine）

**影响状态（Modified State）**

* World.MotivationState
* Character.Stress
* Character.Desperation
* Character.Intent
* Character.Goal
* World.EventQueue

---

# 目的（Purpose）

黑白熊系统负责模拟：

> 一个外部压力源如何逐渐改变封闭环境中的人类行为。

在《弹丸论破》中。

黑白熊并不是简单的：

"发布任务的人。"

而是：

> 一个观察者、操纵者，以及心理实验的推动者。

---

# MONO-001 黑白熊定位

黑白熊具有以下功能：

## 1. 规则制定者（Rule Authority）

负责：

* 宣布共同生活规则；
* 发布禁止事项；
* 解释裁判规则。

---

## 2. 动机提供者（Motivation Provider）

负责：

* 制造心理压力；
* 提供杀人诱因；
* 改变角色行为概率。

---

## 3. 观察者（Observer）

黑白熊关注：

* 希望；
* 绝望；
* 冲突；
* 人际变化。

---

## 4. 娱乐制造者（Entertainment Engine）

黑白熊偏好：

* 戏剧性；
* 意外；
* 情绪波动。

---

# MONO-002 黑白熊行为原则

黑白熊不是随机恶作剧。

其行为必须符合：

```text id="3x6y4v"
Increase Pressure

+

Create Choice

+

Observe Reaction
```

---

例如：

错误：

> 黑白熊突然要求所有人互相攻击。

原因不足。

---

正确：

> 黑白熊观察到大家已经形成稳定联盟，于是提供一个足以动摇信任的选择。

---

# MONO-003 黑白熊信息权限

黑白熊拥有：

## 世界信息

知道：

* 庄园结构；
* 系统规则；
* 隐藏区域；
* 动机机制。

---

## 角色秘密

可能知道：

* 真实身份；
* 隐藏过去；
* 潜在弱点。

---

## 未来行为

不知道。

黑白熊不能预知：

* 谁会杀人；
* 谁会死亡；
* 最终结局。

---

# MONO-004 黑白熊出现频率

禁止：

每天出现。

黑白熊出现应具有：

目的。

---

出现时机：

## 规则需要

例如：

宣布新区域开放。

---

## 动机发布

例如：

第一章动机。

---

## 剧情压力不足

例如：

所有人关系过于稳定。

---

## 观察实验结果

例如：

测试某角色心理极限。

---

# MONO-005 动机系统概念

动机（Motivation）定义：

> 能够显著改变角色选择倾向的外部刺激。

动机不是命令。

角色可以：

接受。

拒绝。

隐藏。

转化。

---

# MONO-006 动机影响模型

动机影响：

```text id="4x2b3h"
External Motivation

↓

Psychology Change

↓

Goal Change

↓

Decision Change

↓

Possible Action
```

---

# MONO-007 动机类型

## 信息型动机（Information Motivation）

提供：

* 过去记忆；
* 隐藏秘密；
* 世界真相。

影响：

好奇心。

---

## 情感型动机（Emotional Motivation）

涉及：

* 家人；
* 朋友；
* 重要关系。

影响：

情绪。

---

## 生存型动机（Survival Motivation）

涉及：

* 资源；
* 安全；
* 时间限制。

影响：

压力。

---

## 竞争型动机（Competition Motivation）

制造：

* 排名；
* 比较；
* 利益冲突。

影响：

关系。

---

## 个人弱点型动机（Personal Weakness Motivation）

针对：

角色恐惧。

角色执念。

隐藏欲望。

---

# MONO-008 动机强度

每个动机拥有：

```text id="y9x3d0"
Intensity 0-100
```

参考：

| 强度     | 效果       |
| ------ | -------- |
| 0-20   | 轻微影响     |
| 21-50  | 明显压力     |
| 51-80  | 严重动摇     |
| 81-100 | 可能改变人生选择 |

---

# MONO-009 动机不会保证杀人

核心规则：

> 动机 ≠ 杀人。

动机只是提高：

Intent。

---

是否发生杀人。

仍需经过：

```text id="9q6c8v"
Motivation

+

Personality

+

Opportunity

+

Stress

+

Relationship

+

Random Factor
```

---

# MONO-010 动机与角色差异

同一个动机。

不同角色反应不同。

例如：

"公开所有人的秘密。"

可能：

## 角色A

恐惧。

试图保护秘密。

---

## 角色B

无所谓。

---

## 角色C

主动利用信息。

---

AI 必须根据角色模拟。

不能统一处理。

---

# MONO-011 动机结束条件

动机不会永久存在。

可能：

* 被解决；
* 被抵抗；
* 被替代；
* 被新的动机覆盖。

---

# AI执行检查（AI Compliance Checklist）

生成黑白熊行为时：

* [ ] 是否有实验目的？
* [ ] 是否符合黑白熊风格？
* [ ] 是否避免直接控制角色？
* [ ] 是否允许角色拒绝动机？
* [ ] 是否根据人物差异产生不同反应？
* [ ] 是否保持凶手未知？

---

# Designer Notes

黑白熊系统的核心不是制造死亡。

而是制造选择。

真正的弹丸论破体验来自：

> 当一个人被逼到极限时，他会选择成为怎样的人。

黑白熊提供压力。

角色决定答案。

---

# 下一节

## Section 6.1 — 动机生成算法（Motivation Generation Algorithm）

下一节将定义：

* 黑白熊如何决定发布什么动机；
* 如何根据16人的心理状态选择刺激；
* 如何避免重复动机；
* 如何动态生成第一章、第二章之后的案件压力。

# Chapter 06 — 黑白熊系统与动机生成系统（Monokuma & Motivation Engine）

## Section 6.5 — 案件后果与社会崩溃系统（Post-Case Consequence System）

**依赖章节（Depends On）**

* Section 6.3 — 杀意生成系统（Murder Intent Generation System）
* Section 6.4 — 案件触发与犯罪生成系统（Case Trigger & Crime Generation System）
* Chapter 05 — 社交模拟系统（Social Simulation Engine）
* Chapter 04 — 角色模拟系统（Character Simulation Engine）

**影响状态（Modified State）**

* Character.Psychology
* Character.Relationship
* Character.Trust
* Character.Desire
* Character.GroupMembership
* World.SocialStability
* World.FutureEventProbability

---

# 目的（Purpose）

案件后果系统用于模拟：

> 一次死亡事件如何永久改变剩余角色以及整个庄园社会。

在 Paradiso 中。

案件结束不是：

"裁判结束 → 恢复日常。"

而是：

```text id="r4gq0n"
死亡

↓

真相公开

↓

心理冲击

↓

关系重组

↓

社会结构变化

↓

新的未来可能性
```

---

# CONSEQUENCE-001 核心原则

每一个案件必须留下痕迹。

包括：

* 情感痕迹；
* 信任变化；
* 群体变化；
* 心理变化；
* 行为变化。

---

禁止：

案件结束后。

所有角色恢复原状。

---

# CONSEQUENCE-002 死亡影响范围

死亡影响：

不只是亲近的人。

影响范围：

---

## 第一层：亲密关系

包括：

* 好友；
* 伙伴；
* 依赖对象。

影响最大。

---

## 第二层：合作关系

包括：

* 调查伙伴；
* 同组成员。

---

## 第三层：普通认识者

影响较低。

---

## 第四层：整个群体

例如：

全员失去安全感。

---

# CONSEQUENCE-003 悲伤系统（Grief System）

角色面对死亡时：

不应统一反应。

---

可能：

## 悲伤型

表现：

* 沉默；
* 回忆；
* 情绪低落。

---

## 愤怒型

表现：

* 寻找责任；
* 指责他人。

---

## 否认型

表现：

* 不接受事实；
* 逃避现实。

---

## 理性处理型

表现：

* 分析案件；
* 维持行动。

---

## 隐藏反应型

表现：

表面平静。

内部变化巨大。

---

# CONSEQUENCE-004 信任变化

案件后：

所有幸存者重新评估关系。

---

例如：

凶手被发现。

角色可能：

对真相接受：

Trust变化。

---

对调查者：

可能增加信任。

---

对隐藏信息的人：

可能降低信任。

---

# CONSEQUENCE-005 群体重组

案件可能导致：

## 群体强化

例如：

共同经历死亡。

让成员更加团结。

---

## 群体崩溃

例如：

怀疑内部成员。

导致联盟瓦解。

---

## 新群体形成

例如：

原本互不交流的人开始合作。

---

# CONSEQUENCE-006 幸存者罪恶感

部分角色可能产生：

Survivor Guilt。

表现：

* "为什么不是我？"
* "如果我早点发现……"

---

影响：

* Hope下降；
* Stress上升；
* 行为改变。

---

# CONSEQUENCE-007 对凶手的记忆

即使裁判结束。

角色不会简单遗忘。

他们可能：

* 恐惧；
* 愤怒；
* 同情；
* 厌恶；
* 理解。

---

不同角色态度不同。

---

例如：

火守朱音：

可能：

无法接受杀人。

---

神永追记：

可能：

分析凶手心理。

---

彼方凪纱：

可能：

思考"是什么让人走到这一步"。

---

# CONSEQUENCE-008 庄园气氛变化

每次案件后：

更新：

## Social Atmosphere

范围：

0-100。

---

影响：

* 对话风格；
* 行动力；
* 信任速度；
* 冲突概率。

---

例如：

第一次死亡后：

所有人更谨慎。

---

连续死亡后：

部分角色可能：

接近崩溃。

---

# CONSEQUENCE-009 黑白熊影响

黑白熊观察：

案件后的反应。

关注：

* 是否产生绝望；
* 是否产生反抗；
* 是否形成新的希望。

---

如果所有人团结：

黑白熊可能提高压力。

---

如果所有人崩溃：

黑白熊可能继续观察。

---

# CONSEQUENCE-010 角色成长

案件可能改变角色。

例如：

原本胆小的人：

经历事件后变得坚定。

---

原本强势的人：

发现自己无法保护所有人。

---

角色变化必须：

渐进。

---

# CONSEQUENCE-011 永久记忆

重大事件进入：

Character.Memory。

格式：

```text id="p8m4u6"
Event:

第一次案件发生

Participants:

所有幸存者

Emotional Impact:

High

Long Term Effect:

Increased distrust toward isolation
```

---

未来行为必须参考。

---

# CONSEQUENCE-012 案件后的日常

案件结束后：

不能立即恢复普通生活。

需要：

恢复阶段。

包括：

* 安静期；
* 讨论期；
* 重新建立关系；
* 新规则适应。

---

# AI执行检查（AI Compliance Checklist）

案件后：

* [ ] 死亡是否产生长期影响？
* [ ] 是否考虑不同角色反应？
* [ ] 是否更新关系？
* [ ] 是否更新心理状态？
* [ ] 是否改变社会结构？
* [ ] 是否避免角色无感？
* [ ] 是否影响未来剧情？

---

# Designer Notes

弹丸论破真正残酷的地方。

不是死亡。

而是：

死亡发生之后。

剩下的人必须继续活下去。

他们会带着：

记忆。

愧疚。

恐惧。

新的关系。

继续面对下一天。

案件不是一个章节的结束。

而是所有幸存者人生的一部分。

---

# Chapter 06 完成

本章定义：

* 黑白熊行为系统；
* 动机生成；
* 心理压力；
* 杀意产生；
* 案件触发；
* 犯罪生成；
* 案件后果。

下一章进入：

# Chapter 07 — 调查与学级裁判系统（Investigation & Class Trial Engine）

将定义：

* 尸体发现流程；
* 调查阶段；
* 证据生成；
* 证据管理；
* 矛盾发现；
* 学级裁判流程；
* 真相推理机制。

---

下一节文件标题：

`Paradiso_Chapter_07_Section_7_0_Investigation_Class_Trial_Overview.md`

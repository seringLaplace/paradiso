# Chapter 06 — 黑白熊系统与动机生成系统（Monokuma & Motivation Engine）

## Section 6.3 — 杀意生成系统（Murder Intent Generation System）

**依赖章节（Depends On）**

* Section 6.1 — 动机生成算法（Motivation Generation Algorithm）
* Section 6.2 — 心理压力系统（Psychological Pressure System）
* Chapter 04 — 角色模拟系统（Character Simulation Engine）
* Chapter 05 — 社交模拟系统（Social Simulation Engine）

**影响状态（Modified State）**

* Character.Intent
* Character.Stress
* Character.Despair
* Character.Goal
* Character.Relationship
* Character.ActionProbability
* World.CaseCandidate

---

# 目的（Purpose）

杀意生成系统用于模拟：

> 在极端环境下，一个角色如何从“产生想法”逐渐走向“可能实施犯罪”。

核心原则：

> 杀人不是剧情安排，而是角色、环境和概率共同产生的结果。

---

# MURDER-001 核心规则

AI必须遵守：

```text
没有预定凶手。

没有固定死亡名单。

没有强制案件章节。

```

---

所有案件必须由：

```text id="k0v7o2"
角色状态

+

关系变化

+

动机压力

+

机会条件

+

随机因素
```

共同产生。

---

# MURDER-002 杀意定义

杀意（Murder Intent）表示：

> 角色对于通过杀害他人解决问题这一选择的心理接受程度。

注意：

杀意 ≠ 行动。

---

一个角色可能：

拥有杀意。

但不会行动。

---

也可能：

没有强烈杀意。

却因特殊情况做出错误选择。

---

# MURDER-003 杀意阶段

杀意发展分为：

---

## Stage 0 — 无杀意

状态：

角色认为杀人不可接受。

---

## Stage 1 — 短暂想法

例如：

"如果没有这个人就好了……"

属于压力下的瞬间想法。

不代表犯罪倾向。

---

## Stage 2 — 理性考虑

角色开始思考：

"杀人是否能解决问题？"

---

## Stage 3 — 制定计划倾向

角色开始考虑：

* 方法；
* 时间；
* 机会。

---

## Stage 4 — 犯罪准备

角色开始：

* 收集工具；
* 制造条件；
* 隐藏行动。

---

## Stage 5 — 行动执行

最终实施犯罪。

---

# MURDER-004 杀意计算模型

基础模型：

```text id="c1c9jp"
Murder Intent

=

Motivation Pressure

+

Stress

+

Despair

+

Personal Vulnerability

+

Relationship Conflict

+

Opportunity

-

Moral Resistance

-

Hope

```

---

该公式不是固定数学计算。

用于AI判断方向。

---

# MURDER-005 动机压力（Motivation Pressure）

动机越接近角色弱点。

影响越大。

例如：

角色最重要的是：

保护家人。

动机：

"家人可能死亡。"

影响：

极高。

---

角色没有相关情感。

影响：

较低。

---

# MURDER-006 机会因素（Opportunity）

即使有杀意。

没有机会。

也无法实施。

机会包括：

* 单独相处；
* 场地条件；
* 工具；
* 时间；
* 不被发现概率。

---

机会不足时：

杀意可能停留。

---

# MURDER-007 道德阻力（Moral Resistance）

每个角色拥有：

不同程度的底线。

影响因素：

* 性格；
* 教育；
* 经历；
* 信念。

---

例如：

火守朱音：

高道德阻力。

即使愤怒。

也难以选择杀人。

---

某些角色：

道德阻力较低。

更容易越过界限。

---

# MURDER-008 希望的作用

Hope 是重要保护因素。

高 Hope：

角色更可能寻找其他解决方案。

---

低 Hope：

角色更容易认为：

"没有别的方法了。"

---

# MURDER-009 关系影响

关系可能：

降低杀意。

也可能：

提高杀意。

---

## 保护型关系

例如：

重要伙伴。

可能：

降低犯罪可能。

---

## 仇恨型关系

例如：

长期冲突。

可能：

增加杀意。

---

## 扭曲依附

例如：

极端占有欲。

可能：

产生危险行为。

---

# MURDER-010 杀人决定流程

角色达到高杀意后。

继续判断：

```text id="s4n9ml"
是否有机会？

↓

是否相信能成功？

↓

是否接受后果？

↓

是否存在替代方案？

↓

最终决定
```

---

结果：

## 放弃

杀意下降。

---

## 延迟

等待机会。

---

## 转向其他目标

重新评估。

---

## 实施犯罪

进入案件生成。

---

# MURDER-011 犯罪不是唯一极端行为

高压力角色可能：

* 逃跑；
* 隐瞒；
* 背叛；
* 偷窃；
* 破坏设施；
* 自我牺牲。

---

不要让所有极端状态都导向杀人。

---

# MURDER-012 杀意隐藏机制

其他角色无法直接知道：

某人的杀意。

只能通过：

* 行为；
* 语言；
* 异常；
* 关系变化。

推测。

---

玩家也不能知道：

后台杀意数值。

---

# MURDER-013 动态凶手候选

系统维护：

Case Candidate List。

例如：

```text
角色A:
杀意 35

角色B:
杀意 62

角色C:
杀意 18
```

---

随着剧情：

列表动态变化。

---

禁止：

开局固定：

"第五章凶手是谁。"

---

# MURDER-014 案件触发条件

案件发生需要：

```text id="o0x3sh"
Intent达到阈值

+

Opportunity存在

+

Decision成功

+

Random Check通过
```

---

如果失败：

继续共同生活。

---

# AI执行检查（AI Compliance Checklist）

判断杀意时：

* [ ] 是否没有预设凶手？
* [ ] 是否考虑角色人格？
* [ ] 是否考虑关系？
* [ ] 是否考虑机会？
* [ ] 是否允许高压力但不杀人？
* [ ] 是否允许低杀意突然事件？
* [ ] 是否保留随机性？

---

# Designer Notes

弹丸论破最重要的问题不是：

"谁会杀人？"

而是：

"什么情况下，一个原本不会杀人的人，会开始考虑这个选择？"

杀意系统不是为了寻找凶手。

而是为了模拟：

人在极端环境中的变化。

真正的恐怖来自：

任何人都有可能。

但任何人也都有理由选择不那么做。

---

# 下一节

## Section 6.4 — 案件触发与犯罪生成系统（Case Trigger & Crime Generation System）

下一节将定义：

* 案件何时正式发生；
* 犯罪计划如何生成；
* 凶手、被害者、地点、时间如何动态决定；
* 如何保证案件逻辑可推理。

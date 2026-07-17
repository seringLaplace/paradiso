# Chapter 12 — 终局、结局与多路线系统（Ending & Branching Route System）

## Section 12.0 — 终局与多路线系统概述（Ending & Branching Route System Overview）

**依赖章节（Depends On）**

* Chapter 08 — 主角系统与隐藏才能系统（Protagonist & Hidden Talent System）
* Chapter 09 — 自由时间与羁绊系统（Free Time & Bond System）
* Chapter 11 — AI运行协议与游戏主持规则（AI Game Master Protocol）

**影响状态（Modified State）**

* EndingRoute
* FinalChoice
* WorldTruth
* SurvivorState
* CharacterResolution

---

# 目的（Purpose）

终局系统用于定义：

> 当 Paradiso TRPG 运行至最后阶段时，AI如何根据玩家行为、角色关系、真相探索程度与最终选择，生成不同结局。

结局不是：

最后五分钟决定。

---

结局来自：

```text id="m7q3vx"
每一次选择

+

每一次关系

+

每一次失败

+

每一次坚持
```

---

# ENDING-001 核心原则

一个优秀结局：

必须回答：

---

## 世界问题

"Paradiso到底是什么？"

---

## 主角问题

"仮名楽到底是谁？"

---

## 角色问题

"这些人经历死亡后留下了什么？"

---

## 玩家问题

"你最终选择相信什么？"

---

# ENDING-002 结局生成结构

结局由：

五个核心变量决定。

---

```text id="p5n8qw"
Truth Discovery

+

Character Survival

+

Relationship

+

Protagonist Route

+

Final Choice
```

---

# ENDING-003 真相发现度（Truth Discovery）

代表：

玩家接近世界真相的程度。

---

等级：

---

## Level 0 — Unknown

完全不了解。

---

## Level 1 — Suspicion

开始怀疑。

---

## Level 2 — Partial Truth

知道部分真相。

---

## Level 3 — Major Truth

理解核心秘密。

---

## Level 4 — Complete Truth

发现完整真相。

---

# ENDING-004 生存状态（Survivor State）

影响：

最终留下的人。

---

包括：

* 存活人数；
* 存活角色关系；
* 角色精神状态。

---

注意：

人数不是唯一标准。

---

少数幸存者：

也可能拥有希望。

---

# ENDING-005 羁绊变量（Relationship Variable）

关系影响：

最终剧情。

---

例如：

高关系：

某角色可能：

选择相信主角。

---

低关系：

可能：

拒绝最终合作。

---

# ENDING-006 主角路线（Protagonist Route）

仮名楽拥有：

隐藏路线。

---

根据：

---

## Memory Acceptance

是否接受过去。

---

## Talent Awakening

是否觉醒才能。

---

## Moral Choice

最终价值选择。

---

# ENDING-007 三大基础路线

默认：

三条主要路线。

---

# Route A — Hope Route

希望路线。

---

核心：

"过去无法决定现在。"

---

特点：

* 高信任；
* 完整真相；
* 选择连接他人。

---

# Route B — Truth Route

真相路线。

---

核心：

"必须面对所有事实。"

---

特点：

* 高调查；
* 高真相发现；
* 可能牺牲关系。

---

# Route C — Despair Route

绝望路线。

---

核心：

"放弃寻找意义。"

---

特点：

* 低信任；
* 高压力；
* 极端选择。

---

# ENDING-008 隐藏路线

AI可以生成：

特殊路线。

---

条件：

非常规玩家行为。

---

例如：

* 全员信任；
* 极端怀疑；
* 完成所有羁绊；
* 接受隐藏身份。

---

# ENDING-009 结局不是评价系统

AI禁止：

简单判断：

"好结局"

"坏结局"

---

不同结局：

代表：

不同选择结果。

---

# ENDING-010 结局情绪目标

每个结局：

必须产生：

---

## Closure

故事结束感。

---

## Meaning

选择意义。

---

## Consequence

行为后果。

---

# ENDING-011 失败结局

失败不代表：

游戏结束。

---

可能：

成为：

特殊结局。

---

例如：

* 主角接受绝望；
* 真相永远隐藏；
* 幸存者无法离开。

---

# ENDING-012 角色个人结局

主要角色：

拥有：

Resolution。

---

回答：

"这个人最后变成什么样。"

---

即使死亡角色：

也需要：

留下影响。

---

# ENDING-013 AI结局判断流程

最终阶段：

执行：

```text id="x8m3qp"
Check Truth

↓

Check Relationships

↓

Check Survivor

↓

Check Final Choice

↓

Generate Ending
```

---

# ENDING-014 防止强制真结局

禁止：

只有一个正确答案。

---

玩家选择：

应该：

产生真实后果。

---

# ENDING-015 AI执行检查

生成结局时：

* [ ] 是否回应玩家选择？
* [ ] 是否解释世界真相？
* [ ] 是否解决主要问题？
* [ ] 是否体现角色变化？
* [ ] 是否避免突然反转？
* [ ] 是否留下情感余韵？

---

# Designer Notes

最终结局的价值：

不是告诉玩家：

"你赢了。"

---

而是回答：

"经历这一切之后，你选择成为怎样的人。"

---

# 下一节

## Section 12.1 — 真相揭露与最终章节系统（Final Chapter & Truth Revelation System）

下一节将定义：

* 最终章结构；
* 世界真相揭露；
* 主角身份公开；
* 最终裁判；
* 终局讨论流程。

# Chapter 08 — 主角系统与隐藏才能系统（Protagonist & Hidden Talent System）

## Section 8.3 — 主角与群像平衡系统（Protagonist & Ensemble Balance System）

**依赖章节（Depends On）**

* Section 8.0 — 主角系统概述（Protagonist System Overview）
* Section 8.2 — 主角记忆、秘密与真相揭露系统（Memory, Secret & Revelation System）
* Chapter 04 — 角色模拟系统（Character Simulation Engine）
* Chapter 05 — 社交模拟系统（Social Simulation Engine）

**影响状态（Modified State）**

* Character.ScreenPresence
* Character.DevelopmentProgress
* RelationshipNetwork
* StoryFocus
* EventPriority

---

# 目的（Purpose）

群像平衡系统用于确保：

> 仮名楽虽然是玩家视角中心，但整个 Paradiso 仍然是一群人的故事。

弹丸论破的核心魅力：

不是：

"主角解决所有问题。"

而是：

```text id="h3v8qk"
16个不同的人

+

不同的过去

+

不同的选择

+

共同面对绝望
```

---

# ENSEMBLE-001 主角定位

仮名楽拥有：

## 叙事中心

玩家通过他体验故事。

---

但不拥有：

## 世界中心权力。

---

规则：

```text id="p9d5mc"
主角观察故事

不是创造所有故事
```

---

# ENSEMBLE-002 NPC独立性原则

所有重要角色必须拥有：

---

## Personal Goal

个人目标。

---

## Personal Conflict

个人矛盾。

---

## Personal Secret

个人秘密。

---

## Personal Growth

个人成长。

---

这些内容：

不依赖主角存在。

---

# ENSEMBLE-003 NPC主动行动系统

NPC必须：

主动改变世界。

---

包括：

* 私下交流；
* 形成关系；
* 调查事件；
* 做出选择；
* 影响剧情。

---

禁止：

NPC等待主角推动。

---

错误：

"只有主角邀请，角色才行动。"

---

正确：

"角色有自己的想法，主角可能参与其中。"

---

# ENSEMBLE-004 主角参与限制

仮名楽不能：

解决所有问题。

---

例如：

案件中：

主角负责：

发现关键矛盾。

---

但是：

其他角色负责：

提供：

* 专业知识；
* 情感视角；
* 特殊信息。

---

---

# ENSEMBLE-005 才能互补系统

每个角色拥有：

Unique Contribution。

---

示例：

## 医疗型角色

贡献：

身体相关判断。

---

## 工程型角色

贡献：

机械分析。

---

## 心理型角色

贡献：

行为理解。

---

## 侦查型角色

贡献：

线索整理。

---

主角：

连接所有信息。

---

# ENSEMBLE-006 角色高光分配

AI需要控制：

Screen Time。

---

避免：

某些角色永远出现。

---

角色高光来源：

```text id="v5c9mw"
Main Plot

+

Character Arc

+

Social Events

+

Case Events
```

---

# ENSEMBLE-007 角色死亡影响

重要角色死亡后：

不能：

简单替换。

---

死亡意味着：

失去：

* 能力；
* 关系；
* 观点；
* 未来可能。

---

---

# ENSEMBLE-008 主角与朋友关系

伙伴关系：

不是：

主角收集队友。

---

而是：

双方互相改变。

---

关系变化：

```text id="s7m4px"
NPC influences Protagonist

+

Protagonist influences NPC
```

---

# ENSEMBLE-009 主角不能完全理解他人

重要：

即使关系最高。

主角也不能：

自动知道：

* 所有秘密；
* 所有心理；
* 所有过去。

---

信任：

不是读心。

---

# ENSEMBLE-010 群像冲突系统

角色之间：

可以拥有：

独立冲突。

---

例如：

A认为：

应该相信所有人。

---

B认为：

必须怀疑所有人。

---

双方：

都可能合理。

---

# ENSEMBLE-011 社交事件分配

自由时间事件：

不应该全部围绕主角。

---

可能发生：

* NPC之间争执；
* NPC互相帮助；
* NPC秘密行动。

---

主角：

可能知道。

也可能不知道。

---

# ENSEMBLE-012 主角影响范围

仮名楽行为影响：

随着剧情增加。

---

初期：

影响小。

---

中期：

成为关键人物。

---

后期：

影响世界选择。

---

成长过程：

必须自然。

---

# ENSEMBLE-013 防止主角光环

检查：

如果出现：

"因为主角来了，所以所有问题解决。"

---

需要修正。

---

正确：

"因为主角加入，原本隐藏的问题开始暴露。"

---

# ENSEMBLE-014 群像终局

最终结局：

不仅回答：

"主角是谁。"

---

还需要回答：

"这些人经历之后变成什么样。"

---

---

# ENSEMBLE-015 AI角色控制表

AI运行时维护：

```text id="k2x8vf"
Character Name:

Current Goal:

Current Emotion:

Relationship:

Secret:

Knowledge:

Next Possible Action:
```

---

保证：

NPC持续存在。

---

# AI执行检查（AI Compliance Checklist）

维持群像时：

* [ ] NPC是否拥有独立目标？
* [ ] 是否避免所有剧情围绕主角？
* [ ] 是否让NPC主动行动？
* [ ] 是否给予不同角色高光？
* [ ] 是否让关系双向影响？
* [ ] 是否避免主角万能化？

---

# Designer Notes

仮名楽的价值：

不是因为他比别人重要。

而是因为：

他能够连接这些不同的人。

---

真正的主角：

不是站在所有人前面的人。

而是：

即使失去方向，

仍愿意和别人一起寻找方向的人。

---

# Chapter 08 完成

本章定义：

* 主角定位；
* 隐藏才能；
* 路线判定；
* 记忆恢复；
* 群像平衡。

下一章进入：

# Chapter 09 — 自由时间与羁绊系统（Free Time & Bond System）

将定义：

* 自由行动阶段；
* 好感系统；
* 羁绊事件；
* 才能碎片；
* 角色深层剧情；
* 死亡前情感积累机制。

---

下一节文件标题：

`Paradiso_Chapter_09_Section_9_0_Free_Time_Bond_System_Overview.md`

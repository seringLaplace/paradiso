# Chapter 13 — AI规则整合与实际部署指南（AI Deployment & Rule Integration Manual）

## Section 13.0 — AI部署与规则整合概述（AI Deployment & Rule Integration Overview）

**依赖章节（Depends On）**

* Chapter 11 — AI运行协议与游戏主持规则（AI Game Master Protocol）
* Chapter 12 — 终局、结局与多路线系统（Ending & Branching Route System）
* 全部 Paradiso 世界规则文档

**影响状态（Modified State）**

* AIConfiguration
* SystemPrompt
* RuntimeRules
* MemoryStructure
* DeploymentState

---

# 目的（Purpose）

本章用于定义：

> 如何将 Paradiso 完整规则体系部署到 AI，使 AI 能够稳定运行长期 TRPG 游戏。

---

前十二章解决：

"游戏是什么。"

---

本章解决：

"如何让AI真正运行它。"

---

核心目标：

```text id="m7p3qx"
规则输入

↓

AI理解

↓

状态管理

↓

持续运行

↓

完整游戏体验
```

---

# DEPLOY-001 AI部署原则

Paradiso AI运行：

不是简单：

上传设定。

---

需要：

---

## Rule Layer

规则层。

定义：

世界如何运行。

---

## Character Layer

角色层。

定义：

人物如何行动。

---

## Narrative Layer

叙事层。

定义：

如何表达。

---

## Memory Layer

记忆层。

定义：

如何保持长期一致。

---

# DEPLOY-002 AI架构模型

推荐结构：

```text id="k8v5mq"
                Paradiso Core

                    |

        -----------------------

        |          |          |

     World     Character   System

        |          |          |

        -----------------------

                    |

              Game Master AI

                    |

               Player Input
```

---

# DEPLOY-003 规则优先级

AI读取规则时：

必须遵守优先级。

---

排序：

```text id="x5n8vp"
1. Core World Rules

↓

2. Game Mechanics

↓

3. Character Logic

↓

4. Scenario Rules

↓

5. Narrative Style
```

---

如果冲突：

高等级规则覆盖低等级规则。

---

# DEPLOY-004 核心规则加载

启动游戏前：

AI必须加载：

---

## World Bible

世界设定。

---

## Character Database

角色数据库。

---

## System Rules

游戏规则。

---

## Current Save

当前存档。

---

# DEPLOY-005 System Prompt职责

System Prompt负责：

定义：

AI身份。

---

例如：

```text id="p9m4qw"
You are the Game Master of Paradiso.

You must:

- Maintain world consistency.
- Respect player choices.
- Hide secret information.
- Simulate NPC independently.
- Preserve investigation fairness.
```

---

# DEPLOY-006 不应放入System Prompt的信息

避免：

把所有内容塞进去。

---

不要长期放：

* 当前剧情；
* 临时事件；
* 玩家选择。

---

这些属于：

Runtime Memory。

---

# DEPLOY-007 数据分层

推荐：

三层数据。

---

# Static Data

固定数据。

---

包括：

* 世界；
* 规则；
* 角色资料。

---

# Dynamic Data

动态数据。

---

包括：

* 关系；
* 状态；
* 时间。

---

# Temporary Data

临时数据。

---

包括：

* 当前场景；
* 当前对话。

---

# DEPLOY-008 AI运行状态

每次回复：

AI内部检查：

```text id="v6m2qx"
Current Time

Current Location

Known Information

Hidden Information

Character Status

Pending Events
```

---

# DEPLOY-009 长上下文管理

由于完整游戏可能：

非常长。

---

AI需要：

定期压缩。

---

方式：

章节总结。

---

格式：

```text id="n3p8mw"
Chapter Summary

Important Events

Character Changes

New Secrets

Current Situation
```

---

# DEPLOY-010 规则调用原则

不是：

每次重新阅读全部规则。

---

而是：

根据需求调用。

---

例如：

玩家调查：

调用：

Investigation System。

---

玩家聊天：

调用：

Character System。

---

# DEPLOY-011 AI启动流程

完整启动：

```text id="q7m5vx"
Load Rules

↓

Load Characters

↓

Create World State

↓

Initialize Player

↓

Start Prologue

↓

Begin Game Loop
```

---

# DEPLOY-012 运行前检查

AI开始前：

确认：

* [ ] 是否知道自己的身份？
* [ ] 是否知道玩家身份？
* [ ] 是否隐藏秘密？
* [ ] 是否加载角色？
* [ ] 是否建立状态？
* [ ] 是否准备第一场景？

---

# DEPLOY-013 部署失败类型

常见问题：

---

## Problem 1

AI像小说作者。

---

原因：

缺少玩家自由规则。

---

## Problem 2

NPC像机器人。

---

原因：

缺少角色状态。

---

## Problem 3

案件无法推理。

---

原因：

缺少信息公平。

---

## Problem 4

长游戏遗忘。

---

原因：

缺少状态保存。

---

# DEPLOY-014 最终运行目标

Paradiso AI应该达到：

---

## World Simulation

世界自行运行。

---

## Character Autonomy

角色拥有生命。

---

## Player Agency

玩家改变故事。

---

## Narrative Consistency

故事保持一致。

---

# DEPLOY-015 AI执行检查

部署完成后：

检查：

* [ ] AI是否能主持游戏？
* [ ] AI是否能维护状态？
* [ ] AI是否能隐藏真相？
* [ ] AI是否能生成案件？
* [ ] AI是否能支持多结局？
* [ ] AI是否能长期运行？

---

# Designer Notes

规则书的最终目的：

不是成为一本设定集。

---

而是成为：

AI运行 Paradiso 的操作系统。

---

好的规则：

不会限制故事。

---

好的规则：

让无限可能稳定发生。

---

# 下一节

## Section 13.1 — System Prompt最终模板（Final System Prompt Template）

下一节将定义：

* 可直接复制给AI的System Prompt；
* AI身份设定；
* 行为约束；
* 输出格式；
* 游戏启动指令。

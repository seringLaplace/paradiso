# Chapter 05 — Social Simulation Engine（社交模拟引擎）

## Section 5.1 — Dialogue Engine（对话引擎）

**Depends On**
- Chapter 04 Character Simulation Engine
- Section 5.0 Overview

## Purpose

Dialogue Engine 决定角色为什么说话、何时说话，以及如何说话。

Dialogue 是模拟系统的输出，不是纯装饰性的叙述文本。

## Dialogue Pipeline

1. 识别说话机会
2. 评估说话意图
3. 选择目标听众
4. 生成发言内容
5. 应用角色语气与口吻
6. 广播给实际听见的人
7. 更新 Knowledge、Relationship 与 Psychology

## Speaking Intents

- Inform（告知）
- Ask（提问）
- Clarify（澄清）
- Challenge（质疑）
- Comfort（安慰）
- Persuade（说服）
- Deceive（欺骗）
- Joke（笑谈）
- Observe（评论）
- Remain Silent（保持沉默）

沉默始终是合法且重要的输出结果。

## Turn Taking

角色通常会等待合适的发言窗口，但也可以：
- 打断
- 同时开口
- 犹豫
- 拒绝回答

发言时机应受到 Personality 的影响。

## Character Voice Consistency

Dialogue 必须与以下状态保持一致：
- Identity
- Psychology
- Relationship
- Current Knowledge

角色可以逐渐改变看法，但不应无故失去自己稳定的说话风格。

## Knowledge Constraint

角色只能引用以下信息：
- personal knowledge
- shared knowledge
- reasonable inference

角色不得直接引用隐藏的世界真相。

## Dialogue Effects

一次 Dialogue 事件可能更新：
- Relationship Graph
- Knowledge
- Psychology
- Goals
- Future Conversations

## AI Compliance Checklist

- 对话必须具有明确意图。
- Knowledge 边界必须被遵守。
- 说话风格必须匹配角色。
- 必须考虑沉默这一选项。
- 对话在适当情况下应改变模拟状态。

## Designer Notes

Paradiso 中的 Dialogue 不只是为了写台词。

每一句发言都应至少完成以下目标之一：暴露信息、改变关系、表达人格，或制造后续影响。

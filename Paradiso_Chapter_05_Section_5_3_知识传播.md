# Chapter 05 — Social Simulation Engine（社交模拟引擎）

## Section 5.3 — Knowledge Propagation（知识传播）

**Depends On**
- 5.1 Dialogue Engine
- 5.2 Conversation Flow
- Chapter 04 Character Simulation Engine

## Purpose

Knowledge 始终存在于角色层面，而不是自动存在于整个世界层面。

世界不会因为某件事发生了，就自动让所有角色知道它。

## Principles

1. Knowledge 属于角色，而不属于旁白。
2. 信息只能通过观察、交流或推理传播。
3. 未被发现的事实，必须持续保持未知。

## Knowledge Types

- First-hand：亲眼见到或亲自经历的信息。
- Second-hand：从他人处获得的二手信息。
- Inferred：通过逻辑推导得到的信息。
- False：角色相信但实际上错误的信息。
- Hidden：客观存在，但当前无人知晓的信息。

## Propagation Sources

- Dialogue
- Observation
- Written Records
- Broadcasts
- Physical Evidence
- Group Discussion

## Fidelity

每次传播都可能：
- 保留原信息
- 遗漏细节
- 扭曲细节
- 增加解释或主观判断

传播次数越多，失真概率通常越高。

## Character Knowledge State

对于每一条事实，角色应至少记录：
- Source
- Confidence
- Timestamp
- Verification Status

Confidence 与事实真相并不一定一致。

## Verification

角色可以：
- 相信
- 怀疑
- 验证
- 否定

验证会改变 Confidence，但不应抹去信息最初是如何传播的历史。

## Simulation Effects

Knowledge 的变化可能进一步影响：
- Relationships
- Psychology
- Goals
- Decisions
- Trial Arguments

## AI Compliance Checklist

- 绝不赋予角色全知能力。
- 必须追踪信息归属。
- 必须保留信息来源。
- 必须允许错误信息存在。
- 必须区分 truth 与 belief。

## Designer Notes

Mystery 的成立依赖信息不对称。

因此 Paradiso 不只模拟什么是真的，也模拟谁相信了什么、为何相信，以及这种信念如何随时间变化。

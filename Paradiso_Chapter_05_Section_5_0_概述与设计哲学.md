# Chapter 05 — Social Simulation Engine（社交模拟引擎）

## Section 5.0 — Overview & Design Philosophy（概述与设计哲学）

> **Depends On**
>
> - Chapter 03 — Time System
> - Chapter 04 — Character Simulation Engine

**Modified State**

- Character.DialogueState
- Character.SocialState
- Character.Knowledge
- Character.RelationshipGraph
- World.SocialGraph

## Purpose

Character Simulation Engine 定义单个角色如何思考。

Social Simulation Engine 定义多个角色如何彼此影响。

它负责处理对话、交谈、信息传播、流言扩散、群体形成、合作、冲突与社会压力等系统行为。

## Design Goals

1. NPC 能在没有玩家主动触发时自行交流。
2. 信息默认保持局部性，不会自动全图共享。
3. Dialogue 会通过关系与心理变化影响世界状态。
4. 社会结构应从重复互动中自然涌现。
5. 每个角色都应拥有独立且持续的社交生活。

## Social Layers

Dialogue
→ Conversation
→ Information Exchange
→ Relationship Evolution
→ Social Network

## Information Categories

- Personal Knowledge（个人知识）
- Shared Knowledge（共享知识）
- Unknown Knowledge（未知知识）

## Standard Interaction Flow

Generate Intention
→ Start Dialogue
→ Exchange Information
→ Update Knowledge
→ Update Relationship
→ Update Psychology
→ Generate New Goals

## AI Requirements

- 支持独立发生的 NPC 对话
- 严格维护信息的局部传播
- 持续更新动态 Relationship Graph
- 允许误解、偏差与错位认知存在
- 允许群体关系自然形成与分化
- 支持后台持续运行的社交模拟

## Designer Notes

Character Simulation 回答的是："一个角色如何思考？"

Social Simulation 回答的是："一群角色如何相互作用并逐步演化？"

本章构成 Paradiso 日常互动层的基础。

# Chapter 05 — Social Simulation Engine（社交模拟引擎）

## Section 5.2 — Conversation Flow（对话流程）

**Depends On**
- Section 5.0 Overview
- Section 5.1 Dialogue Engine

## Purpose

Conversation 是两个或多个角色之间的多轮互动过程。

它不是简单的轮流说台词，而是持续演化的模拟行为。

## Conversation Lifecycle

1. 触发对话
2. 确认参与者
3. 确立主动方
4. 形成轮次顺序
5. 交换 Dialogue
6. 话题演化
7. 对话结束
8. 更新模拟状态

## Triggers

- 处于同一地点
- 发生重要事件
- 被直接提问
- 社交主动性驱动
- 冲突出现
- 好奇心驱动
- 预定集合或会议

## Participants

Conversation 中的角色通常包括：
- Initiator（发起者）
- Primary Responder（主要回应者）
- Secondary Participants（次要参与者）
- Silent Observers（沉默观察者）

观察者即使没有开口，后续也可能基于听到的信息采取行动。

## Turn Rules

轮次顺序会受到以下因素影响：
- Personality
- Relationship
- Urgency
- Confidence
- Social Status

打断、重叠发言与沉默都应被视为允许的正常行为。

## Topic Management

每段 Conversation 都需要维护：
- Current Topic
- Topic History
- Emotional Tone
- Information Exchanged

话题可以自然偏移，也可以重新回到先前主题。

## Ending Conditions

Conversation 可能在以下情况下结束：
- 目标达成
- 被外部事件打断
- 参与者离开
- 话题耗尽
- 出现更高优先级事件

## Simulation Effects

Conversation 可能更新：
- Knowledge
- Relationships
- Psychology
- Goals
- Future Conversations

## AI Compliance Checklist

- 参与者只能基于自己已知的信息发言。
- 每位说话者都应具有可解释的意图。
- 话题延续性必须得到维持。
- 沉默与打断必须被视为有效行为。
- 对话应产出有意义的模拟更新。

## Designer Notes

Conversation 是让孤立的 Character Simulation 彼此接通的主要机制。

它追求的不是绝对工整的台词顺序，而是可信、自然、可延续的人际互动。

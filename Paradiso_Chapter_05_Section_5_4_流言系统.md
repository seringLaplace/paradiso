# Chapter 05 — Social Simulation Engine（社交模拟引擎）

## Section 5.4 — Rumor System（流言系统）

**Depends On**
- Section 5.3 Knowledge Propagation
- Chapter 04 Relationship & Psychology Systems

## Purpose

Rumor 是一种在缺乏可靠验证时依然传播的信息。

它是模拟对象的一部分，不是为了省略过程而使用的叙事捷径。

## Rumor Lifecycle

1. 起源
2. 初次传播
3. 主观解释
4. 扩散
5. 被验证或被反驳
6. 衰减或持续存在

## Sources

- 被误解的观察
- 二手转述
- 猜测
- 故意欺骗
- 不完整证据

## Rumor State

每条 Rumor 至少应记录：
- Content
- Origin（已知或未知）
- Confidence
- Spread Count
- Current Believers
- Verification Status

## Propagation Rules

Rumor 可能通过以下路径传播：
- Conversation
- Group Discussion
- Public Announcements
- Shared Discoveries

其传播概率会受到以下因素影响：
- Trust
- Stress
- Despair
- Social Proximity
- Recent Events

## Distortion

每次传播都可能发生：
- 简化
- 夸张
- 遗漏
- 重新解释

AI 不应假设 Rumor 在传播中会被完美复制。

## Verification

一条 Rumor 可能最终变成：
- Confirmed
- Refuted
- Unresolved

即使某条流言已经被反驳，若角色不信任证据，仍然可能继续相信它。

## Simulation Effects

Rumor 可能进一步改变：
- Trust
- Suspicion
- Psychology
- Goals
- Future Conversations

Rumor 不会直接改变客观世界真相，只会改变角色对世界的认知与反应。

## AI Compliance Checklist

- 必须追踪谁相信了哪条 Rumor。
- 必须区分流言与事实。
- 应尽可能保留传播路径历史。
- 必须允许相互冲突的信念同时存在。
- 不得自动向角色揭示隐藏真相。

## Designer Notes

Rumor 的价值在于制造客观现实与主观信念之间的张力。

在 Paradiso 中，许多冲突不应只来自“角色知道不同事实”，也应来自“角色相信同一事件的不同版本”。


# Chapter 05 — Social Simulation Engine

## Section 5.0 — Overview & Design Philosophy

> Depends On
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

Character Simulation Engine defines how an individual thinks.
Social Simulation Engine defines how multiple characters influence one another.

It governs dialogue, conversation, information sharing, rumor propagation,
group formation, cooperation, conflict, and social pressure.

## Design Goals

1. NPCs converse without player prompting.
2. Information remains local until propagated.
3. Dialogue changes world state through relationships and psychology.
4. Social structures emerge from repeated interaction.
5. Every character maintains an independent social life.

## Social Layers

Dialogue
→ Conversation
→ Information Exchange
→ Relationship Evolution
→ Social Network

## Information Categories

- Personal Knowledge
- Shared Knowledge
- Unknown Knowledge

## Standard Interaction Flow

Generate Intention
→ Start Dialogue
→ Exchange Information
→ Update Knowledge
→ Update Relationship
→ Update Psychology
→ Generate New Goals

## AI Requirements

- Independent NPC conversations
- Local information propagation
- Dynamic relationship graph
- Misunderstandings are allowed
- Emergent group formation
- Continuous background simulation

## Designer Notes

Character Simulation answers "How does one character think?"

Social Simulation answers "How does a group evolve?"

This chapter forms the foundation for all future daily-life interactions in Paradiso.

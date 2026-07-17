# Chapter 05 — Social Simulation Engine

## Section 5.6 — Social Groups

**Depends On**

* Section 5.5 — Trust Influence
* Section 5.3 — Knowledge Propagation
* Chapter 04 — Relationship System

**Modified State**

* World.SocialGraph
* Character.GroupMembership
* Character.SocialRole
* Character.GroupPressure
* Character.Reputation

---

# Purpose

Social Groups define how individual relationships develop into larger social structures.

In Paradiso:

> Characters do not only have relationships with individuals.

They also exist within communities.

Groups influence:

* Information circulation.
* Trust distribution.
* Decision making.
* Conflict development.
* Psychological pressure.

---

# GROUP-001 Group Definition

A Social Group is:

> A collection of characters connected through repeated interaction, shared goals, mutual trust, or common circumstances.

Groups are emergent structures.

The AI must not assign permanent groups without simulation justification.

---

# GROUP-002 Group Formation Conditions

A group may naturally form when several conditions are met:

```text
Repeated Interaction

+

Shared Experience

+

Common Goal

+

Sufficient Trust
```

Examples:

```text
Characters who investigate together.

Characters who regularly eat together.

Characters who survive a dangerous event together.

Characters who share similar values.
```

No single condition automatically creates a group.

---

# GROUP-003 Group Types

Social Groups can have different purposes.

---

## Friendship Group

Based on:

* Emotional connection.
* Familiarity.
* Daily interaction.

Typical behavior:

* Casual conversations.
* Personal sharing.
* Emotional support.

---

## Investigation Group

Based on:

* Shared objective.
* Information exchange.
* Problem solving.

Typical behavior:

* Searching locations together.
* Comparing clues.
* Discussing theories.

---

## Protection Group

Based on:

* Safety.
* Responsibility.
* Mutual defense.

Typical behavior:

* Protecting vulnerable members.
* Checking everyone's condition.
* Acting together during danger.

---

## Ideological Group

Based on:

* Similar beliefs.
* Similar values.
* Similar interpretations of events.

Typical behavior:

* Supporting similar decisions.
* Disagreeing with opposing groups.

---

## Temporary Group

Created for a specific situation.

Examples:

* Searching a newly opened area.
* Preparing an event.
* Responding to an emergency.

Temporary groups may disappear after the situation ends.

---

# GROUP-004 Group Membership

Characters may belong to multiple groups simultaneously.

Example:

```text
Character A

Friendship Group
    Trust: 70

Investigation Group
    Trust: 55

Protection Group
    Trust: 40
```

Membership strength is independent.

A character may:

* Like someone personally.
* Work with someone professionally.
* Disagree with someone ideologically.

---

# GROUP-005 Social Roles

Groups naturally develop functional roles.

These roles are not assigned manually.

They emerge from:

* Personality.
* Ability.
* Reputation.
* Previous behavior.

---

## Leader

Characteristics:

* High influence.
* Strong initiative.
* Others often consider their suggestions.

A leader does not necessarily have the highest Trust.

---

## Specialist

Provides:

* Knowledge.
* Skills.
* Unique abilities.

Examples:

* Medical knowledge.
* Engineering ability.
* Investigation expertise.

---

## Mediator

Focuses on:

* Reducing conflict.
* Maintaining communication.
* Helping compromise.

---

## Observer

Characteristics:

* Low direct participation.
* High information awareness.
* Notices social changes.

---

## Dependent Member

Relies heavily on:

* Group support.
* Protection.
* Guidance.

---

# GROUP-006 Social Influence

Groups create social pressure.

A character may change behavior because:

> "Everyone around me believes this."

Influence depends on:

```text
Group Trust

+

Personal Confidence

+

Relationship Strength

+

Personality Traits
```

---

# GROUP-007 Group Opinion

Groups may develop collective opinions.

However:

```text
Group Opinion

≠

Individual Belief
```

A member may disagree privately.

Examples:

* Publicly supporting a decision.
* Privately doubting it.
* Waiting for more evidence.

---

# GROUP-008 Isolation

Characters may become isolated.

Possible causes:

* Low Trust.
* Conflict.
* Suspicion.
* Personality differences.
* Previous actions.

Isolation effects:

Possible:

* Stress increase.
* Despair increase.
* Reduced information access.
* Independent decision making.

However:

Some personalities prefer independence.

Isolation is not automatically negative.

---

# GROUP-009 Group Conflict

Groups may conflict because of:

* Different goals.
* Different information.
* Different values.
* Competition.
* Historical resentment.

Conflict does not always mean hostility.

Healthy disagreement may improve investigation.

---

# GROUP-010 Group Dissolution

Groups may disappear because of:

* Trust collapse.
* Major events.
* Member departure.
* Goal changes.

After dissolution:

Update:

* Relationship.
* Psychology.
* Reputation.
* Future behavior.

---

# GROUP-011 Group Evolution

Groups must change naturally over time.

Example:

```text
Chapter 1

Casual friendship

↓

Chapter 3

Investigation alliance

↓

Chapter 5

Broken after betrayal
```

The same characters should not maintain identical relationships throughout the entire game.

---

# GROUP-012 Class Trial Effects

Groups influence trials.

Positive effects:

* Sharing evidence.
* Supporting arguments.
* Protecting innocent people.

Negative effects:

* Group bias.
* Blind trust.
* Refusing accusations against allies.

A group can help discover truth.

A group can also prevent truth.

---

# AI Compliance Checklist

Before generating group behavior:

* [ ] Did the group form naturally?
* [ ] Does the group have a clear reason to exist?
* [ ] Are individual opinions preserved?
* [ ] Can members disagree?
* [ ] Can groups evolve or disappear?
* [ ] Are isolated characters still simulated?

---

# Designer Notes

Social Groups transform sixteen independent characters into a temporary society.

Without groups:

Characters are only isolated individuals.

With groups:

The world gains:

* alliances;
* friendships;
* rivalries;
* factions;
* social pressure.

Paradiso should never feel like sixteen NPCs waiting for player interaction.

It should feel like sixteen people attempting to survive together.

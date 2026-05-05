# Snowflake Method

## Definition

The Snowflake Method is a structured planning method for long-form writing, especially fiction.

It starts with a compact story statement and progressively elaborates it into larger forms: a paragraph, character summaries, expanded plot summaries, scene lists, and eventually a draft.

The method is associated with Randy Ingermanson. It is called "snowflake" because a simple starting shape is repeatedly elaborated into a more complex structure.

## Core Pattern

The basic sequence is:

- write a one-sentence story premise
- expand it into a paragraph describing the major arc
- define the main characters, including goals, conflicts, motivations, and endings
- expand the plot summary into several pages
- build a scene-by-scene outline
- draft from that structure

The point is not merely to add more detail. The point is to make each new layer answer back to the previous layer and to the governing story claim.

## IA Interpretation

The Snowflake Method can be understood as center-out, relation-preserving elaboration.

Its hidden IA-like principle is:

> A coherent artifact can be developed by preserving alignment across levels of abstraction.

In narrative terms, the method creates traceability among:

- the one-sentence concept
- the paragraph-level structure
- character motivations
- plot turns
- scene-level decisions
- prose

The premise functions like a working architectural decision for the story. Later details should express, complicate, test, or revise that initial commitment.

## Relation-Preserving, Not Magic Emergence

It is tempting to describe the method as "complexity emerging from a simple rule." That is directionally useful but too magical.

A stronger formulation is:

> The Snowflake Method is progressive elaboration under constraint.

The initial sentence does not contain the whole story in a deterministic way. Instead, it creates a constraint that makes later choices easier to evaluate.

Useful tests:

- Does this scene connect to the story's central conflict?
- Does this character goal pressure the premise?
- Does this subplot alter the meaning or stakes of the main arc?
- Does this detail merely decorate the story, or does it change the structure?

## Several Core Ideas

When a story seems to have several core ideas, the structure usually falls into one of two forms.

### One Governing Premise With Several Arms

Many stories have one governing story question and several subordinate ideas.

Example shape:

```text
Governing story question
|-- Character arc A
|-- Character arc B
|-- Political or social conflict
|-- Mystery or operational problem
`-- Thematic tension
```

Each arm can be elaborated snowflake-style, but each should still relate to the governing question.

### Multiple Cores With An Organizing Relation

A genuinely multi-core story needs a clear relation among the cores.

Possible organizing relations:

- convergence: separate ideas move toward the same event or revelation
- collision: the ideas create incompatible demands
- contrast: each idea reveals the limits of the other
- recursion: the same idea appears at different scales
- causality: one core idea creates the conditions for another

Without one of these relations, the story is not multi-core. It is probably just several interesting ideas occupying the same draft.

## Practical Multi-Core Version

For a story with multiple core ideas:

- write one sentence for each core idea
- write one sentence describing the relation between them
- write one paragraph for each core's arc
- write one paragraph explaining how the cores converge, collide, contrast, or transform each other
- tag each scene by which core idea it advances

The key artifact is the relation map between the ideas, not the list of ideas itself.

## Failure Modes

- Treating the initial premise as sacred instead of provisional
- Adding local cleverness that does not serve the whole
- Mistaking thematic repetition for structural coherence
- Maintaining several separate flakes without defining how they interact
- Using the method to avoid discovery rather than to support it

## Operational Analogy

In engineering terms, the Snowflake Method resembles starting with a bounded context or core service responsibility, then deriving APIs, data models, runbooks, and observability from that center.

The value is not that the first sentence magically contains the system. The value is that each layer remains traceable to a conceptual center and can be checked for drift.

## Open Questions

- When should the initial premise be revised rather than preserved?
- How much traceability is useful before the method becomes mechanical?
- In multi-core stories, what evidence shows that the cores are structurally necessary rather than merely thematically adjacent?
- Can this method be generalized for IA synthesis notes, architecture decisions, or incident narratives?

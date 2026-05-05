# Snowflake Agent Writing System

## Idea

Build a writing system that automates Snowflake-style story development with a group of LLM agents operating over a shared story graph.

The system would not merely ask one model to write and another to edit. It would treat the story as a progressively elaborated dependency graph, where each new node must preserve coherence with the premise, character arcs, causal structure, and core thematic relations.

## Core Claim

LLM agents can help automate Snowflake-style writing if the system makes narrative structure explicit.

The hard part is not generating more text. The hard part is preserving global coherence under repeated expansion.

## Possible Agent Roles

- Expander: turns a premise into arcs, chapters, scenes, or beats
- Continuity checker: tracks facts, timeline, causality, constraints, and promises
- Cohesion checker: tests whether each node still serves the governing premise or core relation map
- Character agent: checks whether actions follow from goals, pressures, and prior choices
- Style editor: improves prose without changing structure
- Red-team critic: looks for ornamental scenes, weak causality, false stakes, and stated rather than dramatized theme

## Workflow Shape

```text
Story kernel
-> expanded outline node
-> critique and checks
-> accepted or revised node
-> updated story state
-> next expansion
```

The system should expand only through accepted state changes. Otherwise it risks producing locally fluent fragments that do not compose.

## Story Node Metadata

Each generated node should carry metadata such as:

- id
- parent_id
- level: premise, arc, chapter, scene, beat
- advances: core idea, character arc, conflict, or relation
- depends_on
- changes_state
- open_questions
- continuity_claims

This makes the Snowflake Method more graph-like and lets agents reason over relationships instead of just prose quality.

## Key Design Pressure

Expansion is cheap, so the system needs deletion pressure.

A checker should be allowed to reject a node with a judgment like:

> This node is fluent but structurally unnecessary.

Without that pressure, the app will likely produce automated bloat: more scenes, more subplots, more explanations, and weaker story shape.

## Stronger Formulation

The promising version is:

> A graph-backed multi-agent writing system for progressive narrative elaboration, with explicit coherence checks and pruning at every level.

This operationalizes the IA principle behind the Snowflake Method: center-out, relation-preserving elaboration.

## Open Questions

- What is the minimum useful story graph model?
- Should the system optimize for outline-first writers, discovery writers, or both?
- How should it distinguish structural necessity from stylistic preference?
- What evidence would show that the system improves story quality rather than merely increasing output volume?
- Can the same architecture support nonfiction essays, incident narratives, or architecture decision records?

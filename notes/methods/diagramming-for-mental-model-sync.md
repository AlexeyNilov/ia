# Diagramming for Mental Model Sync

## Purpose

Use diagrams as external reasoning surfaces, not as decoration or presentation polish.

The goal is to make important structure explicit enough that people can compare models, find disagreement, and reason about action under realistic constraints.

## When To Use It

Use this method when people need a shared model of:

- a system boundary
- a domain workflow
- an incident sequence
- a service dependency chain
- a state lifecycle
- an ownership or escalation path
- a proposed architecture change

It is especially useful when the current discussion contains phrases like "it is obvious", "everyone knows", "the system", "the platform", "the workflow", or "the team owns it" without concrete referents.

## Core Methods

### 1. Diagram For The Inference

Start by asking what inference the diagram should make cheaper.

Weak prompt:

- "Let's diagram the payment system."

Better prompts:

- "Which services are affected if the payment provider is slow?"
- "Where does payment state become durable?"
- "Which team can mitigate a failed refund?"
- "What signal proves the checkout path is degraded?"

Examples:

- For incident response, draw a timeline if the hard question is sequence.
- For architecture review, draw dependencies if the hard question is coupling.
- For domain modeling, draw state transitions if the hard question is lifecycle.
- For platform ownership, draw responsibility boundaries if the hard question is actionability.

Failure mode: drawing the topic rather than the reasoning problem.

### 2. Use Labeled Edges

Unlabeled arrows hide ambiguity. Every important relationship should say what kind of relationship it is.

Useful edge labels:

- causes
- depends on
- owns
- observes
- publishes
- consumes
- blocks
- mitigates
- escalates to
- changes state of
- validates
- stores
- retries

Examples:

- `checkout-api` publishes `PaymentRequested`
- `payment-worker` changes state of `PaymentAttempt`
- `fraud-service` blocks `OrderConfirmed`
- `orders-team` owns refund state transitions
- `latency-alert` observes p95 checkout latency

Failure mode: arrows that mean "talks to", "knows about", "depends on", and "causes" all at once.

### 3. Individual Model First, Shared Model Second

Before group synthesis, ask participants to sketch their model privately.

This reduces anchoring, authority bias, and premature convergence. The point is not artistic quality. The point is to surface hidden differences before the group normalizes them away.

Examples:

- In an incident review, ask each responder to sketch the causal chain before showing the official timeline.
- In a service ownership cleanup, ask each team to mark who they believe owns each dependency.
- In a domain workshop, ask product, engineering, support, and operations to draw the lifecycle separately before merging.
- Before changing a runbook, ask two on-call engineers to independently draw the decision tree they actually use.

Failure mode: the most fluent or senior person draws first, and everyone else edits around that frame.

### 4. Treat The Diagram As A Boundary Object

A useful diagram does not need every group to interpret every detail identically. It needs enough stable structure that different roles can coordinate through it.

Design the diagram so each audience can attach its local concerns without destroying the shared frame.

Examples:

- A service map can show dependencies for engineers, ownership for managers, and escalation paths for incident commanders.
- A domain event map can show business language for product, state changes for engineers, and failure points for SRE.
- A runbook flow can show decisions for responders, required evidence for reviewers, and automation candidates for platform teams.

Failure mode: optimizing the artifact for one community's notation so other groups cannot use it for coordination.

### 5. Layer Diagrams By Question

Do not create the one big diagram unless the question truly requires it.

Separate views by reasoning task:

- Context: who or what interacts with the system?
- Flow: what happens in the normal path?
- State: what entities change state?
- Failure: how does the system degrade?
- Observability: what signals prove each claim?
- Ownership: who can act?

Examples:

- For checkout, keep customer flow, payment state, service dependencies, alerts, and ownership in separate views with shared names.
- For a migration, separate current-state dependencies, target-state boundaries, rollout sequence, and rollback triggers.
- For incident learning, separate timeline, causal graph, detection path, and remediation ownership.

Failure mode: adding every concern to one diagram until it becomes cognitively expensive to use.

### 6. Force Self-Explanation

After drawing, make someone narrate a path through the diagram.

The useful test is whether the diagram supports a coherent explanation using explicit relationships.

Prompts:

- "Walk the path from customer action to durable state."
- "Explain how this alert leads to a mitigation."
- "Show where the system changes from synchronous to asynchronous."
- "Tell the failure story if this dependency times out."
- "Explain who can act at each point."

Examples:

- In architecture review: "Walk through what happens when the queue is full."
- In runbook review: "Explain why this check comes before the restart."
- In onboarding: "Explain how a request becomes an order."
- In postmortem: "Explain how detection, diagnosis, and mitigation connected."

Failure mode: people agree with the diagram visually but cannot use it to explain behavior.

### 7. Test Convergence By Reconstruction

Hide the diagram and ask participants to reconstruct the important parts or answer scenario questions.

This tests whether a shared model actually formed, rather than whether people nodded during the session.

Reconstruction prompts:

- "Redraw the three most important dependencies."
- "What changes state first?"
- "Which team owns the mitigation?"
- "Which signal proves the problem is customer-visible?"
- "What assumption would fail during regional failover?"

Examples:

- After a runbook workshop, ask a new on-call engineer to recreate the decision path from memory.
- After an architecture discussion, ask reviewers to identify the rollback trigger without looking at the diagram.
- After event storming, ask participants to list the events that must remain ordered.
- After an incident review, ask responders to reconstruct the detection-to-mitigation path.

Failure mode: treating momentary agreement as durable alignment.

## Practical Workflow

1. Name the decision or reasoning problem.
2. Choose the diagram type based on the inference needed.
3. Let people sketch individually first.
4. Merge models and mark disagreements explicitly.
5. Label relationships, not just nodes.
6. Split layers when the diagram starts mixing questions.
7. Run self-explanation against realistic scenarios.
8. Test reconstruction or scenario recall later.
9. Record open questions and ownership for keeping the artifact current.

## Strengths

- Makes hidden mental models inspectable.
- Reduces vague agreement.
- Finds ambiguous language early.
- Connects IA artifacts to operational decisions.
- Supports cross-role coordination without requiring a single perfect notation.
- Turns diagrams into reviewable artifacts rather than meeting residue.

## Limitations

- The method does not guarantee truth; it only exposes models for inspection.
- Groups can still converge on a wrong model if evidence is weak.
- High-fidelity diagrams may create false confidence.
- Without ownership, diagrams decay into outdated institutional memory.
- Some disagreements are political or organizational, not cognitive.

## Example Uses

### Incident Review

Create four linked diagrams:

- timeline of symptoms, actions, and state changes
- causal graph of contributing factors
- detection path from signal to human action
- ownership map for remediations

Then test the model with: "If this happened again with the primary region down, what would we detect first and who could act?"

### Service Catalog Design

For each service, capture:

- owned by
- depends on
- publishes
- consumes
- observed by
- mitigated by
- escalates to

This turns the catalog from inventory into an operational reasoning artifact.

### Runbook Improvement

Diagram the runbook as decisions and evidence, not just steps.

Example labels:

- "if error budget burn exceeds threshold"
- "check confirms customer-visible impact"
- "restart mitigates stuck workers"
- "escalate when state cannot be reconciled"

Then ask an on-call engineer to explain why each branch exists.

### Domain Modeling Workshop

Ask product, engineering, and operations to separately draw:

- lifecycle states
- domain events
- failure or exception paths
- ownership of state transitions

Merge only after naming conflicts and missing transitions are visible.

## Related Methods

- Event storming
- Concept mapping
- Causal loop diagramming
- State machine modeling
- C4 modeling
- Context mapping
- Incident timeline review
- Runbook review
- Architecture decision records

## Sources

- Larkin and Simon, "Why a Diagram is Sometimes Worth Ten Thousand Words" - diagrams help when layout makes useful inferences cheaper.
- Concept mapping research - labeled relationships and explicit propositions support learning and model inspection.
- Cognitive load theory - diagrams work better when they reduce unnecessary integration and search effort.
- Shared mental model research - team performance depends partly on shared knowledge content and structure.
- Boundary object research - artifacts can support coordination across groups with different local concerns.
- Retrieval practice and self-explanation research - reconstruction and explanation improve durable understanding and expose weak comprehension.

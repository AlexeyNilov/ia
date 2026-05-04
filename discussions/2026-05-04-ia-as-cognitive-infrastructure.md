# IA as Cognitive Infrastructure

## Context

Prompting claim:

> Some diagramming practices are evidence-aligned because they reduce cognitive load, externalize hidden structure, force explicit relations, support common ground, and make disagreement inspectable.

Question: this sounds close to what information architecture should do or provide.

## Crux

Yes. This is a strong candidate framing for IA: not merely organizing information for retrieval, but building structures that reduce the cost of forming, testing, sharing, and revising mental models.

In this framing, IA is cognitive infrastructure. It shapes what people can notice, compare, discuss, decide, operate, and remember.

## Core Claim

Good IA helps people reason together under constraints.

It should:

- reduce cognitive load
- externalize hidden structure
- force explicit relationships
- support common ground across roles
- make disagreement inspectable
- preserve context across time
- connect information to decisions and action

This makes IA broader than findability. Findability matters, but it is only one function. In operational and engineering contexts, the higher-value function is often model alignment.

## Useful Distinction

IA for finding:

- Where is the thing?
- What is it called?
- Which category contains it?
- How do I navigate to it?

IA for reasoning:

- What depends on what?
- What causes what?
- What changes state?
- What evidence supports this claim?
- What assumptions are being made?

IA for coordination:

- Who owns this?
- Who needs to know?
- What action follows?
- What changes during an incident?
- What context must survive handoff?

The same artifact can serve all three, but confusing them produces weak designs. A taxonomy optimized for lookup may not explain causality. A beautiful architecture diagram may not reveal ownership. A runbook may list steps without preserving the mental model behind them.

## SRE Analogy

A weak service catalog is an inventory.

A stronger service catalog is a shared operational model. It captures services, owners, dependencies, SLOs, escalation paths, failure modes, dashboards, alerts, runbooks, and operational maturity.

That makes it useful during:

- incidents
- onboarding
- architecture review
- dependency migration
- ownership cleanup
- postmortem follow-up

The value is not the list of services. The value is that the catalog makes operational reasoning cheaper and less dependent on tribal memory.

## What Holds Up

The connection between diagramming and IA is plausible because both are forms of external representation.

They help when they:

- make important relationships explicit
- reduce search effort
- expose gaps or contradictions
- create a shared object of discussion
- allow later reconstruction of the reasoning

This is why diagrams, maps, taxonomies, service catalogs, runbooks, and decision records belong in the same broad family of cognitive artifacts.

## Strongest Objection

"Cognitive infrastructure" may be too broad if it makes IA mean everything that helps people think.

The useful boundary is this: IA is concerned with the structure, naming, relationships, navigation, and use-context of information artifacts. It becomes cognitive infrastructure when those structures materially improve reasoning, coordination, or memory.

If an artifact only organizes labels without improving interpretation or action, it may be clerical structure rather than architecture.

## Failure Modes

- Decorative taxonomy: categories exist, but do not improve decisions.
- False coherence: a clean diagram hides disagreement or uncertainty.
- Navigation bias: the structure helps retrieval but not reasoning.
- Frozen model: the artifact preserves a model after reality has changed.
- Ownership ambiguity: information is organized, but no one can act on it.
- Terminology theater: labels sound precise but are not tied to observable distinctions.

## Working Test

An IA artifact is doing real work if it improves the quality, speed, or reliability of reasoning under realistic conditions.

Useful review questions:

- What question does this structure help answer?
- What inference becomes cheaper?
- What disagreement becomes visible?
- What assumption is now explicit?
- What action does this support?
- What would make this structure wrong?
- Who can maintain it when reality changes?

## Current Best Judgment

Treat IA as a companion discipline to software architecture, DDD, and SRE operational design.

DDD asks whether the domain concepts and boundaries are modeled coherently.

Software architecture asks whether system responsibilities and dependencies are shaped coherently.

SRE asks whether the system can be operated, observed, recovered, and improved under real conditions.

IA asks whether the information environment lets people find, interpret, reason about, and act on the right things with tolerable cognitive cost.

The overlap is not accidental. All four disciplines care about structure, boundaries, names, relationships, and consequences.

## Next Questions

- What are the main IA artifacts in an SRE organization?
- Which ones support finding, reasoning, coordination, or institutional memory?
- How can IA quality be reviewed in code repos, runbooks, service catalogs, dashboards, and incident records?
- What would an "IA review checklist" look like for operational artifacts?

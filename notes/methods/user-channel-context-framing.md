# User, Channel, Context Framing

## Purpose

Use `User, Channel, Context` as an early heuristic for understanding a messy situation before designing an information structure.

The point is to avoid treating an artifact as if it has stable meaning by itself. Meaning changes depending on who is using the information, where they encounter it, and what situation they are in.

## When To Use It

Use this method near the beginning of IA work, especially when the problem is still vague.

It is useful for:

- runbooks
- service catalogs
- dashboards
- alert documentation
- onboarding material
- incident knowledge bases
- architecture documentation
- support or escalation flows

It is especially useful when someone says, "It is just a document", "It is just a page", "It is just a dashboard", or "Everyone knows where this lives."

## How It Works

Ask three basic questions:

- User: who is trying to use this information?
- Channel: where or through what surface do they encounter it?
- Context: what situation are they in when they encounter it?

Then sharpen the result with one action question:

- What decision or action should become easier?

This keeps the model practical. Without the action question, the exercise can become generic persona work.

## Operational Version

For SRE and engineering contexts, use this phrasing:

> Who is acting, through what information surface, under what conditions, toward what decision?

This version forces the analysis toward operational reality rather than abstract audience description.

## Examples

### Runbook

Same artifact: database failover runbook.

Different realities:

- User: new on-call engineer
- Channel: alert link from PagerDuty
- Context: 3 a.m. incident, partial knowledge, customer impact likely
- Needed action: decide whether to fail over or escalate

Another reality:

- User: service owner
- Channel: wiki search
- Context: quarterly review, no active incident
- Needed action: verify whether the runbook is still accurate

The IA implication: the runbook needs not only clear steps, but also ownership, freshness, prerequisites, confidence signals, and escalation rules.

### Dashboard

Same artifact: checkout reliability dashboard.

Different realities:

- User: incident commander
- Channel: linked from incident channel
- Context: active incident, needs scope and customer impact quickly
- Needed action: decide severity and coordinate response

Another reality:

- User: team lead
- Channel: weekly review dashboard
- Context: planning reliability work
- Needed action: identify chronic weak points

The IA implication: one dashboard may not serve both contexts well. The first needs triage and decision support. The second needs trends and prioritization evidence.

### Service Catalog

Same artifact: service catalog entry.

Different realities:

- User: platform engineer
- Channel: internal catalog
- Context: preparing a dependency migration
- Needed action: identify owners and integration points

Another reality:

- User: on-call responder
- Channel: alert metadata link
- Context: degraded service, unclear ownership
- Needed action: find who can mitigate

The IA implication: a catalog entry should expose ownership, dependencies, runbooks, alerts, SLOs, and operational maturity rather than merely naming the service.

### Architecture Document

Same artifact: architecture proposal.

Different realities:

- User: reviewer
- Channel: pull request or design review tool
- Context: deciding whether to approve a change
- Needed action: evaluate risk, boundaries, and rollback

Another reality:

- User: future maintainer
- Channel: repo documentation
- Context: debugging unexpected behavior months later
- Needed action: understand why the current shape exists

The IA implication: architecture documentation should preserve constraints, rejected alternatives, and operational assumptions, not just the final design.

## Strengths

- Easy to remember.
- Easy to explain to non-specialists.
- Quickly exposes mismatches between artifact, audience, and situation.
- Prevents generic "user" thinking.
- Works across digital, document, operational, and organizational artifacts.
- Creates a bridge from IA to service design, SRE, and platform UX.

## Limitations

- It is an early heuristic, not a complete IA method.
- It does not by itself define taxonomy, navigation, metadata, or governance.
- It can become shallow persona work if not tied to decisions and actions.
- It may miss power, ownership, incentives, and maintenance realities.
- It does not prove that a structure works; it only improves the framing.

## Practical Heuristic

The model is useful when it changes the design conversation from:

> What should this artifact contain?

to:

> Who needs to act, where will they encounter this, and what constraints shape their interpretation?

If it does not change the questions being asked, it is probably being used too superficially.

## Related Methods

- Diagramming for mental model sync
- Journey mapping
- Stakeholder mapping
- Service blueprinting
- Runbook review
- Service catalog design
- Questions before starting a change

## Sources

- Abby Covert, How to Make Sense of Any Mess: users, channels, and context as part of facing reality
- Synthesized from repo discussion on IA as cognitive infrastructure and operational reasoning

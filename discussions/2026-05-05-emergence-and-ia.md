# Emergence and Information Architecture

## Context

Question sequence:

- What is emergence in systems?
- Do emergent properties relate to information architecture?
- Is the goal of IA practice to create conditions for positive emergent properties?
- Are IA interventions needed because unmanaged systems tend to produce negative emergent properties?

## Crux

Yes, IA can be understood as work that shapes the conditions under which desirable system-level information properties emerge.

The important precision: an IA practitioner does not directly install properties like findability, trust, navigability, or institutional memory. Those are system outcomes. The practitioner shapes labels, relationships, metadata, navigation, ownership, lifecycle rules, and governance so those outcomes become more likely and more reliable.

## Core Claim

IA practice shapes information environments so that people can find, understand, trust, use, connect, and maintain information in context.

This matters because information environments behave like systems. Pages, labels, taxonomies, search, metadata, ownership, incentives, workflows, and user habits interact. The global behavior users experience is often not reducible to any one artifact.

## Positive Emergent Properties

- Findability: users can locate the right thing through the interaction of naming, structure, metadata, search, cross-links, and task context.
- Trust: users believe information because freshness, ownership, provenance, consistency, review history, and past operational usefulness reinforce each other.
- Institutional memory: the organization can recover why decisions were made, what changed, what failed, and what was learned.
- Navigability: users can move through the information environment without constantly rebuilding the structure in their heads.
- Semantic stability: important terms keep sufficiently consistent meaning across teams, tools, and time.
- Lower cognitive load: users do not need to infer ownership, relevance, meaning, or canonicality repeatedly.
- Operational readiness: runbooks, alerts, dashboards, ownership, escalation paths, and current system state are meaningfully connected.
- Reuse: useful information can be found and adapted instead of recreated.
- Coherence across boundaries: local team structures remain intelligible when work crosses services, domains, or organizations.

## Why Negative Properties Emerge

Systems do not naturally become negative in a moral sense. They drift toward outcomes favored by local incentives, entropy, growth, ambiguity, and maintenance neglect.

In information environments, local publication is usually easier than global use. People add pages, fields, labels, channels, diagrams, dashboards, and decision records to solve immediate problems. Those choices can be locally rational while producing global incoherence.

## Negative Emergent Properties

- Unfindability: information exists but cannot be reliably located.
- Distrust: users stop believing the information environment because content is stale, contradictory, unowned, or wrong when needed.
- Semantic drift: shared terms gradually mean different things across teams or time.
- Duplicate truth: multiple artifacts appear to answer the same question, forcing users to judge which source is canonical.
- Orphaned knowledge: useful context exists but is disconnected from the workflows where it matters.
- Navigation debt: structures that once made sense preserve historical shape after reality has changed.
- Cognitive overload: users must inspect too many options, infer too many meanings, or remember too many exceptions.
- False confidence: the IA looks tidy while hiding weak evidence, stale assumptions, or unowned content.
- Local coherence, global incoherence: each team's area makes sense internally, but cross-team discovery fails.
- Institutional amnesia: the archive exists, but the organization cannot recover useful memory from it.
- Ownership ambiguity: users cannot tell who maintains, approves, or can explain information.
- Runbook decay: operational guidance falls out of sync with systems and erodes responder confidence.
- Search nihilism: users stop expecting search to work and fall back to tribal knowledge, bookmarks, or asking people.
- Dark knowledge: important knowledge survives only in private chats, individual memory, local scripts, or informal networks.

## Useful Caveat

Calling something emergent is only useful if it points back to mechanisms.

Weak version:

> We improve IA to create better knowledge flow.

Stronger version:

> We improve ownership metadata, service naming, runbook links, and incident-document lifecycle rules so responders can find trustworthy operational guidance during an incident.

The stronger version names the target property and the mechanisms expected to produce it.

## Current Best Judgment

IA is partly the design and maintenance of conditions for desirable emergent behavior in information systems.

This framing is useful because it shifts IA away from "organizing content" as a clerical activity and toward shaping system behavior: findability, trust, memory, semantic coherence, and operational readiness.

The risk is that "emergence" becomes a vague sophistication word. To avoid that, each claimed emergent property should be tied to observable behavior and to specific structural mechanisms.

## Measurement Principle

Emergent IA properties usually cannot be measured with one clean metric. They need proxy bundles: behavioral signals, quality signals, and maintenance signals.

The useful rule:

> Measure the user's ability to succeed in context, not the existence of IA artifacts.

A taxonomy existing is not evidence of findability. A runbook existing is not evidence of operational readiness. The metric should test whether the intended user can succeed under realistic conditions.

## Candidate Metrics

Findability:

- Task success rate: percentage of users who find the correct artifact without help.
- Time to find: median and p90 time to locate the right item.
- Search refinement rate: how often users need multiple searches.
- Zero-result or low-quality-result rate.
- "Ask someone" fallback rate for information that should be findable.
- Duplicate artifact creation rate for topics that already exist.

Trust:

- Staleness rate: percentage of high-value docs past review date or with stale owners.
- Provenance coverage: percentage of docs with owner, last reviewed date, source, and status.
- Conflict rate: number of contradictory artifacts found for the same question.
- Use-under-pressure rate: whether responders actually use the docs during incidents.
- Correction latency: time from detecting wrong information to fixing it.
- User confidence score after use, treated as weak unless paired with behavior.

Institutional memory:

- Decision recoverability: whether someone can reconstruct why a decision was made.
- Incident learning linkage: percentage of postmortem actions linked to updated runbooks, dashboards, alerts, or architecture notes.
- Repeat-incident rate caused by forgotten prior knowledge.
- Context survival: percentage of major changes with linked rationale, owner, date, and supersession status.
- Onboarding retrieval tasks: whether new team members can find prior decisions and failure history.

Navigability:

- Path efficiency: number of clicks or steps to reach common destinations.
- Wrong-turn rate: paths users take that do not lead to the intended object.
- Backtrack rate.
- Cross-boundary task completion rate for tasks spanning teams, services, or domains.
- Navigation consistency defects where the same type of object is reachable through incompatible structures.

Semantic stability:

- Term collision rate: same term used with materially different meanings.
- Alias rate: number of names used for the same service, concept, or object.
- Definition coverage for high-value terms.
- Review disagreement rate caused by terminology ambiguity.
- Search synonym dependence: users must know local vocabulary to find the thing.

Cognitive load:

- Steps to answer: number of artifacts a user must inspect before confidence.
- Choice overload points where users face many similar options without discriminators.
- Clarification-request rate.
- Rework caused by misunderstanding information.
- Subjective effort score after realistic tasks, treated as secondary.

Operational readiness:

- Incident task success: whether responders can get from alert to diagnosis or action using linked information.
- Alert-to-runbook coverage.
- Runbook freshness and owner coverage.
- Dashboard, runbook, and service ownership linkage completeness.
- Mean time to useful context during incident response.
- Post-incident documentation update completion rate.

Coherence across boundaries:

- Cross-team findability task success.
- Broken handoff rate caused by missing or ambiguous information.
- Inconsistent metadata rate across teams.
- Canonical source coverage for shared concepts.
- Number of local structures that cannot be mapped to shared structures.

Negative property signals:

- Duplicate truth: count of competing canonical-looking artifacts.
- Orphaned knowledge: artifacts with no inbound links from workflows.
- Dark knowledge: recurring questions answered from chat or individuals instead of durable sources.
- Search nihilism: low search usage combined with high people-asking behavior.
- Navigation debt: high traffic to stale structures or high backtracking from old categories.
- Ownership ambiguity: percentage of artifacts with missing, inactive, or disputed owners.

## Measurement Pattern

For each property, define:

- Target behavior: what should users be able to do?
- Scenario: under what realistic condition?
- Success metric: did they succeed?
- Friction metric: how costly was it?
- Maintenance metric: will the structure stay valid?
- Failure signal: what negative property appears when it decays?

Example:

> Responders can find trustworthy payment-service rollback guidance during a SEV-1.

Possible metrics:

- Percentage of responders who find the right runbook.
- p90 time to useful context.
- Runbook owner and freshness coverage.
- Alert-to-runbook link correctness.
- Number of contradictory rollback docs.
- Post-incident update latency.

This is stronger than assigning a vague "IA maturity score." A maturity score may be useful for reporting, but only after concrete behavioral and maintenance signals exist.

## Review Questions

- What positive emergent property is this IA intervention trying to make more likely?
- Which local structures or rules are expected to produce that property?
- What negative emergent property is likely if the system is left unmanaged?
- How would we observe whether the desired property is actually emerging?
- Which incentives or maintenance gaps could make the structure decay?
- Is this really emergence, or just a relabeling of a known design goal?

## Suggested Next Note

Create a map of `positive and negative emergent properties in IA`, with each property connected to likely mechanisms, failure modes, and observable signals.

# IA and Spec-Driven Development

## Definition

Information architecture and spec-driven development are both practices for making downstream work legible before implementation.

IA does this for meaning, retrieval, and structure in an information space.

Spec-driven development does this for behavior, constraints, and validation in a software system.

The useful connection is not merely that both involve planning or documentation. The stronger connection is that both create shared constraint systems that reduce ambiguity across design, implementation, review, and change.

## Why It Matters

This connection matters because it places IA closer to engineering coordination than to surface-level content organization.

Both IA and specs help teams externalize assumptions about:

- what units exist
- what they are called
- how they relate
- what actions are possible
- what constraints must hold
- what should remain stable as the system changes

That makes both disciplines relevant where systems need to survive scale, handoffs, drift, and partial knowledge.

In operational environments, this matters because many failures are not failures of expression but failures of structure. A runbook library, service catalog, or incident knowledge base can fail for reasons analogous to a weak software spec: unclear boundaries, overloaded terms, hidden assumptions, and no reliable way to tell whether the artifact still matches reality.

## Key Characteristics

- IA is a specification practice for meaning and retrieval.
- Spec-driven development is a specification practice for behavior and implementation.
- IA usually defines the shape of an information space before every item inside it is fully known.
- Specs usually define expected behavior before or alongside code.
- Both serve as coordination artifacts between multiple contributors.
- Both improve review quality by making structural disagreements visible earlier.
- Both support governance by making invariants, naming, and boundaries explicit.

## Examples

- A taxonomy for operational documents is an IA artifact.
- A schema for service metadata is a spec artifact.
- Both answer a similar class of question: what exists here, how is it distinguished, and how should people or systems interact with it?

- Navigation from alert to dashboard to runbook to ownership record is an IA concern.
- The contract between an API request, expected response, failure mode, and test suite is a spec concern.
- In both cases, the artifact exists to reduce ambiguity before someone is forced to improvise under pressure.

- A content type with required metadata fields resembles a schema.
- Labeling rules in IA resemble naming conventions or interface contracts in software.
- Governance for information structures resembles architectural governance for APIs, domain boundaries, and change control.

## Related Concepts

- Domain-driven design: overlaps strongly in naming, boundaries, and shared language
- Knowledge management: overlaps in institutional memory, retrieval, and governance
- Content strategy: overlaps in deciding what information should exist and for whom
- API contracts: a stronger engineering analogue than generic "documentation"
- Service catalogs and runbook systems: operational cases where IA and specs often meet directly

## Open Questions

- How far can IA be treated as a specification discipline before the analogy starts to break?
- Which IA artifacts are best understood as contracts, and which remain too interpretive for that framing?
- What is the operational equivalent of validation for IA: findability tests, incident performance, content trust signals, or something else?
- Can a service catalog be treated as both an IA system and a spec surface for organizational reality?

## Sources

- Synthesized from repo discussions on IA, DDD, SRE, and spec-driven development
- Based on the distinction that IA structures meaning and retrieval, while specs structure behavior and verification

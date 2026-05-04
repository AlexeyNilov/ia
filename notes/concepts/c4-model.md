# C4 Model

## Definition

The C4 model is a software architecture diagramming approach organized around four levels:

- Context
- Containers
- Components
- Code

Its purpose is to describe software systems at different levels of abstraction without forcing every audience into the same diagram.

## Why It Matters

C4 is useful because it separates architectural questions by scale.

That matters for IA because many architecture diagrams fail by mixing audience needs:

- executives need system context
- teams need ownership and deployment boundaries
- engineers need component responsibilities
- maintainers may need code-level structure

C4 gives a simple ladder of abstraction so people can choose the right view for the question.

## Key Characteristics

- Starts with system context before internal detail.
- Separates containers from components.
- Encourages explicit relationships between boxes.
- Works well for communicating existing systems and proposed changes.
- Is lightweight compared with formal modeling languages.

## Examples

For a checkout platform:

- Context: customer, payment provider, fraud provider, fulfillment system.
- Container: web app, checkout API, payment worker, order database, message broker.
- Component: payment authorization component, refund component, retry scheduler.
- Code: classes, modules, or packages inside a component.

Operational example:

A C4 container diagram can show which deployable unit owns payment retries and which database stores payment attempt state.

## Related Concepts

- Software architecture
- System context diagrams
- Dependency mapping
- Ownership mapping
- Diagramming for mental model sync
- Architecture decision records

## Open Questions

- How should C4 diagrams represent runtime failure modes, ownership, and observability?
- When does C4 become too implementation-centered for domain discovery?
- What metadata should accompany a C4 diagram so it stays trustworthy?

## Sources

- Simon Brown's C4 model
- Synthesized from repo discussion on diagramming, IA, and operational reasoning

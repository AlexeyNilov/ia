# BPMN

## Definition

BPMN, Business Process Model and Notation, is a formal notation for modeling business processes.

It represents activities, events, gateways, sequence flows, message flows, pools, lanes, and related process elements.

## Why It Matters

BPMN is useful when a process needs more precision than an informal flowchart.

It can clarify:

- where a process starts and ends
- which steps are activities versus events
- where decisions branch or merge
- which participants exchange messages
- where responsibility changes between roles or systems
- which paths are exceptions rather than the happy path

For IA, BPMN matters as a structured language for process information.

## Key Characteristics

- More formal than casual boxes and arrows.
- Distinguishes control flow from message flow.
- Uses pools and lanes to show participants and responsibilities.
- Represents gateways, events, tasks, and subprocesses with specific semantics.
- Can be used for documentation, analysis, and in some environments execution.

## Examples

Incident escalation process:

- Start event: alert triggered.
- Task: assess customer impact.
- Gateway: customer impact confirmed?
- Task: declare incident.
- Message flow: notify incident channel.
- Lane change: service owner investigates while incident commander coordinates.
- End event: incident resolved and follow-up created.

Order fulfillment process:

- Start event: order confirmed.
- Task: reserve inventory.
- Gateway: inventory available?
- Message flow: request shipment.
- Exception path: cancel or backorder.

## Related Concepts

- Process modeling
- Flowcharts
- Swimlane diagrams
- Event storming
- Runbook design
- Diagramming for mental model sync

## Open Questions

- When does BPMN precision help, and when does it create notation overhead?
- Which operational processes deserve formal BPMN versus a simpler runbook flow?
- How should BPMN models stay aligned with actual system behavior?

## Sources

- Object Management Group BPMN standard
- Synthesized from repo discussion on diagramming, IA, and process clarity

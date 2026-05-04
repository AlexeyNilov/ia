# Event Storming

## Definition

Event Storming is a collaborative modeling method for exploring a business or system process through domain events.

Participants map things that have happened, usually as past-tense events, then add commands, actors, policies, aggregates, external systems, questions, and pain points around them.

## Why It Matters

Event Storming is useful because it shifts discussion away from abstract nouns and toward observable state changes.

That makes hidden disagreement easier to see:

- Which events actually occur?
- In what order?
- Who or what causes them?
- Which decisions are manual, automated, or policy-driven?
- Where do failures, delays, or handoffs appear?

For IA, the value is that it exposes the event structure behind a domain vocabulary.

## Key Characteristics

- Starts from domain events, not database tables or UI screens.
- Uses workshop participation to compare mental models.
- Makes temporal order and causal assumptions visible.
- Helps discover bounded contexts, state transitions, and ambiguous language.
- Works best when people with different perspectives are present.

## Examples

Payment flow:

- `CartCheckedOut`
- `PaymentRequested`
- `PaymentAuthorized`
- `OrderConfirmed`
- `PaymentFailed`
- `RefundRequested`
- `RefundCompleted`

Incident flow:

- `LatencyIncreased`
- `AlertTriggered`
- `IncidentDeclared`
- `TrafficShifted`
- `QueueDrained`
- `CustomerImpactResolved`

Operational question:

If teams disagree about whether `OrderConfirmed` happens before or after durable payment authorization, the diagram has exposed a real modeling problem.

## Related Concepts

- Domain-driven design
- Domain events
- Bounded contexts
- State machine modeling
- Diagramming for mental model sync
- Incident timeline review

## Open Questions

- Which parts of Event Storming are essential, and which are workshop ritual?
- How should Event Storming outputs be maintained after the workshop?
- When does an event map become too detailed to support reasoning?

## Sources

- Alberto Brandolini's Event Storming method
- Synthesized from repo discussion on diagramming, shared mental models, and IA as cognitive infrastructure

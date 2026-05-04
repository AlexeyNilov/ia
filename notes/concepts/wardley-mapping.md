# Wardley Mapping

## Definition

Wardley Mapping is a strategy mapping method that places components of a value chain on a map according to their visibility to users and their stage of evolution.

The typical vertical axis shows user value or visibility. The horizontal axis shows evolution from novel/custom to industrialized/commodity.

## Why It Matters

Wardley Mapping is useful when the question is strategic position rather than process flow or software structure.

It helps ask:

- What does the user actually value?
- What capabilities are needed to deliver that value?
- Which capabilities are novel, custom, productized, or commodity?
- Where should we build, buy, outsource, automate, or standardize?
- Which dependencies are strategically important but operationally invisible?

For IA, the value is that it makes strategic assumptions explicit and spatially comparable.

## Key Characteristics

- Starts from user needs.
- Maps value chains rather than org charts.
- Distinguishes visibility from evolution.
- Helps reason about build-versus-buy, platform investment, and commoditization.
- Is more strategic and situational than descriptive architecture diagrams.

## Examples

Internal developer platform:

- User need: teams deploy safely.
- Visible capabilities: deployment workflow, service templates, release status.
- Less visible capabilities: CI runners, artifact storage, policy engine, secrets management.
- More commodity capabilities: source control, container registry, monitoring backend.
- More custom capabilities: organization-specific golden paths, compliance policies, service maturity model.

Operational question:

If a team spends custom engineering effort on a commodity capability, the map can expose a possible misallocation. That is not proof by itself, but it is a useful challenge.

## Related Concepts

- Strategy mapping
- Value chain analysis
- Platform strategy
- Build versus buy decisions
- Service catalogs
- Diagramming for mental model sync

## Open Questions

- How reliable are evolution judgments without market evidence?
- When does a Wardley map become a persuasive story rather than a testable strategy artifact?
- How should maps be validated against operational cost, incidents, and adoption data?

## Sources

- Simon Wardley's mapping method
- Synthesized from repo discussion on diagrams, IA, and operational decision support

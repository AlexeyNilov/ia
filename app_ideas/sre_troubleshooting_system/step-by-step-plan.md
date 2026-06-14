# Step By Step Plan

## Aim

Build the smallest useful SRE-Codex troubleshooting aid:

```text
Given a service and a time window, produce a compact incident packet and use it to drive hypothesis-based troubleshooting.
```

Do not start with broad autonomy, remediation, or a full incident platform.

## Phase 1: Pick The Narrow Test Case

Choose one production-like service that has:

- reasonably consistent Kubernetes labels
- logs in ELK
- metrics in VictoriaMetrics
- deployment history
- at least one known past incident or near miss

Output:

- selected service name
- selected historical incident
- known symptom time window
- expected root cause or mitigation path

Success criterion:

- you can later compare Codex's reasoning against what actually happened.

## Phase 2: Define Service Identity

Create a first service context entry using `service-context-template.yaml`.

Do this manually for the first service. Automation can come later.

Minimum fields:

- canonical service name
- namespace
- cluster
- workload name
- labels for logs
- labels for metrics
- repo
- owner
- known downstream dependencies

Success criterion:

- one canonical name can be resolved to Kubernetes, ELK, VictoriaMetrics, and deployment metadata.

## Phase 3: Build The V0 Incident Packet

Implement or manually compose the first packet using `incident-packet.md`.

V0 sections:

1. service identity
2. recent changes
3. Kubernetes health
4. metric deltas
5. top log signatures
6. open questions

For each section, prefer short structured output.

Success criterion:

- the packet can be pasted into Codex without raw data dumps and still supports useful reasoning.

## Phase 4: Add Tool Wrappers Around Existing MCP Access

Create thin wrappers around current MCP capabilities. Each wrapper should aggregate before returning data.

Suggested V0 tools:

```text
get_service_context(service)
get_recent_changes(service, window)
get_k8s_health(service, window)
compare_metrics(service, window, baseline)
summarize_logs(service, window, filters)
```

Do not expose raw logs or broad metric queries as the default path.

Success criterion:

- each tool returns stable JSON or YAML-like data with bounded size.

## Phase 5: Use The Scratchpad During Review

Use `incident-scratchpad-template.md` for every test run.

Codex should produce:

- known facts
- timeline
- 2-4 hypotheses
- evidence for and against each hypothesis
- missing evidence
- next discriminating query
- candidate mitigations

Success criterion:

- each hypothesis has a mechanism and a next test.

## Phase 6: Run Historical Incident Replays

Replay the selected incident with limited context.

Run 1:

- give Codex only the incident packet
- ask for hypotheses and next queries

Run 2:

- allow Codex to request additional summarized evidence
- update the scratchpad after each query

Compare against the real incident.

Measure:

- time to useful hypothesis
- number of tool calls
- estimated token use
- false leads
- missing context
- whether the proposed mitigation was reasonable

Success criterion:

- the system helps identify the right direction faster than a raw-tool conversation.

## Phase 7: Close The Gaps

Only add tooling for gaps observed in replay.

Common gaps to check:

- service names do not align across systems
- deploy/config history is hard to query
- dependency data is missing
- baseline windows are not available
- log signatures are too noisy
- metrics lack route or operation labels
- Codex repeatedly asks for the same context

Success criterion:

- each new component is justified by a failed or weak replay, not by imagined completeness.

## Phase 8: Expand To Three Services

Add two more services with different operational profiles.

Pick one of each if possible:

- user-facing API
- background worker
- stateful or queue-dependent service

Success criterion:

- the same packet shape still works without becoming too generic or too large.

## Phase 9: Decide Whether To Productize

After three services and at least two replayed incidents, decide whether the system is worth deeper investment.

Decision criteria:

- Does it reduce time to a plausible and testable hypothesis?
- Does it reduce repeated context gathering?
- Does it avoid raw-data token waste?
- Does it improve incident notes?
- Does it create fewer false confident explanations?

If the answer is weak, improve observability and service identity before adding more agent behavior.

## First Week Checklist

1. Choose one service.
2. Fill one service context file.
3. Pick one historical incident.
4. Manually assemble one incident packet.
5. Ask Codex for hypotheses using the scratchpad format.
6. Record what evidence was missing.
7. Build only the first wrapper that would have removed the biggest manual step.


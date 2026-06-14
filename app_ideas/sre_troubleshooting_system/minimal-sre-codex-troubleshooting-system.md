# Minimal SRE-Codex Troubleshooting System

## Question

What is the minimal tooling and knowledge needed for effective troubleshooting to emerge from a pair of:

- an SRE engineer
- Codex with access to deployment, logs, Kubernetes state, and metrics

The goal is not to encode many static playbooks. The goal is to create enough stable operational context, tool contracts, and reasoning discipline that Codex can help form and test useful hypotheses without depending on stale procedural knowledge.

## Crux

The system should minimize static incident instructions, but it cannot minimize operational semantics to zero. Troubleshooting needs stable names, boundaries, timelines, ownership, and signal meaning. Without those, Codex can query data but cannot reliably decide which evidence discriminates between competing explanations.

The minimum useful system is therefore:

1. stable service identity
2. compact service context
3. recent change context
4. structured signal summaries
5. an explicit hypothesis model
6. a small incident scratchpad
7. safe action boundaries

## Core Claim

Codex should not be treated as a playbook executor. It should be treated as an evidence-oriented troubleshooting partner.

Its job is to:

- establish the symptom and time window
- build a provisional operational map
- identify recent changes
- compare current behavior with baseline behavior
- generate competing hypotheses
- ask discriminating questions
- update confidence as evidence arrives
- preserve what was ruled out

The system succeeds if it reduces time to a useful hypothesis and mitigation path without producing confident but weakly supported explanations.

## What "Service" Means

In this system, `service` should mean a stable operational identity, not a Kubernetes pod ID.

A pod is an instance. It is ephemeral, low-level, and often too narrow for troubleshooting. A service identity should be the durable thing an engineer would name during an incident.

Examples:

- `checkout-api`
- `payment-gateway`
- `search-indexer`
- `billing-worker`
- `notification-service`

The service identity should map to lower-level runtime objects:

- Kubernetes namespaces
- Deployments, StatefulSets, DaemonSets, Jobs, or CronJobs
- pods and containers
- images and versions
- config maps and secrets references
- service mesh identities, if present
- log indexes or labels
- metrics labels
- dashboards and alerts
- repo and owner

This is similar to a domain model distinction: `service` is the aggregate root for operational reasoning; pods are implementation/runtime entities inside that boundary.

### Why Pod ID Is The Wrong Primary Key

Pod IDs are useful when debugging a specific failure mode:

- one bad replica
- restart loop
- node-local issue
- container OOM
- bad scheduling placement

But pod IDs are a poor root object because they hide the higher-level question: what user-facing or dependency-facing capability is degraded?

The primary key should usually be:

```text
environment + cluster + namespace + service_name
```

Then tools can descend to pods only when the evidence points there.

## Minimal Durable Knowledge

The durable knowledge should be small, factual, and cheap to refresh.

### Service Catalog

For each service:

- canonical service name
- aliases used in logs, metrics, deployment tools, and repos
- owner or escalation path
- repo
- runtime type
- namespace and cluster
- criticality or tier
- user-facing or internal role

### Dependency Context

For each service:

- upstream callers
- downstream services
- databases
- queues or streams
- external APIs
- shared infrastructure dependencies

This should not pretend to be a perfect architecture diagram. It is a starting map for blast-radius reasoning.

### Signal Inventory

For each service:

- log locations and label conventions
- key RED metrics
- key saturation metrics
- alert names
- dashboards
- trace availability, if any

### Change Inventory

For each service:

- deploy history
- image versions
- config changes
- feature flag changes
- infra changes
- dependency version changes

This may be the highest-value missing context. Many incidents are solved by correlating symptom start with change history.

### Safe Action Boundaries

Codex should know:

- read-only commands it may run freely
- commands that require engineer approval
- commands that are forbidden
- data sensitivity limits
- production mutation limits

This prevents the system from needing long incident playbooks while still maintaining operational control.

## Minimal Tool Contracts

Existing MCP tools provide access to deployment data, ELK logs, Kubernetes, and VictoriaMetrics. The missing layer is not more raw access. It is compact, structured summaries.

### `get_service_context(service)`

Returns the operational identity packet for a service.

Suggested fields:

```yaml
service: checkout-api
environment: prod
cluster: eu-prod-1
namespace: checkout
owners:
  - team: payments-platform
repo: git.example.com/payments/checkout-api
runtime:
  kind: deployment
  selector: app=checkout-api
  containers:
    - checkout-api
current_version:
  image: registry.example.com/checkout-api:1.42.7
  deployed_at: 2026-06-14T09:12:00Z
dependencies:
  downstream:
    - payment-gateway
    - pricing-api
    - postgres-checkout
signals:
  logs:
    - elk_index: prod-checkout-*
      labels:
        service: checkout-api
  metrics:
    - http_request_duration_seconds
    - http_requests_total
    - container_cpu_cfs_throttled_seconds_total
alerts:
  - CheckoutHighErrorRate
  - CheckoutLatencyP95
```

The exact schema matters less than stable naming and low ambiguity.

### `get_recent_changes(service, window)`

Returns deploys, config changes, feature flag changes, and relevant infra changes in the time window.

This should answer:

- what changed before the symptom?
- what changed during the symptom?
- what changed in dependencies?
- what changed in shared infrastructure?

### `summarize_logs(service, window, filters)`

Returns signatures, counts, first-seen timestamps, and representative samples.

Default output should not be raw logs. It should be something like:

```yaml
window: 2026-06-14T09:00:00Z/2026-06-14T10:00:00Z
top_error_signatures:
  - signature: "Timeout calling payment-gateway"
    count: 1842
    first_seen: 2026-06-14T09:17:21Z
    previous_baseline_count: 12
    sample_request_ids:
      - req-123
      - req-456
  - signature: "Connection pool exhausted"
    count: 317
    first_seen: 2026-06-14T09:19:04Z
    previous_baseline_count: 0
representative_samples:
  - timestamp: 2026-06-14T09:17:21Z
    level: error
    message: "Timeout calling payment-gateway after 2000ms"
    request_id: req-123
```

Raw logs should be available only as a drill-down.

### `compare_metrics(service, window, baseline)`

Returns current values compared with a relevant baseline.

Useful comparisons:

- request rate
- error rate
- latency percentiles
- saturation
- pod restarts
- throttling
- memory pressure
- queue depth
- dependency latency

Absolute values are weaker than deltas and shape changes.

### `get_k8s_health(service)`

Returns Kubernetes health summarized at the service level.

Suggested fields:

- desired vs available replicas
- rollout status
- restarts by pod
- OOMKilled events
- probe failures
- recent events
- CPU and memory requests/limits
- throttling
- node placement anomalies

### `find_related_signals(service, window)`

Returns anomalies in upstreams, downstreams, and shared infrastructure.

This supports blast-radius reasoning:

- is the issue isolated to this service?
- are all callers affected?
- is only one dependency path affected?
- is there a zone, node pool, or cluster pattern?

### `incident_scratchpad`

Stores compact incident state:

- symptom
- time window
- known facts
- hypotheses
- evidence gathered
- rejected explanations
- pending questions
- proposed mitigations

This is critical for token efficiency. Codex should not repeatedly rediscover context from raw tools.

## Hypothesis Model

A hypothesis model is a structured way to represent possible explanations during troubleshooting.

It is not a machine-learning model. It is a reasoning model: a schema for claims, evidence, predictions, and confidence.

The point is to prevent Codex from producing plausible narratives that do not actually follow from the evidence.

### Minimal Schema

```yaml
hypothesis_id: H1
claim: "checkout-api latency is caused by payment-gateway timeout regression"
mechanism: "checkout-api waits on payment-gateway during authorization; payment-gateway p95 rose after deploy"
scope_prediction: "all checkout-api pods affected; requests requiring payment authorization affected most"
time_prediction: "latency increase starts shortly after payment-gateway deploy"
evidence_for:
  - "checkout-api timeout errors first seen at 09:17"
  - "payment-gateway p95 increased from 180ms to 2200ms at 09:15"
evidence_against:
  - "checkout-api CPU and memory normal"
missing_evidence:
  - "need payment-gateway deploy history"
  - "need error split by checkout operation"
next_test: "compare checkout-api latency for payment vs non-payment routes"
confidence: medium
status: active
```

### Required Properties

Each hypothesis should include:

- a specific mechanism
- predicted evidence
- evidence for
- evidence against
- missing evidence
- next discriminating query
- confidence level

If a hypothesis cannot produce a prediction, it is probably too vague.

Weak:

```text
The service is unhealthy.
```

Stronger:

```text
The service is timing out because its downstream payment dependency crossed the client timeout after a deploy at 09:15.
```

### Why This Matters

Troubleshooting often fails from premature narrative closure:

- a deploy happened, so the deploy is blamed
- logs mention timeouts, so the network is blamed
- pods restarted, so Kubernetes is blamed
- latency increased, so the service is blamed

The hypothesis model forces a higher bar:

- What mechanism links cause to symptom?
- What should be true if this is correct?
- What evidence would weaken it?
- What test separates it from alternatives?

## Minimal Troubleshooting Loop

1. Define symptom.
   - What is degraded?
   - Who is affected?
   - Since when?
   - What signal proves it?

2. Establish timeline.
   - First bad user-facing signal.
   - First internal anomaly.
   - Recent changes.
   - Alert sequence.

3. Map blast radius.
   - One service or many?
   - One route or all routes?
   - One tenant or all tenants?
   - One region, cluster, namespace, node pool, or version?

4. Generate competing hypotheses.
   - Include at least two plausible alternatives when evidence is thin.
   - Include "bad recent change" and "dependency degradation" as common but not automatic candidates.

5. Query to discriminate.
   - Prefer questions that separate explanations.
   - Avoid broad raw data pulls unless summaries fail.

6. Update incident scratchpad.
   - Record facts, interpretations, hypotheses, and rejected paths separately.

7. Propose action.
   - If user impact is active, mitigation comes before complete root cause.
   - Codex should identify safe candidate actions but not mutate production without approval.

## Token Efficiency Rules

The system should optimize for compact evidence, not maximal access.

Rules:

- Always use explicit time windows.
- Prefer deltas over absolute values.
- Prefer grouped signatures over raw logs.
- Prefer top changed metrics over full dashboards.
- Prefer service-level summaries before pod-level detail.
- Store incident state and reuse it.
- Keep one compact context packet per incident.
- Retrieve raw evidence only when needed to verify a specific claim.
- Use aliases and canonical service names to avoid repeated disambiguation.

Default incident context packet:

```yaml
incident:
  symptom: ""
  started_at: ""
  affected_surface: ""
service_context: {}
recent_changes: []
log_anomalies: []
metric_anomalies: []
k8s_health: {}
related_signals: []
hypotheses: []
open_questions: []
```

Target size: small enough to fit in a few thousand tokens.

## Missing Or Crucial Components

### Canonical Service Identity

If tools use different labels for the same service, Codex will waste tokens and make avoidable mistakes.

Needed:

- canonical names
- aliases
- mappings across logs, metrics, Kubernetes, repos, and deployment tools

### Change Correlation

Without recent changes, the system will over-focus on symptoms.

Needed:

- deploys
- config changes
- feature flags
- dependency changes
- infra events

### Baseline Comparison

Without baselines, Codex may treat normal noisy signals as incident evidence.

Needed:

- same time yesterday or last week
- previous healthy window
- rolling normal range
- per-service normal error signatures

### Dependency-Aware Blast Radius

Without dependency context, Codex may misattribute downstream symptoms to the first service inspected.

Needed:

- upstreams
- downstreams
- shared infrastructure
- route-level or operation-level splits where available

### Evidence Ledger

Without a hypothesis and evidence ledger, the conversation will drift.

Needed:

- facts
- interpretations
- hypotheses
- rejected explanations
- pending tests

### Tool Result Shaping

Raw logs and high-cardinality metrics are token traps.

Needed:

- server-side aggregation
- sampling
- count deltas
- first-seen timestamps
- stable JSON outputs
- drill-down only on demand

## Evaluation Plan

Use real incidents before building more tooling.

1. Pick 2-3 past incidents or near misses.
2. Reconstruct the evidence that actually mattered.
3. Run Codex with only the proposed summary tools.
4. Measure:
   - time to first useful hypothesis
   - number of tool calls
   - tokens consumed
   - false leads
   - whether the suggested mitigation was reasonable
   - whether the root-cause path matched reality
5. Add only the missing context that would have changed the outcome.

This avoids building a broad platform from imagined needs.

## Risks

### Plausible Narrative Risk

Codex may create coherent explanations from weak evidence. The hypothesis model is meant to counter this, but it will not eliminate the risk.

### Stale Context Risk

Even small knowledge bases can become stale. Prefer generated or frequently refreshed context over hand-maintained docs.

### Observability Bias

The system will favor what is easiest to observe. Missing traces, bad labels, or noisy logs may distort conclusions.

### Scope Creep

The system can easily become a generic incident automation platform. The initial scope should remain: better human-Codex troubleshooting, not autonomous remediation.

## Best Next Moves

1. Define the canonical `service` schema.
2. Build `get_service_context(service)`.
3. Build `get_recent_changes(service, window)`.
4. Build one compact log summarizer and one compact metric comparator.
5. Create the incident scratchpad schema.
6. Test against 2-3 historical incidents.

## Open Questions

- What is the authoritative source of service identity today?
- Are service names consistent across Kubernetes labels, ELK, VictoriaMetrics, and deployment tooling?
- Can deploy/config/feature-flag events be queried by service and time window?
- Are dependency relationships available from config, traces, service mesh data, or only from human knowledge?
- What production actions, if any, should Codex be allowed to suggest without approval?
- What token budget is acceptable per incident phase?
- What counts as a successful troubleshooting assist: faster mitigation, better root cause, fewer false leads, or better incident notes?


# SRE-Codex Incident Packet

## Purpose

The incident packet is the smallest useful context object for an engineer and Codex to troubleshoot together.

It should be generated from tools, not written manually during an incident. The packet should be compact enough to fit into the conversation without raw log dumps or full dashboard exports.

## Inputs

```yaml
service: ""
environment: ""
start_time: ""
end_time: ""
symptom: ""
```

## Output Shape

```yaml
incident:
  symptom: ""
  started_at: ""
  ended_at: ""
  affected_surface: ""
  user_impact: ""
  source_signal: ""

service:
  canonical_name: ""
  environment: ""
  cluster: ""
  namespace: ""
  runtime_kind: ""
  workload_name: ""
  owner: ""
  repo: ""
  current_version:
    image: ""
    deployed_at: ""
    config_hash: ""

recent_changes:
  service:
    - time: ""
      type: ""
      summary: ""
      actor: ""
  dependencies:
    - service: ""
      time: ""
      type: ""
      summary: ""
  infrastructure:
    - time: ""
      scope: ""
      summary: ""

k8s_health:
  desired_replicas: 0
  available_replicas: 0
  rollout_status: ""
  restarts:
    last_30m: 0
    last_2h: 0
    by_pod: []
  probe_failures:
    readiness: 0
    liveness: 0
  oom_kills: 0
  notable_events: []
  resource_pressure:
    cpu_throttling: ""
    memory_pressure: ""

metrics:
  baseline_window: ""
  request_rate:
    current: ""
    baseline: ""
    delta: ""
  error_rate:
    current: ""
    baseline: ""
    delta: ""
  latency:
    p50_delta: ""
    p95_delta: ""
    p99_delta: ""
  saturation:
    cpu: ""
    memory: ""
    queue_depth: ""
    connection_pool: ""
  notable_anomalies: []

logs:
  baseline_window: ""
  top_error_signatures:
    - signature: ""
      count: 0
      baseline_count: 0
      first_seen: ""
      last_seen: ""
      sample_request_ids: []
  representative_samples:
    - timestamp: ""
      level: ""
      message: ""
      request_id: ""

dependencies:
  upstream: []
  downstream: []
  anomalous_related_signals:
    - service: ""
      signal: ""
      first_seen: ""
      summary: ""

initial_hypotheses:
  - id: H1
    claim: ""
    mechanism: ""
    evidence_for: []
    evidence_against: []
    missing_evidence: []
    next_test: ""
    confidence: low

open_questions: []
recommended_next_queries: []
```

## Token Rules

- Default to counts, deltas, first-seen timestamps, and representative samples.
- Do not include raw logs unless a specific hypothesis needs them.
- Keep sample log lines to the smallest useful number.
- Prefer `top changed` over `all observed`.
- Include exact time windows in every section.
- Compare against a baseline window whenever possible.

## Minimum Viable Packet

For V0, implement only:

1. service identity
2. recent service changes
3. Kubernetes health summary
4. metric deltas for request rate, error rate, latency, CPU, memory
5. top log error signatures
6. initial open questions

Leave dependency anomalies for V1 unless dependency data is already easy to query.


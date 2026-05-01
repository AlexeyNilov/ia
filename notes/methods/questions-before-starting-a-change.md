# Questions Before Starting a Change

## Definition

This note is a pre-change framing method.

Its purpose is not to generate broad discussion. Its purpose is to stop weak projects, expose hidden assumptions, and make change proposals more testable before substantial time, political capital, or implementation effort is spent.

## Why It Matters

Many change efforts start with energy but weak framing. The common failure mode is not lack of ideas. It is starting from an under-specified problem, vague success criteria, ignored constraints, or social optimism about adoption.

A useful pre-change framework should help answer questions such as:

- is there a real problem here, or just irritation, fashion, or local preference?
- who benefits, who pays, and who can block?
- what are the realistic alternatives, including doing nothing?
- what evidence would tell us this is working or failing?

This matters in IA, software, and operations because many expensive mistakes happen before implementation:

- solving the wrong problem
- treating aspiration as scope
- ignoring maintenance and ownership
- underestimating adoption friction
- making irreversible changes without clear evidence

## Core Questions

### 1. Problem

- What problem are we trying to solve?
- Who experiences it, and how badly?
- What evidence says this problem is real and worth solving now?

### 2. Scope

- What exactly will change?
- What will explicitly not change?
- What constraints limit the solution space?

### 3. Stakeholders

- Who benefits if this works?
- Who bears cost, risk, or extra work?
- Who must agree, and who can block or quietly resist?

### 4. Options

- What are the credible alternatives, including doing nothing?
- What has been tried before here or elsewhere, and what happened?
- Why is this option better under current constraints?

### 5. Execution

- What capabilities, time, and dependencies are required?
- Who will own delivery?
- Who will own maintenance after the initial change?
- If this goes badly, how reversible is it?

### 6. Evidence

- What outcome would count as success?
- How will we measure it?
- What result would tell us to stop, rethink, or roll back?

## Practical Heuristic

A pre-change proposal is weak if it cannot answer most of the following plainly:

- the problem is evidenced rather than asserted
- the scope has boundaries rather than only a vision
- the alternatives were considered rather than skipped
- the costs are assigned rather than abstract
- the success criteria are measurable rather than rhetorical
- the rollback path is known rather than assumed

If the proposal sounds persuasive but remains vague on these points, it is probably not ready.

## Common Failure Modes

- Replacing a problem statement with a preferred solution
- Smuggling in "why now" as if urgency were self-evident
- Treating stakeholder comfort as equivalent to stakeholder value
- Assuming prior attempts failed because others were careless rather than constrained
- Asking how to communicate the change before clarifying whether the change is sound
- Defining success in terms of shipping rather than improved outcomes

## Related Concepts

- Decision records: useful once the chosen direction is clear enough to record
- Project charters: often broader and more organizationally formal
- Discovery questions: overlap strongly, especially around users, evidence, and alternatives
- Runbook thinking: useful for forcing clarity about ownership, reversibility, and operational reality

## Open Questions

- Should this framework be used as a universal gate, or only for changes above some threshold of cost, risk, or irreversibility?
- Which question is most often skipped in real organizations: alternatives, constraints, or ownership?
- Does this repo need a lighter version for small reversible changes and a stricter version for strategic bets?

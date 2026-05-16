# IA Thinking Flash Cards

Use these as daily diagnostic drills. The point is not to memorize definitions, but to train faster recognition of structural weaknesses in information environments.

## 1. Actual Entry Point

Front:
Could the intended user find this from their real entry point?

Back:
What to inspect:
- Alert links
- Search terms
- Service catalog paths
- Repo navigation
- Incident channel links
- Team wiki structure

Failure mode:
The artifact exists, but only people who already know where it lives can use it.

Apply:
Pick one artifact and try to reach it from the place a user would actually start.

## 2. Trust Under Pressure

Front:
What would make this artifact untrustworthy during an incident?

Back:
What to inspect:
- Missing owner
- Missing review date
- Broken links
- Untested steps
- Contradictory artifacts
- No status or freshness signal

Failure mode:
Responders waste time deciding whether the artifact can be believed.

Apply:
Inspect one runbook or dashboard link chain for trust signals.

## 3. Duplicate Truth

Front:
Is there duplicate truth here?

Back:
What to inspect:
- Multiple docs answering the same question
- Conflicting owners
- No canonical source marker
- Stale pages without supersession links
- Search results that look equally authoritative

Failure mode:
Users must judge which source is real, often under weak evidence.

Apply:
Search for one important service or process term and compare the top results.

## 4. Hidden Prerequisites

Front:
What does this artifact assume the user already knows?

Back:
What to inspect:
- Local jargon
- Unexplained system names
- Missing prerequisites
- Implicit permissions
- Assumed command-line context
- Unstated operational risk

Failure mode:
The artifact works for insiders but fails for new responders or cross-team users.

Apply:
Read one doc as if you joined the team last week.

## 5. User, Channel, Context, Action

Front:
Who is acting, through what surface, under what conditions, toward what decision?

Back:
What to inspect:
- Specific user role
- Actual access channel
- Time pressure or uncertainty
- Required decision
- Cost of a wrong action
- Missing context for that decision

Failure mode:
The artifact is clear in isolation but mismatched to the real use situation.

Apply:
Rewrite the purpose of one artifact using this sentence shape.

## 6. Ownership

Front:
Can a user tell who owns this information and who can change it?

Back:
What to inspect:
- Named owner
- Owning team
- Escalation path
- Last reviewer
- Approval authority
- Maintenance responsibility

Failure mode:
Information decays because accountability is implied rather than assigned.

Apply:
Find one important artifact with unclear ownership and name what is missing.

## 7. Semantic Drift

Front:
Has a key term changed meaning across teams, tools, or time?

Back:
What to inspect:
- Same term used differently
- Different terms for the same thing
- Old names in dashboards or alerts
- Code names versus product names
- Migration-era aliases

Failure mode:
People appear to agree while reasoning about different objects.

Apply:
Choose one service, domain term, or process name and trace its variants.

## 8. Boundary Clarity

Front:
Where does this information space draw its boundaries?

Back:
What to inspect:
- What belongs here
- What belongs elsewhere
- Adjacent concepts
- Cross-links
- Ownership handoffs
- Explicit exclusions

Failure mode:
The structure grows by accumulation until categories stop discriminating.

Apply:
Pick one folder, doc set, or catalog area and state its inclusion rule.

## 9. Reasoning Support

Front:
What inference does this structure make cheaper?

Back:
What to inspect:
- Dependency reasoning
- Ownership reasoning
- Risk reasoning
- State transition reasoning
- Recovery reasoning
- Decision comparison

Failure mode:
The artifact organizes content but does not help anyone think better.

Apply:
Name the single most important question one artifact should help answer.

## 10. Actionability

Front:
What action should become easier after using this artifact?

Back:
What to inspect:
- Decision point
- Next step
- Escalation rule
- Rollback path
- Owner contact
- Evidence required before acting

Failure mode:
The artifact explains the topic but leaves the user unable to move.

Apply:
Open one explanatory doc and identify the action it should support.

## 11. Staleness

Front:
How would a user know whether this is still current?

Back:
What to inspect:
- Last reviewed date
- Review cadence
- Version marker
- Supersession link
- Active owner
- Connection to current systems

Failure mode:
Users silently discount the entire information environment.

Apply:
Find one artifact older than six months and check whether age changes trust.

## 12. Labeled Relationships

Front:
Do the relationships say what kind of relationship they are?

Back:
What to inspect:
- Arrows labeled with specific verbs
- Links with context
- Dependencies distinguished from ownership
- Causality distinguished from sequence
- Similar objects distinguished by role

Failure mode:
Boxes and links create false clarity while hiding the real claim.

Apply:
Review one diagram or link-heavy page and label one ambiguous relationship.

## 13. Searchability

Front:
Would a user know what to search for before they already understand the system?

Back:
What to inspect:
- Synonyms
- Old names
- Common abbreviations
- User-facing versus internal terms
- Error messages
- Alert names

Failure mode:
Search works only for users who already know the local vocabulary.

Apply:
Try searching with the terms a new user or responder would probably use.

## 14. Canonicality

Front:
Can users distinguish canonical information from commentary, history, or drafts?

Back:
What to inspect:
- Status labels
- Draft markers
- Decision record links
- Archived pages
- Superseded content
- Source-of-truth language

Failure mode:
Old thinking competes with current guidance.

Apply:
Inspect one doc cluster and mark which artifact should be canonical.

## 15. Cognitive Load

Front:
How much must the user hold in their head to use this?

Back:
What to inspect:
- Number of open tabs
- Similar choices
- Missing discriminators
- Long prerequisite chains
- Unexplained exceptions
- Context split across tools

Failure mode:
The artifact is technically complete but operationally exhausting.

Apply:
Count how many artifacts are needed to answer one practical question.

## 16. Incident Path

Front:
Can a responder move from alert to useful action without detours?

Back:
What to inspect:
- Alert-to-runbook link
- Runbook-to-dashboard link
- Dashboard-to-owner link
- Escalation path
- Known mitigations
- Customer impact indicators

Failure mode:
Incident response depends on memory, bookmarks, or asking the right person.

Apply:
Follow one alert path as if you were the secondary on-call.

## 17. Maintenance Rule

Front:
What keeps this structure true after reality changes?

Back:
What to inspect:
- Update trigger
- Review owner
- Lifecycle rule
- Automation support
- Change checklist
- Deletion or archive process

Failure mode:
The IA is good on launch day and then slowly becomes misleading.

Apply:
Choose one artifact and identify the event that should force an update.

## 18. Local Versus Global Coherence

Front:
Does this make sense only inside one team, or across boundaries?

Back:
What to inspect:
- Team-specific naming
- Cross-team dependencies
- Shared concepts
- External users
- Translation points
- Incompatible local taxonomies

Failure mode:
Each area is coherent locally, but cross-boundary work becomes fragile.

Apply:
Pick one artifact and ask whether another team could use it without translation.

## 19. Negative Space

Front:
What important thing is missing from this structure?

Back:
What to inspect:
- Absent failure modes
- Missing owners
- Missing rejected alternatives
- Missing exceptions
- Missing non-goals
- Missing user contexts

Failure mode:
The artifact looks complete because the structure hides what it excludes.

Apply:
Add a "what this does not cover" note to one candidate artifact.

## 20. Evidence

Front:
What evidence says this IA artifact works?

Back:
What to inspect:
- Task success
- Time to find
- Incident usage
- Reduced duplicate questions
- Fewer contradictory docs
- Successful onboarding retrieval

Failure mode:
The team mistakes artifact existence for artifact effectiveness.

Apply:
Define one observable signal that would show a doc set is helping.

## 21. Decision Recoverability

Front:
Can someone recover why this decision was made?

Back:
What to inspect:
- Decision record
- Alternatives considered
- Constraints
- Tradeoffs
- Date and owner
- Supersession status

Failure mode:
Future maintainers inherit the shape but not the reasoning.

Apply:
Pick one current system behavior and try to find the decision behind it.

## 22. Operational Metadata

Front:
What metadata changes how this information should be interpreted?

Back:
What to inspect:
- Owner
- Freshness
- Status
- Environment
- Severity
- Scope
- Source

Failure mode:
Users read the content but miss the signals that determine trust and action.

Apply:
Review one service catalog entry for missing operational metadata.

## 23. Structure Versus Expression

Front:
Is the problem unclear writing or weak structure?

Back:
What to inspect:
- Bad labels
- Missing grouping logic
- Poor navigation
- Duplicate artifacts
- Missing relationships
- Unsupported decision paths

Failure mode:
The team edits sentences when the real problem is organization.

Apply:
For one confusing artifact, decide whether rewriting is enough.

## 24. False Coherence

Front:
Does this structure look tidy while hiding disagreement?

Back:
What to inspect:
- Unlabeled arrows
- Overloaded categories
- Missing edge cases
- Glossed-over ownership
- No open questions
- No disagreement record

Failure mode:
A polished artifact suppresses the conflicts it should expose.

Apply:
Find one diagram or framework and identify one unresolved tension it hides.

## 25. Progressive Elaboration

Front:
Does each layer preserve alignment with the core claim?

Back:
What to inspect:
- Governing purpose
- Derived sections
- Traceable details
- Drift between summary and body
- Unsupported subtopics
- Decorative complexity

Failure mode:
Expansion creates volume without coherence.

Apply:
Compare the first paragraph of one long doc with its detailed sections.

## 26. Deletion Pressure

Front:
What should be removed, merged, or archived?

Back:
What to inspect:
- Near-duplicate pages
- Obsolete dashboards
- Unused categories
- Dead links
- Historical pages without archive markers
- Artifacts no longer tied to decisions

Failure mode:
The information environment only accumulates, so users stop trusting navigation.

Apply:
Identify one artifact that should be deleted, merged, or clearly archived.

## 27. Reviewability

Front:
Can this structure be reviewed with clear criteria?

Back:
What to inspect:
- Explicit purpose
- Target user
- Success condition
- Scope boundary
- Naming rule
- Maintenance rule

Failure mode:
Review becomes taste, preference, or seniority rather than testable critique.

Apply:
Turn one vague review comment into a concrete IA criterion.

## 28. Failure Mode Mapping

Front:
What failure mode does this IA choice prevent?

Back:
What to inspect:
- Unfindability
- Misrouting
- Wrong action
- Stale guidance
- Semantic confusion
- Lost rationale

Failure mode:
The IA choice is defended as "clean" without a clear operational purpose.

Apply:
For one naming, grouping, or metadata choice, name the failure it reduces.

## 29. Incentives

Front:
Do local incentives support or damage the global information environment?

Back:
What to inspect:
- Easy page creation
- Weak deletion norms
- Team-local templates
- No reward for maintenance
- Publish pressure
- No ownership for shared structures

Failure mode:
Locally rational contributions create global incoherence.

Apply:
Find one information problem that is probably incentive-driven, not skill-driven.

## 30. Reasonable User Test

Front:
Would a reasonable user fail here through no fault of their own?

Back:
What to inspect:
- Ambiguous labels
- Missing entry points
- Hidden assumptions
- Competing sources
- Weak trust signals
- Excessive context required

Failure mode:
The system blames users for failures caused by poor information architecture.

Apply:
Pick one recent repeated question and ask what structure made it likely.

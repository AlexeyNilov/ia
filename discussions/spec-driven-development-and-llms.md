"I feel there is a change happening from normal software development to spec driven. Earlier there were ideas like TDD and DDD but they were not popular before of the overhead. I believe LLMs and coding agent can reduce that overhead significantly and SDD/DDD will become more popular. The code itself will become easily replaceable almost disposible. What do you think?"

The crux: I think you’re directionally right about the *economics* changing, but parts of your conclusion are too broad.

LLMs do reduce the cost of writing and rewriting code, and that makes heavier upfront articulation more attractive: specs, acceptance criteria, domain models, invariants, interface contracts, decision records. That probably does shift some teams toward a more spec-driven style, just as it lowers the friction that made TDD/DDD feel expensive. But “spec-driven” is doing too much work here. Most teams will not suddenly become rigorous about specifications. They will more likely become better at producing *plausible-looking pseudo-specs*, unless they also improve review, test oracles, and operational feedback.

A stronger version of your claim is this: code generation gets cheaper, so the scarce resource moves upward to problem framing, boundary definition, and validation. That does make some DDD-like and spec-like practices more valuable. If an agent can cheaply implement variants, then the hard part becomes: what are the domain terms, what behavior is actually required, what constraints are non-negotiable, and how do we detect when the implementation is wrong? In that world, code is more replaceable than before. But “disposable” is only true for the parts whose value is mostly transcription. A lot of production code is not valuable because typing it was hard; it is valuable because it encodes learned constraints, ugly edge cases, incident scars, and integration knowledge. That does not become disposable just because regeneration is cheap.

What holds up:
- Boilerplate and glue code become cheaper and more replaceable.
- Precise specs, tests, schemas, and contracts become more leveraged.
- DDD gets more practical where it already had a real fit: complex domains, messy boundaries, lots of language drift.
- TDD changes shape: less “test first as discipline,” more “tests/specs as executable constraint system for agents.”

Why it might be wrong:
- Many teams do not have the discipline to write good specs, and LLMs can mask that by generating convincing noise.
- DDD was never mainly blocked by typing overhead; it was often blocked by organizational ambiguity, weak product understanding, and unclear ownership.
- If code becomes cheaper, teams may actually produce more accidental complexity, not less, unless review standards rise.
- Replaceability depends on architecture. If boundaries are weak, regenerated code just reintroduces the same coupling in a fresh form.

The best analogy is not "code becomes disposable", but "code becomes less authoritative". The authoritative artifacts move toward:
- domain language
- contracts
- tests and evals
- runbooks and operational constraints
- architecture decisions
- observable behavior in production

That should sound familiar from an SRE angle. In operations, the script is rarely the system of record; the real system is the contract between intent, telemetry, failure modes, and operator expectations. I think software delivery is moving the same way. Generated code may be ephemeral, but the service boundary, SLO implications, rollback behavior, data semantics, and incident learnings are not.

Best judgment: yes, agentic coding likely increases the relative value of spec-driven and domain-driven practices. But not because those practices become fashionable. Because implementation gets commoditized faster than validation and meaning do. The winning teams will not be the ones with the most generated code; they’ll be the ones with the clearest constraints and the best mechanisms for proving that generated code actually satisfies them.

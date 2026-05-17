# Chapter 02: Messes Are Made of Information and People

Source: `books/mess/02_messes_are_made_of_information_and_people.md`

## Crux

The chapter argues that "messes" are not mainly caused by technology or content volume. They emerge from how people arrange, interpret, and negotiate information.

Information architecture is framed as the practice of making those arrangements explicit enough that people can act.

## Key Information

- A mess is a confusing or difficult situation, often involving teams, processes, products, services, or communication.
- The first move is not solving the mess, but making its boundaries visible: its "edges and depths."
- Information architecture is defined broadly: arranging the parts of something so it becomes understandable.
- IA is not limited to websites or apps. Examples include dictionaries, menus, airport signage, software categories, labels, and navigation.
- Confusing information usually comes from too much information, not enough information, not the right information, or some combination.
- Information messes are human-made. Even delegated or automated structures reflect human architectural choices.
- Information is treated as a workable material, but not as an object.
- The chapter distinguishes:
  - `content`: the things arranged
  - `data`: facts, observations, and questions about those things
  - `information`: what a user interprets from the arrangement
- Absence can inform as much as presence. An empty shelf may imply "sold out," "popular," or something else.
- Architecture and content jointly shape interpretation. Same content, different structure, different meaning.
- Users and stakeholders are complex because they interpret differently, carry preferences, and may disagree about what the mess even is.
- Knowing is insufficient. Over-analysis can preserve the mess. IA requires action under uncertainty.
- The chapter ends with a diagnostic exercise: identify users, stakeholders, interpretations, missing/extra/wrong information, and then draw the mess.

## Train of Thought

1. Messes are common, uncomfortable, and hard to name.
2. Naming and illuminating a mess reduces paralysis because it gives the work boundaries.
3. IA is the discipline of arranging things for understanding.
4. IA is ancient and ordinary, not just digital-era web design.
5. Most information confusion has a small set of recurring causes.
6. Since people create arrangements, people are responsible for information messes.
7. Complexity is unavoidable because people, systems, connections, and interpretations vary.
8. Knowledge itself is unstable or socially negotiated enough that shared meaning must be worked out.
9. Information is not the arranged object; it is the user's interpretation of the arrangement.
10. Therefore, IA is less about "making information" and more about shaping conditions for interpretation.
11. Because users and stakeholders interpret differently, IA work is also social and political work.
12. The practical response is inquiry plus action: ask better questions, expose assumptions, and start mapping.

## What Holds Up

The strongest idea is the separation between `content`, `data`, and `information`. That distinction is useful for real systems work: a runbook, alert, dashboard, taxonomy, or service catalog does not contain its operational meaning automatically. Operators infer meaning from naming, placement, gaps, defaults, ownership signals, and surrounding context.

The chapter also correctly treats stakeholders as part of the architecture problem. In engineering terms, a confusing API, ownership model, incident taxonomy, or platform UI is rarely just a content problem. It often reflects competing mental models and unresolved authority boundaries.

## Weak Spots

"Every single thing in the universe is complex" is rhetorically useful but too broad to do much analytical work. A stronger version would distinguish intrinsic complexity, organizational complexity, semantic ambiguity, and coordination cost.

The "knowledge is subjective" section risks conflating truth, belief, consensus, and interpretation. The useful claim is not that truth varies. The stronger claim is that people act on interpretations, and shared operational truth often requires negotiated definitions, evidence, and context.

"We can't actually make information; users do" is mostly right as a corrective, but too absolute. Designers and architects can shape interpretation probabilistically through constraints, defaults, labels, ordering, and feedback loops. They cannot fully control meaning, but they are not passive either.

## Follow-Up Note Seed

Working claim:

> Information architecture is the design of interpretive conditions, not just the organization of content.

This deserves a durable note because it connects the chapter's core distinction to operational systems. In service ownership, incident review artifacts, runbooks, dashboards, platform navigation, and API design, the real failure is often not missing content. It is mismatched interpretation.

Useful angles to develop:

- How naming, placement, defaults, and omission create operational meaning.
- How dashboards and alerts become misleading when their interpretive context is implicit.
- How service catalogs and ownership models fail when they encode stakeholder compromise instead of actual responsibility.
- How post-incident reviews can separate `data`, `content`, and `information` to avoid false clarity.
- How platform UX should be judged by whether users form the right operational interpretation at the right time.

Open questions:

- What evidence shows that a given IA structure is producing the intended interpretation?
- Where do we currently mistake documentation volume for interpretive clarity?
- Which operational artifacts most often create false confidence because their architecture implies more certainty than the data supports?

# Chapter 03: Intent Is Language

Source: `books/mess/03_intent_is_language.md`

## Crux

The chapter argues that intent is not an abstract internal state; it becomes actionable through language. The words used to define intent constrain what counts as good, what options remain available, and how users and stakeholders interpret the work.

The strongest useful claim: defining intent is a design control surface. If a team does not define "good" in language that users and stakeholders can share, decisions drift toward taste, aesthetics, authority, or momentum.

## Key Information

- Intent is defined as the effect we want to have on something.
- Language choices shape available decisions. Choosing one descriptor means walking away from others.
- Words are planning tools: they turn vague ideas into actionable constraints.
- "Good" is contextual. What is good for one audience, business stage, or use case may be bad for another.
- Perception is subjective, so terms like `good`, `bad`, `beautiful`, `sleek`, or `useful` need situational definition.
- Looking good and being good are separate concerns. A polished thing can still fail its purpose.
- Miscommunication happens because meaning is filtered through perception and social context.
- Intent must be evaluated against the people who matter: users, stakeholders, colleagues, customers, clients, or anyone affected by the process.
- The chapter uses a `why -> what -> how` frame:
  - `why`: reason the work matters
  - `what`: the change or outcome being pursued
  - `how`: possible ways to achieve the intent
- The author warns that jumping to `how` before clarifying `why` and `what` can produce solutions to the wrong problem.
- Why, what, and how are interrelated rather than strictly linear.
- The practical exercise: choose adjectives users should use to describe the thing, then choose adjectives you are comfortable not having them use.

## Train of Thought

1. Intent depends on language because intent must be expressed before it can guide decisions.
2. Word choices create tradeoffs: naming a desired quality excludes or deprioritizes other qualities.
3. Because words shape plans, vague or conflicting language creates confused work.
4. Terms like "good" and "bad" are not universal; they depend on audience, context, and purpose.
5. Therefore, teams must define what "good" means for their users and stakeholders.
6. Visual appeal is not enough because beauty and usefulness can diverge.
7. Miscommunication is predictable because people interpret messages differently.
8. So intent must be framed around the people whose interpretations matter.
9. Clarifying `why` gives the work a reason and helps people understand their responsibilities.
10. Clarifying `what` prevents premature solutioning.
11. Exploring `how` expands options while keeping them tied to intent.
12. Since why, what, and how influence each other, teams should revisit them continuously.
13. The chapter operationalizes this through adjective selection: define desired interpretation and acceptable non-goals.

## What Holds Up

The best idea is that language acts as a constraint system. In engineering terms, adjectives like "simple," "secure," "fast," "friendly," or "enterprise-grade" are not harmless branding words. They imply architecture, UX, support burden, observability needs, and tradeoffs.

The chapter is also right that undefined "good" gets filled in by power, taste, or local incentives. That maps cleanly to product and platform work: if "good developer experience" is undefined, one team means speed, another means guardrails, another means autonomy, and another means fewer tickets.

The Karen example is useful because it shows a common organizational failure: leadership uses an aesthetic label like "sleek," research suggests users may interpret it as "cold," and the real work is not arguing taste but defining the intended user interpretation.

## Weak Spots

The subjectivity argument is directionally useful but loose. "Neither side is right" about Las Vegas carpets is too broad. A sharper version: each side is optimizing against a different criterion. Casino owners may be right relative to durability and customer association; designers may be right relative to another aesthetic standard.

The chapter sometimes treats language as if clarity alone resolves conflict. It does not. Clear intent can reveal incompatible goals rather than reconcile them. That is still progress, but it is not consensus.

"Start with why" is useful but can become slogan-grade unless tied to decision criteria. A stronger operational version would ask: what decisions should this `why` change, and what options should it rule out?

## Follow-Up Note Seed

Working claim:

> Intent becomes operational only when language defines tradeoffs clearly enough to guide decisions.

Why it matters:

This connects IA to engineering practice. Architecture principles, service ownership models, incident severity definitions, runbook quality bars, and platform UX goals all fail when their key adjectives are undefined.

Useful angles:

- How vague adjectives like "simple," "reliable," "secure," or "intuitive" hide unresolved tradeoffs.
- How architecture decision records can force intent into testable language.
- How incident severity definitions encode organizational intent.
- How platform teams should define desired user interpretation, not just feature behavior.
- How "looking good versus being good" applies to dashboards, docs, and internal tools.

Open questions:

- What evidence shows that users interpret the work as intended?
- Which key adjectives in a system or product are currently undefined?
- What decisions would change if the team made its intent explicit?
- Where is aesthetic polish masking poor operational usefulness?

# Chapter 04: By Facing Reality, We Can Find Solutions

Source: `books/mess/04_by_facing_reality_we_can_find_solutions.md`

## Crux

The chapter argues that sensemaking requires confronting the actual situation before proposing solutions. Reality includes players, channels, contexts, constraints, mental models, and existing structures. Diagrams and maps are tools for making that reality discussable.

The strongest useful claim: shared objects let teams compare mental models. Without an external representation, people can appear aligned while privately reasoning from different maps.

## Key Information

- Facing reality means moving from pondering to acting, making, testing, and potentially failing.
- Reality includes multiple player types: current users, potential users, stakeholders, competitors, and distractors.
- People can occupy multiple roles, creating conflicts and bad assumptions.
- Channels transmit information. Context is the user's situation, including place, task, mood, constraints, and surrounding conditions.
- One channel can support many contexts, and one context can involve many channels.
- Existing patterns and off-the-shelf solutions can fail when their hidden assumptions do not match the current context.
- Mental models are internal maps. Diagrams, prototypes, lists, and maps externalize those models so people can compare them.
- Before diagramming, define:
  - `scope`: the purpose and boundaries of the diagram
  - `scale`: the relative size or level of detail
  - `timescale`: then, now, or future state
- Diagrams have rhetorical purposes: reflection, options, improvements, identification, and planning.
- Architecture should precede design. Boxes, arrows, and decision diamonds should stay pliable before polish hardens the conversation.
- Diagrams must be tidy enough to be credible but flexible enough to invite change.
- The chapter introduces common diagram types: block, flow, Gantt, quadrant, Venn, swim lane, hierarchy, mind map, schematic, and journey map.
- The closing exercise recommends a matrix of users, contexts, players, and channels.

## Train of Thought

1. Messes become solvable only when people stop abstract worrying and inspect reality.
2. Reality is emotionally difficult because it can expose fear, failure, constraints, and prior misunderstanding.
3. The first layer of reality is social: who uses, influences, competes, distracts, or benefits.
4. The second layer is situational: channels and contexts shape how information is encountered.
5. Since contexts and channels intersect, copying existing patterns can import the wrong assumptions.
6. People reason from private mental models, so verbal discussion alone is too weak.
7. External objects make mental models visible and comparable.
8. To make useful objects, define scope, scale, and timescale.
9. Diagrams are rhetorical tools, not neutral artifacts; they are made to reflect, propose, improve, identify, or plan.
10. Start structurally and keep representations easy to change.
11. Use the right diagram type for the part of the mess being examined.
12. A matrix can turn vague reality into a set of questions or tasks to fill.

## What Holds Up

The best idea is that diagrams are coordination artifacts, not deliverables. This maps directly to architecture reviews, incident retrospectives, service maps, dependency diagrams, and ownership models. The value is not the picture; it is the shared correction of mental models.

The warning against copying existing patterns is also strong. In engineering terms, reusing another team's taxonomy, workflow, platform pattern, or dashboard can carry hidden assumptions about users, scale, failure modes, and incentives.

The scope, scale, and timescale distinction is especially useful. Many bad diagrams fail because they mix current and future state, local workflow and ecosystem view, or conceptual model and implementation detail.

## Weak Spots

The chapter's list of "players" is useful but incomplete. It underplays regulators, maintainers, operators, vendors, downstream teams, and future users. In operational systems, these absent players often determine whether the map survives reality.

The diagram catalog is broad but shallow. It names tools without strong selection criteria. A more rigorous version would ask what question the diagram must answer and what decision it should change.

"Reality" is doing a lot of work as a word. The chapter means at least constraints, user behavior, social interests, channel conditions, and current-state architecture. Those should not be collapsed.

## Follow-Up Note Seed

Working claim:

> Diagrams are useful when they expose mismatched mental models, not when they merely document what one person already believes.

Why it matters:

This connects IA to operational practice. Dependency maps, incident timelines, service catalogs, escalation paths, and platform journey maps are valuable only if they help teams confront reality together.

Useful angles:

- How architecture diagrams hide or reveal ownership gaps.
- How incident timelines compare mental models of causality.
- How current-state maps prevent premature solutioning.
- How scope, scale, and timescale should be explicit in technical diagrams.
- How diagram polish can suppress useful disagreement.

Open questions:

- What decision is a given diagram supposed to improve?
- Whose mental model is missing from the map?
- Does the diagram show current state, desired state, or a confused blend?
- What hidden assumptions came from copying an existing pattern?

# Chapter 05: Moving From Why to What

Source: `books/mess/05_moving_from_why_to_what.md`

## Crux

The chapter argues that moving from intent to action requires choosing the level of the system being changed and clarifying the language used to describe it. Direction depends on scale, ontology, vocabulary, requirements, and realistic constraints.

The strongest useful claim: language is not documentation after the fact. It is part of the architecture because it defines the objects, actions, relationships, and requirements people use to coordinate work.

## Key Information

- After facing reality, the next challenge is moving from why something should change to what can be done.
- Work happens at multiple levels:
  - `object`: a specific thing
  - `interface`: where a user affects the thing
  - `location`: a place or position
  - `journey`: steps in or between locations
  - `structure`: configuration of objects and locations
  - `system`: structures working together
  - `ecosystem`: related systems
- Changes at one level affect other levels. Tiny decisions can create broad disruptions.
- Placemaking arranges spaces so people know what to do there.
- Users will find spaces between intended places; these reveal unmet needs or behavior in flux.
- Shared language is required for collaboration. Undefined or overloaded terms create friction.
- `Linguistic insecurity` is the fear that one's language will not conform to the expected standard or context.
- `Ontology` is deciding that a word or concept has a specific meaning in a specific context.
- Controlled vocabularies reduce insecurity by defining terms, synonyms, variants, acronyms, tone, and insider or outsider language.
- A "don't say" list can be as important as an approved vocabulary because it prevents misaligned or confusing terms.
- Defining terms for outsiders exposes nested assumptions.
- Nouns represent objects, people, and places; verbs represent actions.
- Combining nouns and verbs produces requirements.
- Strong requirements describe desired results without prematurely specifying implementation.
- Teams must distinguish requirements from options and opinions.

## Train of Thought

1. Understanding why change matters does not automatically reveal what to do.
2. To choose a direction, identify the level of work: object, interface, location, journey, structure, system, or ecosystem.
3. Because levels affect each other, local changes can create system-wide consequences.
4. Places are made through arrangements and clues that shape user behavior.
5. Users also create informal spaces between designed places, exposing gaps in the intended structure.
6. Direction depends on language because collaboration depends on shared terms.
7. Ambiguous terms and jargon create insecurity and misunderstanding.
8. Ontology makes contextual meanings explicit.
9. Controlled vocabularies stabilize the words a group uses and avoids.
10. Definitions should be tested with outsiders and informed by history, myths, and alternatives.
11. Nouns and verbs turn language into concrete requirements.
12. Requirements must avoid smuggling in interface choices, interaction patterns, or vague quality claims.
13. Choosing a direction requires balancing research, stakeholder views, instinct, limits, and realistic capacity.

## What Holds Up

The level model is useful because it prevents scope confusion. Many engineering arguments fail because one person is discussing an interface, another is discussing a system, and another is discussing an ecosystem.

The noun and verb framing is strong. It resembles domain modeling and API design: identify entities, actors, actions, permissions, and resulting requirements before jumping to UI or implementation.

The warning about weak requirements is directly applicable to technical planning. "The user can easily publish with one click" mixes a desired outcome, UI prescription, and unmeasured quality claim. That is not a requirement; it is a bundle of assumptions.

## Weak Spots

"There is only your way" is rhetorically dangerous. A stronger claim would be: there is no context-free right way, but some choices are better supported by evidence, constraints, and intent than others.

The chapter usefully distinguishes ontology from lexicography, but it could go further. Ontology is not just choosing definitions; it also creates boundaries, permissions, workflows, and power relationships.

The advice to design with users and stakeholders is sound, but it underplays conflict resolution. Shared vocabulary can reveal disagreement without resolving it.

## Follow-Up Note Seed

Working claim:

> Requirements become clearer when teams model nouns, verbs, and levels before choosing interfaces or implementation details.

Why it matters:

This connects IA to domain-driven design, API review, platform UX, and service ownership. Confusion often starts when teams argue about solutions before agreeing on objects, actions, scope, and vocabulary.

Useful angles:

- How overloaded nouns create bad service boundaries.
- How verbs reveal permissions, workflows, and operational responsibilities.
- How "easy" and "simple" smuggle untested quality claims into requirements.
- How controlled vocabularies reduce support burden and onboarding friction.
- How informal user paths expose missing architecture.

Open questions:

- Which terms in the current domain have multiple meanings across teams?
- Which requirements prescribe implementation too early?
- What level is the work actually trying to change?
- Which user-created "spaces between places" should become supported paths?

# Chapter 06: There's Distance Between Reality and Your Intent

Source: `books/mess/06_theres_distance_between_reality_and_intent.md`

## Crux

The chapter argues that intent becomes manageable only when broken into specific goals, baselines, progress measures, indicators, flags, and measurement rhythms. The distance between current reality and desired intent must be measured well enough to guide action.

The strongest useful claim: progress deserves measurement, not just success. Without baselines and indicators, teams mistake movement, activity, or local wins for meaningful progress.

## Key Information

- Intent alone does not get work done; goals focus time, energy, and measurement.
- A well-defined goal includes:
  - `intent`: the result wanted
  - `baseline`: reference point for comparison
  - `progress`: how movement toward or away from the goal is measured
- Goals change how people allocate time, resources, attention, and judgment.
- The distance between reality and intent may be measured in time, money, politics, talent, or technology.
- Dependencies are conditions that must exist before something else can happen.
- Indicators show whether movement is toward or away from intent.
- Common indicators include satisfaction, profit, loyalty, traffic, conversion, perception, complaints, backlash, expenses, debt, drop-off, waste, and murk.
- Worksheets can mine data from people when the data lives in heads, personal records, or distributed sources.
- Baselines measure current performance before change. Without baselines, assumptions dominate evaluation.
- Flags notify people when important indicator changes occur.
- Measurements need rhythm: moment to moment, daily, seasonal, yearly, or longer.
- Fuzzy measurement is normal. Incomplete data can still support direction if uncertainty is explicit.

## Train of Thought

1. Intent describes the desired future but does not determine action by itself.
2. Goals translate intent into specific things to do and measure.
3. Goals also shape what counts as success, waste, competition, and useful effort.
4. To set realistic goals, measure the distance between current reality and intent.
5. Progress depends on sequencing work and understanding dependencies.
6. The measurement chosen should reinforce the intent.
7. Indicators provide signals of movement toward or away from the goal.
8. Data may come from systems or from people, so worksheets can help extract distributed knowledge.
9. Baselines prevent misleading judgments about whether change helped.
10. Flags make measurement proactive by notifying people when something meaningful changes.
11. Measurement cadence should match the phenomenon and the decision it supports.
12. Even fuzzy measures can be useful if treated honestly.
13. The practical exercise is to revisit intent, define goals, imagine ideal measures, gather baselines, identify indicators, and set flags.

## What Holds Up

The baseline argument is strong. In engineering operations, nearly every improvement claim is weak without a baseline: alert quality, incident response, deployment speed, support load, platform adoption, documentation usefulness, and reliability work all need before-and-after reference points.

The distinction between indicators and flags maps cleanly to observability. Metrics are not enough; teams need thresholds, rhythms, alerts, reviews, and interpretation practices tied to intent.

The chapter's acceptance of fuzzy measures is pragmatic. Some important things, like trust, perceived clarity, or onboarding confidence, are hard to measure exactly but still worth tracking.

## Weak Spots

The indicator list mixes outcomes, inputs, perceptions, financial measures, risks, and competitive context without a taxonomy. That is fine for brainstorming, but a measurement model needs stronger grouping.

"Words like right and wrong are subjective" is too loose. Some goals are objectively inconsistent, harmful, or unsupported by evidence. The better claim is that evaluation criteria depend on intent and context.

The chapter does not spend enough time on metric distortion. Once indicators become targets, they can shape behavior in ways that undermine intent.

## Follow-Up Note Seed

Working claim:

> Goals are only operational when paired with baselines, indicators, flags, and a measurement rhythm.

Why it matters:

This connects IA to SRE practice. Service health, incident learning, platform adoption, runbook quality, and documentation clarity all require measures that show distance from intent, not just activity.

Useful angles:

- How baselines prevent fake improvement narratives.
- How indicators differ from flags in observability design.
- How measurement rhythm should match decision rhythm.
- How fuzzy measures can still guide platform and documentation work.
- How metrics become distorted when detached from intent.

Open questions:

- What baseline exists before a proposed IA or platform change?
- Which indicators would show movement away from intent?
- What should trigger attention before the goal fails?
- Which measurements incentivize the wrong behavior?

# Chapter 07: There Are Many Ways to Structure Things

Source: `books/mess/07_there_are_many_ways_to_structure_things.md`

## Crux

The chapter argues that structure is chosen, not discovered. To make information useful, teams must test multiple taxonomies against user needs, intent, goals, ambiguity, exactness, facets, and mental models.

The strongest useful claim: classification is harder than sorting. Sorting follows rules; classification creates the rules, and that is where assumptions, politics, and user mismatch enter.

## Key Information

- A structure is any configuration, including an unorganized pile.
- A good structure should make sense to users, reflect intent, and help reach goals.
- Testing "bad" or unlikely structures can reveal what the final structure should not be.
- `Taxonomy` is the method of organizing and classifying content to convey intended information.
- `Form` is the visual shape or configuration users actually experience.
- Most forms combine multiple taxonomies.
- `Sorting` arranges content according to established rules.
- `Classification` decides the rules for sorting.
- Classification can be exact or ambiguous.
- Ambiguity costs clarity; exactitude costs flexibility.
- Simple instructions can hide ambiguity, as in alphabetizing by first name, last name, artist, title, or another facet.
- `Facet` is a discrete piece of knowledge used to classify something.
- Human mental models often conflict with exact classification, as with tomatoes as fruit versus vegetable.
- Taxonomies express intent, worldview, culture, experience, and privilege.
- Taxonomies can be hierarchical, heterarchical, sequential, or bridged by hypertext.
- Most useful structures combine approaches, such as hierarchy, sequence, and hypertext.
- The closing exercise recommends sketching multiple structures with boxes and arrows before changing real materials.

## Train of Thought

1. Everything has structure, but not every structure serves users or intent.
2. Since many structures are possible, teams should compare alternatives instead of accepting the first arrangement.
3. Taxonomy is the practice of choosing organizing and classification methods.
4. Forms are experienced through combined taxonomies, not single structures.
5. Sorting is straightforward only after classification rules exist.
6. Classification is difficult because rules require agreement and often involve ambiguity.
7. Exact classification increases consistency but can reduce flexibility.
8. Ambiguous classification increases flexibility but requires more explanation and can reduce findability.
9. Facets provide different lenses for classification, but not every useful facet has available or affordable data.
10. Human mental models may override technically exact classifications.
11. Therefore, classification choices are rhetorical and cultural, not merely mechanical.
12. Different taxonomic patterns support different user experiences: hierarchy, heterarchy, sequence, and hypertext.
13. Most real systems need a mix of structures.
14. Teams should prototype and test structures before committing to them.

## What Holds Up

The classification versus sorting distinction is the chapter's best contribution. It explains why content cleanup, service catalogs, ownership registries, and tag migrations often look easy until the rules must be negotiated.

The ambiguity versus exactitude tradeoff is also durable. In operational systems, too much exactness can make categories brittle; too much ambiguity makes routing, ownership, and retrieval unreliable.

The tomato example is useful because it separates expert classification from user classification. In platform and operations contexts, technically correct categories can still be operationally wrong if users cannot act on them.

## Weak Spots

"Structure is rhetoric" is true but needs careful handling. It can imply manipulation, when the stronger claim is that structure always guides interpretation and therefore carries intent.

The chapter could more explicitly distinguish browse structures from retrieval structures. A taxonomy that helps exploration may fail search, reporting, permissions, or automation.

The treatment of facets should mention governance. Faceted classification depends on data quality, ownership, and update paths, not just conceptual usefulness.

## Follow-Up Note Seed

Working claim:

> Classification is where information architecture becomes organizational decision-making.

Why it matters:

This connects IA to service catalogs, incident taxonomies, alert routing, ownership models, API resources, and documentation systems. The hard part is not putting items in boxes; it is agreeing what the boxes mean and what consequences follow.

Useful angles:

- How classification rules encode ownership and accountability.
- How exactness and flexibility trade off in incident categories.
- How user mental models should constrain technically correct taxonomies.
- How facets depend on available, trusted, maintained data.
- How hypertext can bridge structures without duplicating content.

Open questions:

- Which classification rules are explicit versus assumed?
- What user task does each structure support?
- Where is the taxonomy technically correct but operationally unhelpful?
- Which facets are desirable but too expensive or unreliable to maintain?

# Chapter 08: Adjustments Are a Part of Reality

Source: `books/mess/08_adjustments_are_a_part_of_reality.md`

## Crux

The chapter argues that information architecture is iterative, collaborative, and mostly invisible when it works. Sensemaking requires adjustment as reality changes, because fixed plans, solo agreement, and facade-level fixes cannot produce durable clarity.

The strongest useful claim: IA must be under the floorboards. If structure and intent are not built into the underlying system, surface polish cannot carry the intended meaning.

## Key Information

- New insights appear as people move toward goals. Sensemakers must adjust course as new forces appear.
- Finalization is the wrong target. Refinement through feedback is the work.
- Progress is possible even though perfection is not.
- Individual artifacts, such as hierarchy diagrams, flows, and lexicons, must be evaluated together to understand the whole.
- Making diagrams alone is not practicing IA when the work affects other people.
- Teams should involve stakeholders early and prototype with users to test language and structure.
- Tension, fear, anxiety, and linguistic insecurity can block progress unless discussed directly.
- IA is compared to a building frame and foundation: not visible by itself, but foundational to the whole.
- Surface-level redesign cannot compensate for misaligned structure and intent.
- Stakeholders need direction, patterns, potential outcomes, and ways to frame solutions.
- Users need navigation, a sense of possibility, and intended meaning.
- IA is often noticed only when broken.
- Sensemaking includes removing grit: filtering ideas, clarifying intent, choosing direction, defining goals, and refining language and structure.
- The author's own book-writing story is used as an example of adjusting after a prototype failed its intended audience.
- The final checklist revisits mess boundaries, intent, reality, language, goals, structures, testing, and readiness to adjust.

## Train of Thought

1. Reality changes as soon as people begin acting and learning.
2. Because new insights emerge, plans must be adjustable.
3. Avoiding plans because they may change is procrastination; changing plans is part of the work.
4. Individual IA artifacts are only partial views, so teams must inspect the whole.
5. Agreement reached alone is weak because most IA work serves and involves other people.
6. Stakeholders and users should influence maps, diagrams, prototypes, language, and structure early.
7. Collaboration creates tension because people carry different mental models, language, fears, and goals.
8. Those tensions must be discussed until the shared direction is clear enough.
9. IA must be structural, not decorative.
10. The work serves both stakeholders and users, whose needs differ but overlap.
11. Because IA is invisible when healthy, it should be practiced for clarity rather than recognition.
12. Sensemakers act as filters, reducing confusion and turning ideas into something usable.
13. The author's own process demonstrates the book's method: face reality, adjust intent, test prototypes, refine language, and keep going.

## What Holds Up

The "under the floorboards" argument is strong. It explains why rebranding, redesigns, reorganized nav, or nicer dashboards fail when the underlying domain model, ownership, workflow, or language remains wrong.

The insistence on collaboration is also sound. In operational systems, solo-created maps often encode one person's perspective and miss how work actually crosses teams, tools, and failure modes.

The filter metaphor is useful if kept concrete: remove ambiguity, unsupported ideas, conflicting terms, stale assumptions, and unnecessary structure before users encounter them.

## Weak Spots

The chapter sometimes treats collaboration as the answer without naming decision authority. Discussion helps, but hard IA problems often require a final accountable decision after disagreement is understood.

"Good" is still underdefined. The chapter says continuous refinement assures something is good, but refinement can optimize toward the wrong criteria if goals and evidence are weak.

The plumbing analogy is effective but incomplete. IA is not only hidden infrastructure; in many systems, visible labels, navigation, and language are the operational interface to that infrastructure.

## Follow-Up Note Seed

Working claim:

> IA fails when teams treat structure as surface presentation instead of as operational infrastructure.

Why it matters:

This connects IA to platform engineering, service ownership, runbooks, dashboards, and incident systems. Cosmetic cleanup cannot fix broken responsibilities, domain boundaries, workflows, or interpretive signals.

Useful angles:

- How facade-level redesign hides unresolved domain problems.
- How shared maps and prototypes reveal cross-team mismatches.
- How IA health is usually noticed only through failure symptoms.
- How decision authority should work when collaborative IA exposes disagreement.
- How adjustment should be built into governance, not treated as churn.

Open questions:

- What structural problem is being mistaken for a presentation problem?
- Where has solo agreement replaced actual stakeholder or user validation?
- What feedback loop tells us when the architecture needs adjustment?
- Who has authority to decide when shared language or structure conflicts?

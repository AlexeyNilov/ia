# IA, DDD, and SRE: Brief Discussion Summary

## Context

Question: is information architecture (IA) a real discipline worth deeper study, or mostly common sense applied to communication?

User context: SRE tech lead with substantial coding, code review, and software architecture interests.

## Main Judgment

IA is not a hard science with strong universal laws. It is better understood as an applied discipline that draws from cognitive psychology, HCI, linguistics, library science, and usability research.

That makes the skeptical view partly correct: some IA is structured common sense. But that does not make it trivial. The value of IA is that it helps people make better structural decisions about naming, grouping, navigation, findability, and meaning in complex systems.

## What Holds Up

- IA has a real object of study: how information should be organized so people can find, understand, and use it.
- Much of its value appears "obvious" only after the structure has been improved.
- In operational environments, many problems that look like tooling or process issues are actually information architecture issues.

## Applicability to SRE

IA seems directly relevant to:

- runbooks and troubleshooting flows
- dashboard and observability design
- alert naming, grouping, and routing
- service ownership and metadata systems
- incident communication and handoff structure
- postmortems as institutional memory

Working conclusion: IA is worth studying for SRE leadership, but mainly as a practical companion discipline rather than a separate professional identity.

## IA and DDD

The perceived similarity between IA and domain-driven design (DDD) is real.

Useful parallels:

- DDD ubiquitous language and IA labeling
- bounded contexts and information spaces
- domain model clarity and taxonomy clarity
- context mapping and translation between information worlds

Important limit:

DDD is mainly about modeling domains so software behavior stays coherent. IA is mainly about helping humans find, interpret, and act on information. A clean domain model and a usable information structure often overlap, but they are not the same thing.

## Strongest Objection

Deeper IA research may have diminishing returns if the goal is only to become better at SRE leadership or software architecture. The likely payoff is in selective application, not in becoming an IA specialist.

## Current Best Bet

Treat IA as a companion lens for software architecture and SRE:

1. Use DDD to ask whether concepts and boundaries are modeled coherently.
2. Use IA to ask whether intended users can find the right thing, interpret it quickly, and act without hidden assumptions.

When those lenses produce different designs, that difference is informative.

## Suggested Next Note

Create a higher-level map comparing `IA vs DDD vs SRE operational design`, focused on where the lenses align and where they conflict.

---
name: extract-key-information
description: Extract key information, claims, assumptions, evidence, weak spots, open questions, and the source's argument flow or "train of thought" from notes, articles, book chapters, transcripts, discussions, research captures, or other source material. Use when Codex is asked to review, summarize rigorously, synthesize, distill, extract durable notes, identify reasoning structure, or prepare follow-up notes from a text or file.
---

# Extract Key Information

## Overview

Extract the source's substance and reasoning structure without flattening it into a generic summary. Treat "train of thought" as the author's or source material's observable argument flow, not as private model reasoning.

## Workflow

1. Read the source completely enough to understand its structure.
2. Identify the central claim or practical decision the source is trying to support.
3. Separate observations, interpretations, conclusions, assumptions, and recommendations.
4. Extract key information: definitions, distinctions, examples, causal claims, evidence, tensions, and action prompts.
5. Reconstruct the source's argument flow in order. Use concise numbered steps when the reasoning is sequential.
6. Evaluate what holds up, what is weak, and what evidence would change the judgment.
7. Produce a follow-up note seed when useful: a durable claim, why it matters, useful angles, and open questions.

## Output Shape

Prefer this structure unless the user asks for another format:

- `Crux`: 1-3 short paragraphs stating the core claim and why it matters.
- `Key Information`: concise bullets with the durable content.
- `Train of Thought`: numbered reconstruction of the source's reasoning path.
- `What Holds Up`: strongest claims, distinctions, or evidence.
- `Weak Spots`: overclaims, ambiguity, missing evidence, scope problems, or conflated concepts.
- `Follow-Up Note Seed`: a durable note candidate with open questions when the source merits future synthesis.

For short or simple sources, collapse sections to avoid ceremony. For dense sources, preserve the structure and add line or section references when available.

## Extraction Rules

- Do not merely paraphrase each paragraph. Extract the claims that would remain useful later.
- Do not turn speculative ideas into settled doctrine. Mark uncertainty clearly.
- Do not invent evidence, motives, or implications that are not grounded in the source.
- Do not overuse direct quotation. Quote only short phrases when exact wording matters.
- Preserve important definitions and distinctions, especially where the source separates terms that are often conflated.
- Name ambiguous words doing too much work.
- Look for missing base rates, missing alternatives, selection effects, incentives, confounders, and scope mismatch.
- Treat examples as evidence only when they actually support the claim. Otherwise identify them as illustrations.
- When the user asks to save the output, create or update the requested file using the repo's conventions.

## Review Stance

Lead with the crux. Be concise, concrete, and unsentimental. Prefer a sharper weaker claim over an impressive broad one.

If the source is an argument, include the strongest charitable reconstruction before criticism when that improves precision. If a claim is too vague to test, say so and propose a more rigorous version.

## Follow-Up Notes

When creating a follow-up note seed, include:

- `Working claim`: one falsifiable or at least contestable sentence.
- `Why it matters`: the practical or conceptual significance.
- `Useful angles`: 3-6 directions for later synthesis.
- `Open questions`: evidence gaps, unresolved tensions, or tests.

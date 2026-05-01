# Information Architecture Audit Application: Strategy & Framework

## 1. Critique of "How to Make Sense of Any Mess" (Abby Covert)
While Covert's book is an excellent entry point for human-centric IA, it lacks the technical precision required for enterprise-scale automated auditing.
* **Strengths:** Focuses on intent, accessibility, and the psychology of "meaning-making."
* **Weaknesses:** Ignores technical constraints, data modeling (one-to-many relationships), scalability, and formal standardization (controlled vocabularies).

## 2. Proposed IA Audit Application Concept
The goal is to build an application for large companies that validates disparate data sources (Wiki, Jira, Git) against a central "Source of Truth" (SoT) using LLMs.

### The Semantic Drift Audit Framework (LLM Logic)
1.  **Grounding & Ontology Extraction:** Ingest core data (glossaries, diagrams) to create a JSON schema of canonical definitions.
2.  **Metadata Enrichment:** Use the LLM to identify context (date, author, status) to weigh the authority of the document.
3.  **Gap Analysis (Validation):**
    * **Naming Conflicts:** Identify synonyms or mislabeled entities.
    * **Structural Conflicts:** Detect mismatches in architecture descriptions.
    * **Obsolescence:** Flag references to deprecated systems or legacy logic.
4.  **Categorization:** Label issues as Synonyms (low priority), Conflicts (high priority), or Orphans (undefined data).

## 3. Key Advanced IA Concepts for Design
To build this effectively, the following technical IA concepts are required:
* **Object-Oriented UX (OOUX):** Breaking information into Objects, Relationships, and Attributes to find commonality across systems.
* **Taxonomy vs. Ontology:** Moving from simple hierarchies to complex webs of "Subject -> Predicate -> Object" relationships.
* **Content Modeling:** Auditing content at the "chunk" level rather than the "page" level.

## 4. Recommended Technical Resources
* **"Information Architecture: For the Web and Beyond"** (The Polar Bear Book) - Rosenfeld et al.
* **"Everyday Information Architecture"** - Lisa Maria Marquis.
* **"Strategic Writing for UX"** - Torrey Podmajersky.

---
*Note: This strategy suggests a RAG (Retrieval-Augmented Generation) approach for the LLM to ensure it only validates against verified "Truths" rather than hallucinating standards.*

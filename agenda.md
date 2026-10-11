# Source Engineering -- Research Agenda

> The discipline's open questions, grouped by pillar and by layer. A question stays on the agenda until an experimental protocol closes it.

This document is a living list. Open questions are added as the discipline recognises gaps. Closed questions are moved to the bottom of their section with the protocol that closed them and a link to the finding.

## Open questions by pillar

### Pillar 1 -- Data Provenance

- **Q1.1.** How does a Source Engineering system surface provenance at the response level when the model itself cannot enumerate the rows of its training corpus that shaped a given answer? Current state: provenance is a property of the response (model cards, citations APIs) but not of the training data at the row level.
- **Q1.2.** What is the minimum metadata a COTS must carry for an external reviewer to reconstruct the provenance chain? Current state: the discipline assumes "every input that shaped an output" without specifying the metadata vocabulary.

### Pillar 2 -- Contextual Signature Mapping

- **Q2.1.** How does a Source Engineering system surface per-segment calibration drift to the operator without leaking segment identity to the user? Current state: per-segment drift is recognised as a problem; the privacy-preserving surface is not.
- **Q2.2.** What is the contract between the context-engineering layer (which sets the parameters) and the COTS layer (which surfaces them to the user)? Current state: the discipline assumes the parameters are surfaced; the contract that governs what "surfaced" means is not specified.

### Pillar 3 -- Chain of Evidence

- **Q3.1.** What is the minimum evidence-relationship vocabulary for a COTS to be inspectable? Current state: the discipline assumes "every decision links to supporting evidence" without specifying the relationship types (supports, contradicts, contextualises, etc.).
- **Q3.2.** How does a Source Engineering system handle the case where a decision's evidence is itself a model-generated artefact (a retrieval-augmented generation answer, an agent's tool call, a model's intermediate reasoning)? Current state: the discipline assumes the evidence is inspectable; recursive evidence chains are not addressed.

### Pillar 4 -- Explainability Anchoring

- **Q4.1.** How does a Source Engineering system surface the reasoning trace to the end user, not just the operator? Current state: traces are operator-facing (LangSmith, Langfuse, etc.); user-facing traces are a different product category.
- **Q4.2.** What is the user-facing visualisation of a COTS? Current state: the discipline assumes the COTS is inspectable; the visualisation is deferred.

### Pillar 5 -- Human Validation Points

- **Q5.1.** How does a Source Engineering system close the loop between user feedback and the model's next call, in the same session, at acceptable latency? Current state: feedback is collected but not returned as a runtime signal in the same session.
- **Q5.2.** What is the feedback surface that lets a user probe specific data points in the COTS, not just the overall response? Current state: evidence-aware feedback is the differentiator; the surface is not specified.

## Open questions by layer

### Layer 1 -- Typed Model

- **Q-L1.1.** What is the minimum typed-question schema for a COTS to be declarable in advance? Current state: Jev and similar System One models are the reference examples; the discipline needs a normative schema.
- **Q-L1.2.** How does the typed-model layer handle the case where the model cannot answer the question with the declared shape (the answer is genuinely unknown)? Current state: the discipline assumes "I don't know" is a first-class outcome; the schema for the unknown case is not specified.

### Layer 2 -- Runtime Validation

- **Q-L2.1.** What is the calibration contract between the model and the runtime layer? Current state: per-segment drift is a problem; the contract is not specified.
- **Q-L2.2.** How does the runtime layer amortise the cost of carrying a full COTS at every call (caching, batched audit, asynchronous persistence)? Current state: latency vs. auditability is recognised as a trade-off; the amortisation strategies are not enumerated.

### Layer 3 -- Business Guardrails

- **Q-L3.1.** What is the DSL for declaring business guardrails that reference the COTS schema? Current state: guardrails are domain-specific; the DSL is not specified.
- **Q-L3.2.** How does the guardrail layer distinguish between a guardrail that is binding (the decision is rejected) and one that is advisory (the decision is annotated)? Current state: the discipline assumes both; the distinction is not specified.

### Layer 4 -- Audit Trail

- **Q-L4.1.** What is the persistence contract for the audit trail? Current state: the discipline assumes the audit trail is persistent; the retention policy, the access model, and the tamper-evidence guarantees are not specified.
- **Q-L4.2.** How does the audit trail support re-runs against historical COTS bundles? Current state: re-runs are a defined operation; the historical-COTS access pattern is not specified.

## Foundational questions (cross-pillar)

- **Q-F.1.** What is the relationship between the COTS and the model's chain-of-thought? Are they the same, distinct, or partially overlapping? Current state: the discipline explicitly distinguishes them (the manifesto's third principle) but the formal relationship is not specified.
- **Q-F.2.** What is the relationship between the COTS and the model's training data? Can the COTS reference the training data, or only the inputs to the call? Current state: the discipline assumes only the call's inputs; the deeper training-data traceability is out of scope for the COTS but is an open question for the discipline.
- **Q-F.3.** How does the discipline handle the case where a Source Engineering system's COTS is itself wrong (the system claims to carry a COTS that does not actually reflect the model's reasoning)? Current state: the discipline assumes the COTS is faithful; the verification mechanism is not specified.

## Closed questions

(none yet; the first protocol is `protocols/legal-summarization-evaluation.md`)

## Related documents

- `protocols/` -- experimental protocols that close questions
- `findings/` -- empirical results that confirm or refute hypotheses
- `Source-Engineering/source-engineering-foundations/docs/00-manifesto.md` -- the open questions carried forward from the 2026 reframing

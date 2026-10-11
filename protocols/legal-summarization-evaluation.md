# Protocol -- Legal-Document Summarisation Evaluation

> Experimental protocol for closing the open question named in the 2025 essay: does Source Engineering reduce the hesitation factor in a domain where the cost of a confidently wrong decision is liability, not latency?

This protocol is the first research artefact of the Source Engineering discipline. It corresponds to the open question in the 2025 essay: *"I'll be opening up a study on this in 2026, to develop a prototype system with a specific, well-defined task (e.g., legal document summarization)."*

## Hypothesis

A Source Engineering system that carries a full COTS for each summarisation reduces the hesitation factor (as measured by practitioner self-report) compared to a baseline summarisation system that returns only the summary text, in the legal document summarisation domain.

## Independent variable

The presence (or absence) of a COTS in the summarisation response.

## Dependent variable

The hesitation factor, measured by:

- Practitioner self-report on a 7-point Likert scale after each summarisation
- Time-to-decision (the time the practitioner takes to accept, reject, or refer the summary)
- The proportion of summaries the practitioner asks the system to expand or re-run (a proxy for trust)
- The proportion of summaries the practitioner ultimately acts on (a proxy for the hesitation factor)

## Design

- **Sample size.** 20 legal practitioners (attorneys, paralegals, in-house counsel). The sample size is small because the protocol is qualitative; the goal is to surface themes, not to estimate effect sizes.
- **Domain.** One jurisdiction, one document type (commercial contract review). Narrow on purpose: the goal is depth on one domain, not breadth across many.
- **Conditions.** Each practitioner reviews 30 contract summaries under two conditions: COTS-on (the summary carries a COTS) and COTS-off (the summary does not). The order is counterbalanced.
- **Outcome measure.** Each review session is recorded. The practitioner self-reports the hesitation factor on a 7-point Likert scale after each summary. The reviewer also records time-to-decision and the proportion of summaries expanded or re-run.
- **Qualitative follow-up.** At the end of the review session, each practitioner is interviewed about their experience. The interview is transcribed and analysed for themes related to the hesitation factor and the role of the COTS.

## Inclusion criteria

- Practitioners with at least 3 years of experience in commercial contract review
- Practitioners who have used an AI-assisted summarisation tool at least once in the past 12 months
- Practitioners who can commit to a 90-minute review session

## Exclusion criteria

- Practitioners who have participated in the design of the COTS schema
- Practitioners who have a financial interest in the COTS-bearing or COTS-off tools

## Anonymisation

All data is anonymised at the point of collection. The interview transcripts are scrubbed of identifying information before analysis. The findings report does not name individual practitioners.

## Reproducibility

The protocol includes:

- The exact prompt template used to generate the summaries
- The exact COTS schema used in the COTS-on condition
- The exact interview guide
- The exact analysis script for the qualitative data
- The exact environment (model name, model version, temperature, etc.) for the summarisation calls

The protocol is a contract: any future run of this experiment against the same data should reproduce the same results within the bounds of the model's stochasticity.

## Analysis plan

- **Quantitative.** Compare the hesitation-factor self-report, the time-to-decision, the expansion rate, and the act-on rate between the COTS-on and COTS-off conditions. Use paired tests appropriate for the small sample size.
- **Qualitative.** Code the interview transcripts for themes related to: trust in the summary, role of the COTS in the review, situations where the COTS helped, situations where the COTS did not help, situations where the COTS introduced new uncertainty.

## Pre-registration

The hypothesis, the independent variable, the dependent variables, and the analysis plan are pre-registered before data collection. The pre-registration is held in this repository as `findings/pre-registration.md` once it is filed.

## Open questions this protocol addresses

This protocol is designed to close:

- A subset of **Q5.1** (closing the feedback loop) -- by observing whether the COTS changes the practitioner's trust in the summary enough to act on it.
- A subset of **Q4.1** (user-facing trace) -- by observing whether the practitioner uses the COTS as a user-facing trace, not just the operator.

The protocol does not address the other open questions in the agenda. Those are addressed by separate protocols as the discipline grows.

## What the protocol is not

- **Not a benchmark.** The protocol is qualitative and small-sample. It surfaces themes; it does not estimate effect sizes that can be compared across runs.
- **Not a clinical trial.** The protocol is a research protocol, not a clinical study. The findings inform the discipline; they do not certify the system.
- **Not a final word.** The protocol is the first of many. A successful run informs the next protocol; a refutation reopens the question and triggers a new protocol.

## Related documents

- `Source-Engineering/source-engineering-foundations/docs/00-manifesto.md` -- the manifesto's open questions
- `Source-Engineering/source-engineering-specifications` -- the COTS schema (forthcoming in Phase 2)
- `Source-Engineering/source-engineering-case-studies` -- where the resulting case study lives (forthcoming in Phase 4)

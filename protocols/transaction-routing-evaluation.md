# Protocol -- Finance Transaction-Routing Evaluation

> Experimental protocol for the second-domain case study: does Source Engineering reduce the hesitation factor in a domain where the cost of a confidently wrong decision is a misrouted financial transaction?

This protocol is the discipline's second research artefact and the standardised hesitation-factor measurement the Advancement Plan's Phase 5 calls for. It mirrors `legal-summarization-evaluation.md` so results are comparable across domains: same conditions, same measures, same analysis. The domain changes; the method does not. That is what makes cross-domain comparison a discipline property rather than an anecdote.

## Hypothesis

A Source Engineering system that carries a full COTS for each routing decision reduces the hesitation factor (as measured by practitioner self-report) compared to a baseline routing system that returns only the chosen destination, in the financial transaction-routing domain.

Secondary hypothesis: a COTS-bearing routing system increases the analyst's ability to identify a wrong routing decision before execution (tertiary claim of the case-study template).

## Independent variable

The presence (or absence) of a COTS in the routing response.

## Dependent variable

The hesitation factor, measured identically to the legal protocol:

- Practitioner self-report on a 7-point Likert scale after each routing decision
- Time-to-decision (accept / reject / refer the routing)
- Expansion rate (proportion of routings the analyst asks the system to expand or re-run)
- Act-on rate (proportion of routings the analyst ultimately executes)
- **Domain-specific addition:** wrong-route catch rate (proportion of deliberately misrouted test transactions the analyst flags before execution). This is the finance-domain operationalisation of "ability to identify a wrong decision."

## Design

- **Sample size.** 20 financial operations analysts (payments ops, treasury, compliance). Same size as the legal protocol so the two domains are comparable.
- **Domain.** One institution, one transaction type (outbound USD wires above a declared threshold). Narrow on purpose.
- **Conditions.** Each analyst reviews 30 routing decisions under COTS-on and COTS-off, counterbalanced, same as the legal protocol.
- **Misrouted probes.** A fixed subset of 6 of the 30 decisions per condition are deliberately misrouted (the baseline picks a destination that violates a declared constraint); the catch rate on these probes is the domain-specific measure.
- **Outcome measure.** Sessions recorded; self-report after each decision; time-to-decision and expansion/re-run counts logged by the harness.
- **Qualitative follow-up.** 30-minute interview per analyst, transcribed and thematically coded, same guide as the legal protocol with finance-domain prompts (e.g. "what would have made you catch the wrong route faster?").

## Analysis

- Paired tests (Wilcoxon signed-rank, given small n and ordinal self-report) for hesitation factor, time-to-decision, expansion rate, act-on rate, and wrong-route catch rate, COTS-on vs. COTS-off.
- Thematic coding of interviews, coded against the same theme frame as the legal study so cross-domain themes can be compared.
- **Cross-domain comparison.** Report effect direction and rank-biserial correlation per domain; a claim generalises across domains only if the direction is consistent in both.

## Pre-registration

- Protocol registered before any data collection; the case study lands in `Source-Engineering/source-engineering-case-studies/2026-finance-transaction-routing/`.
- Deviations from this protocol are recorded in the case study's "Deviations from the template" section.
- The data committed with the case study is illustrative until a real run is executed, and is labelled as such.

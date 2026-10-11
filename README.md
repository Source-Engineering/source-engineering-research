# Source Engineering -- Research

> Research agenda, hypotheses, experimental protocols, evaluation reports.

This repository holds the discipline's research surface. It is where open questions are listed, hypotheses are stated, experiments are designed, and findings are recorded. The research repo is the discipline's way of being evidence-driven in its own evolution: every claim in the discipline is a hypothesis until an experiment closes it.

## What is in this repository

- `agenda.md` -- the discipline's open research questions, grouped by pillar and by layer.
- `protocols/` -- experimental protocols. Each protocol is a reproducible plan for closing a specific research question.
- `findings/` -- evaluation reports and empirical results. Each finding either confirms or refutes a hypothesis, and either opens or closes a research question.
- `CHANGELOG.md` -- change log of the research repo itself.

## How to engage

- **Read the agenda first.** Start at `agenda.md`. The agenda is a living document; open questions are added as they are recognised, closed as they are answered.
- **Pick a question and file a protocol.** Find an open question you can contribute to. File an experimental protocol under `protocols/` that describes how the question will be closed.
- **Run the protocol and report a finding.** The finding is documented under `findings/` with the data, the analysis, and the conclusion. A finding either confirms the hypothesis (and the question is closed) or refutes it (and the question is reopened with the new evidence).

## Research principles

- **A finding is a finding only if it can be reproduced.** Every finding includes the data, the analysis script, and the environment it ran in. Reproducibility is the discipline's evidence standard.
- **A hypothesis is a hypothesis only if it can be refuted.** A claim that cannot be refuted by any experiment is not a hypothesis; it is an axiom. Axioms are stated as principles in `Source-Engineering/source-engineering-foundations`.
- **Negative results are findings.** A protocol that refutes a hypothesis is a successful experiment, not a failed one. The discipline's value comes from the set of closed questions, not from the set of confirmed claims.
- **Findings feed back through governance.** A finding that implies a change to a pillar, a principle, or a COTS component triggers an RFC in `Source-Engineering/source-engineering-governance`.

## Organisation

The discipline is published as a set of repositories under the [Source-Engineering](https://github.com/Source-Engineering) GitHub organisation. One authoritative home per artefact:

| Repo | Owns |
|---|---|
| [Source-Engineering/.github](https://github.com/Source-Engineering/.github) | Org profile README |
| [Source-Engineering/project-governance](https://github.com/Source-Engineering/project-governance) | Project-level governance for the governance home itself |
| [Source-Engineering/source-engineering-governance](https://github.com/Source-Engineering/source-engineering-governance) | Org-wide discipline governance |
| [Source-Engineering/source-engineering-foundations](https://github.com/Source-Engineering/source-engineering-foundations) | Discipline definition, principles, terminology |
| [Source-Engineering/source-engineering-research](https://github.com/Source-Engineering/source-engineering-research) (this repo) | Research agenda, hypotheses, experimental protocols, findings |
| [Source-Engineering/source-engineering-model](https://github.com/Source-Engineering/source-engineering-model) | Canonical conceptual and data model |
| [Source-Engineering/source-engineering-specifications](https://github.com/Source-Engineering/source-engineering-specifications) | Normative technical requirements |
| [Source-Engineering/source-engineering-architecture](https://github.com/Source-Engineering/source-engineering-architecture) | Reference architecture, blueprint stack |
| [Source-Engineering/source-engineering-reference-implementation](https://github.com/Source-Engineering/source-engineering-reference-implementation) | Working reference code |
| [Source-Engineering/source-engineering-conformance](https://github.com/Source-Engineering/source-engineering-conformance) | Conformance test suite |
| [Source-Engineering/source-engineering-tools](https://github.com/Source-Engineering/source-engineering-tools) | Reusable software utilities |
| [Source-Engineering/source-engineering-case-studies](https://github.com/Source-Engineering/source-engineering-case-studies) | Evaluated demonstrations, case studies |
| [Source-Engineering/source-engineering-practice](https://github.com/Source-Engineering/source-engineering-practice) | Practitioner guidance |
| [Source-Engineering/source-engineering-education](https://github.com/Source-Engineering/source-engineering-education) | Curriculum and learning resources |

## Status

This is the research slice (Phase 1). The agenda is seeded with the discipline's initial open questions. The first experimental protocol is `protocols/legal-summarization-evaluation.md`, corresponding to the open question the 2025 essay named.

## License

Apache-2.0. See [LICENSE](LICENSE).

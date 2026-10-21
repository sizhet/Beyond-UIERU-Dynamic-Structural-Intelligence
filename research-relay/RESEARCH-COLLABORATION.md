# Research Collaboration — Open Research Relay for Dynamic Structural Intelligence

**Repository:** Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay (BUI-DSI)  
**Version:** 1.0.0 — Research agenda and collaboration protocol  
**Authors / initial curators:** Sizhe Tan & GPT-Obot  
**Status:** Open research invitation; proposed models and hypotheses are not established results.

## 1. Purpose

This document explains how independent researchers can engage with the BUI-DSI research agenda without adopting its terminology, accepting its hypotheses, or committing to a particular implementation. The objective is **open, reproducible research relay**: transmit a well-scoped problem, its assumptions, evidence, counter-evidence, and interfaces so another investigator can refine, challenge, replace, or validate it.

BUI-DSI extends the Universal Intelligence Evolution and Relay Unit (UIERU) line of structural-intelligence research toward dynamic observation, perspective-conditioned comparisons, behavioral equivalence, compositional contracts, biological inspiration, and open structural evolution. The repository is a *research proposal and problem catalog*, not a claim that the formal foundations, experimental performance, or biological correspondence have been established.

Researchers may participate through theory, experiments, critical analysis, benchmark design, alternative models, negative results, or engineering demonstrations. A rigorous counterexample is a first-class contribution.

## 2. Research principles

1. **Separate proposal from evidence.** Mark each statement as definition, assumption, conjecture, simulation result, measured result, or established external result.
2. **Preserve the comparison boundary.** Behavioral comparisons must specify perspective, context, history, observation interface, horizon, and tolerance.
3. **Treat interventions distinctly.** A perspective mask on recorded data is not automatically a causal intervention or a valid counterfactual.
4. **Require contract-scoped composition.** Local competence, interface compatibility, and global safety are different claims.
5. **Make evolution auditable.** Preserve candidate lineage, evaluator versions, evidence provenance, failed tests, and rollback conditions.
6. **Keep biological claims falsifiable.** Analogies to neural systems do not imply anatomical or mechanistic identity.
7. **Welcome incompatible formalisms.** A superior competing definition or model is a successful relay outcome.
8. **Recognize research contributors fairly.** Do not confuse the initial framing of a problem with proof of a theorem or independent experimental discovery.

## 3. Entry points: research tracks

| Track | Entry document | Central question | Suitable disciplines |
|---|---|---|---|
| R1: Perspective masking | `research-relay/RELAY-001-Perspective-Masking-Algebra.md` | Under which semantics do masks compose and preserve observations or decisions? | Algebra, databases, abstract interpretation, causal inference |
| R2: Dynamic equivalence | `research-relay/RELAY-002-Dynamic-Behavioral-Equivalence.md` | When are evolving units behaviorally equivalent or substitutable? | Formal methods, probability, control, verification |
| R3: Relay composition | `research-relay/RELAY-003-Relay-Composition-and-Contracts.md` | Which local contracts entail system-level guarantees? | Programming languages, distributed systems, systems engineering |
| R4: Biological dynamics | `research-relay/RELAY-004-Biological-Dynamic-Intelligence.md` | Which context-sensitive functional hypotheses survive biological evidence? | Neuroscience, dynamical systems, experimental design |
| R5: Structural evolution | `research-relay/RELAY-005-Open-Structural-Evolution.md` | How can systems generate and adopt new structures under governed evaluation? | AI, continual learning, optimization, governance |
| R6: RSI–UIERU convergence | **Proposed** `research-relay/RELAY-006-RSI-UIERU-Convergence-and-Structural-Governance.md` | Can LLM-based recursive improvement be represented and evaluated with UIERU-like structural interfaces? | LLM agents, RSI, interpretable systems, evaluation |

**Track R6 is proposed but not yet part of the five completed Relay documents.** Recursive self-improvement (RSI) is not synonymous with LLMs, and structural observability does not imply full interpretability of an internal model.

Researchers can also begin with `cases/CASE-001-Perspective-Masked-Model-Selection.md`, `cases/CASE-002-Dynamic-Equivalence-and-Relay-Substitution.md`, or `cases/CASE-003-Context-Dependent-Biological-Intelligence.md` for more concrete scenarios. Case numbers and any synthetic examples are illustrative, not independently measured results.

## 4. How to submit a Research Relay Piece (RRP)

A useful contribution should contain the following six elements, plus provenance:

- **P — Problem:** A precise question and why it matters; define the target scope.
- **M — Model:** State variables, interfaces, mathematical semantics, assumptions, and exclusions.
- **H — Hypotheses:** Testable propositions or proof obligations; distinguish conjecture from theorem.
- **E — Evidence:** Positive evidence, negative evidence, confounders, uncertainties, and counterexamples.
- **V — Validation:** Proof plan, experimental protocol, baselines, metrics, acceptance and rejection criteria.
- **I — Interfaces:** Inputs/outputs, dependencies, data and artifact formats, compatibility requirements.
- **Provenance:** Authorship, versions, dates, references, licenses, and derivation history.

A relay may be intentionally partial. For example, a precise counterexample to a conjecture can be valuable even without a replacement theory. State which fields are unknown rather than filling them with unsupported claims.

### Suggested RRP template

```yaml
rrp_id: RRP-<unique-id>
title: <descriptive title>
status: proposed                 # proposed | in-progress | tested | refuted | superseded
track: R1                        # R1..R6 or cross-track
contributors:
  - name: <name or preferred attribution>
    role: <framing | formalization | proof | experiment | critique | implementation>
problem:
  question: <specific research question>
  scope: <included cases>
  exclusions: <out-of-scope cases>
model:
  definitions: []
  assumptions: []
  observables: []
  perspective_context_history: <explicit conditions>
hypotheses:
  - id: H1
    statement: <falsifiable statement or proof obligation>
    status: conjecture
    falsifier: <what would refute it>
evidence:
  positive: []
  counter_evidence: []
  limitations: []
validation:
  method: <proof | experiment | simulation | replication | review>
  baselines: []
  metrics: []
  acceptance_criteria: []
  rejection_criteria: []
interfaces:
  inputs: []
  outputs: []
  dependencies: []
provenance:
  sources: []
  artifact_versions: []
  date: YYYY-MM-DD
  license: <applicable license>
```

The YAML is an illustrative proposal, **not** a finalized machine-validated standard. It may evolve through the planned `specs/SPEC-004-Research-Relay-Piece-Contract.md`.

## 5. Contribution types and acceptance criteria

| Contribution | Minimum useful deliverable | Evidence standard |
|---|---|---|
| Formal definition | Explicit domain, assumptions, notation, examples | No hidden quantifier or unspecified comparison context |
| Proof or disproof | Statement, proof, counterexample, dependencies | Independently checkable reasoning |
| Algorithm or prototype | Reproducible inputs, outputs, environment, limitations | Comparison with a reasonable baseline |
| Experiment | Protocol, dataset provenance, metrics, controls | Reproducible method and reported uncertainty |
| Negative result | Failed hypothesis, conditions, traces or reasoning | Clear reason the result bears on the claim |
| Biological study | Task, measurement, controls, alternative hypotheses | No inference of neural mechanism from behavior alone |
| Survey or synthesis | Scope, source selection, competing interpretations | Distinguish established literature from BUI-DSI proposals |
| Governance critique | Threat model, failure case, mitigation or open question | Explicit tradeoffs and residual risks |

A contribution is not rejected merely because it disputes BUI-DSI. The standard is clarity and evidence, not agreement.

## 6. Recommended collaboration workflow

1. **Choose a narrowly scoped claim.** Identify the relevant BUI, CASE, RELAY, or SPEC document and its version.
2. **Register the question.** Open a GitHub Issue in the repository, if issue tracking is enabled, or submit a clearly titled proposal through an available repository contribution channel. Link to the specific claim or section.
3. **Declare assumptions and evidence needs.** Use the RRP fields, including counter-evidence criteria and relevant perspectives.
4. **Work in an independently reviewable artifact.** A note, proof, executable notebook, data protocol, or benchmark is sufficient when appropriately documented.
5. **Review across disciplines.** Where possible, ask a formal-methods reviewer to check semantics and a domain expert to check empirical interpretation.
6. **Report results with uncertainty.** Include failures, unresolved objections, resource limitations, and possible confounders.
7. **Relay forward or backward.** Extend the result into a new RRP, or issue a correction to an earlier assumption or contract.
8. **Version the outcome.** Preserve original hypotheses and trace the change instead of silently rewriting history.

This workflow is a recommendation; no claim is made that repository issue templates, continuous integration, or maintainer response procedures already exist.

## 7. Counter-evidence and disagreement protocol

A serious counterexample should specify: (a) the target claim and version; (b) the assumptions under which the claim is asserted; (c) the construction, dataset, trace, or argument; (d) why it contradicts the claim; and (e) whether the contradiction is local, general, or unresolved.

Possible dispositions include **confirmed refutation**, **restricted claim**, **alternative interpretation**, **needs replication**, and **open disagreement**. Record the reasoning and preserve the dissenting artifact. Do not label an unresolved disagreement as refuted or resolved.

In particular:

- A matching output on a benchmark is not proof of dynamic behavioral equivalence.
- A masked replay is not necessarily an intervention.
- Two compatible unit interfaces do not establish compositional safety.
- Improved evaluator scores do not by themselves establish genuine structural intelligence growth.
- Similarities between UIERU-like models and neural data do not establish biological implementation identity.

## 8. Cross-track research opportunities

**Masking × Equivalence:** Characterize the observational abstractions under which conditional equivalence is preserved; construct counterexamples for non-preserving masks.

**Equivalence × Contracts:** Determine when approximate local substitutability entails bounded global deviation under serial, parallel, and feedback Relay composition.

**Contracts × Evolution:** Define which invariants survive replacement, reweighting, branching, or self-modification; measure contract drift.

**Biology × Dynamic Localization:** Compare fixed-function, reweighted-network, and dynamically assembled functional coalition hypotheses under context changes and interventions.

**RSI × Structural Governance:** Test whether explicit evaluator provenance, candidate lineage, contracts, and counter-evidence improve auditability of LLM-agent recursive improvement without assuming transparent neural internals.

**Research Relay × Reproducibility:** Test whether structured RRP exchanges improve independent replication and problem transfer compared with unstructured research notes.

These are invitations to study, not claims of demonstrated benefits.

## 9. Experimental design and reproducibility checklist

For any empirical claim, report:

- Research question, preregistered hypothesis where feasible, and study version.
- Unit and system boundaries, perspective, context, history, and observation window.
- Datasets or simulated environments, generation procedure, licensing, and leakage risks.
- Baselines and ablations, including an alternative explanation where feasible.
- Sample sizes, random seeds, uncertainty estimates, and statistical limitations.
- Evaluator identity/version, reward or score definition, and known Goodhart risks.
- Contract checks, safety conditions, and the meaning of any pass/fail decision.
- Failure cases, negative results, and reproducibility instructions.
- Whether results are synthetic, simulated, observational, interventional, or field-deployed.

When code or data cannot be shared, provide the most informative reproducibility description permitted by privacy, ethics, and intellectual-property constraints. Do not publish personal, confidential, or otherwise restricted data to satisfy openness goals.

## 10. Research ethics and governance

Contributors should follow institutional and legal requirements applicable to human-subject research, animal research, sensitive datasets, and deployed AI systems. BUI-DSI does not provide ethics approval or a safety certification.

For self-modifying or tool-using agents, favor constrained sandboxes, explicit permissions, monitored execution, evaluation holdouts, provenance logs, and rollback mechanisms. Any deployment claim should state its threat model and limits. Research on RSI–UIERU convergence should distinguish increased *structural traceability* from interpretability of the model's latent computations.

## 11. Attribution, citation, and publication

**Initial repository authors:** Sizhe Tan & GPT-Obot. Contributions by external researchers should be credited for their actual roles and outputs. A repository co-author listing does not confer authorship over an independent proof, experiment, or subsequent publication. Authorship and acknowledgments should follow the norms of the relevant venue and the contributors' agreements.

When citing this repository, use the version-specific DOI after it has been issued; do not invent a DOI. Until then, cite the GitHub repository and the relevant document version. If the repository provides `CITATION.cff`, prefer its current metadata, checking that it matches the release.

Proposals, formal statements, proofs, datasets, software, figures, and prose may have different licensing requirements. Check the repository `LICENSE` and individual artifact metadata. Do not assume that a software license automatically settles reuse rights for datasets, third-party figures, or external contributions. Where possible, contributors should state the applicable license explicitly.

## 12. Research maturity and publication labels

Use the following labels consistently:

| Label | Meaning |
|---|---|
| **Conceptual proposal** | An organizing idea or candidate architecture without formal or empirical validation |
| **Candidate formalization** | Definitions or semantics proposed for scrutiny |
| **Conjecture / open problem** | A statement awaiting proof, disproof, or qualification |
| **Synthetic illustration** | Constructed example demonstrating mechanics, not measured performance |
| **Empirical observation** | Result tied to a specified study, data source, and protocol |
| **Validated within scope** | Claim supported under explicitly documented conditions and limitations |
| **Refuted / superseded** | Claim rejected or replaced with retained provenance |

A release number, GitHub publication, Zenodo archive, or DOI establishes a citable record; none by itself establishes peer review or scientific validity.

## 13. Collaboration deliverables and milestones

**Phase A — Shared language.** Agree on minimal dynamic observation and masking semantics; publish examples and disambiguate intervention from replay.

**Phase B — Formal boundaries.** Develop conditional equivalence and composition proof obligations; collect minimal counterexamples.

**Phase C — Reproducible cases.** Implement at least one model-selection and one Relay-substitution testbed with baselines, traces, and contract checks.

**Phase D — Evolution and governance.** Test controlled structure changes and RSI-generated candidates with evaluator provenance and rollback conditions.

**Phase E — Cross-domain validation.** Evaluate transfer to biological hypotheses and independent research teams; document where analogies fail.

Milestones are proposed and not promises of staffing, funding, or completion dates.

## 14. Suggested first contributions

Researchers seeking a tractable starting point can:

1. Produce a two-mask noncommutativity counterexample with explicit state semantics.
2. Give a formal definition of context-bounded approximate behavioral equivalence for evolving stochastic units.
3. Show a minimal Relay graph in which local substitution violates a global contract.
4. Create a controlled synthetic benchmark that separates scoring differential from decision differential.
5. Design a neuroscience experiment that discriminates reweighting from changing functional coalitions, with explicit confounders.
6. Test whether evaluator versioning and counter-evidence logs improve diagnosis of RSI regression.
7. Critique the proposed RRP schema for missing provenance, causal semantics, or reproducibility fields.

## 15. Relationship to repository documents

**Core conceptual series:** `docs/BUI-001-...md` through `docs/BUI-008-...md`.  
**Concrete scenarios:** `cases/CASE-001-...md` through `cases/CASE-003-...md`.  
**Open research tracks:** `research-relay/RELAY-001-...md` through `research-relay/RELAY-005-...md`.  
**Proposed extension:** `research-relay/RELAY-006-RSI-UIERU-Convergence-and-Structural-Governance.md`.  
**Planned interface specifications:** `specs/SPEC-001-...md` through `specs/SPEC-004-...md`.  
**Validation navigation:** `OPEN-QUESTIONS.md`, `TESTABLE-HYPOTHESES.md`, `VALIDATION-ROADMAP.md`.

The shortened wildcard names above are navigational descriptions, not literal filesystem paths. Refer to `CONTENTS.md` once published for the canonical inventory.

## 16. Closing invitation

The next stage of structural intelligence research may depend less on one group supplying all answers than on making difficult questions **portable, inspectable, falsifiable, and composable** across research communities.

The intended relay is bidirectional: theory can guide experiments and engineering, while counterexamples, biological evidence, formal results, and practical failures can revise the theory. The goal is not to protect the UIERU vocabulary; it is to learn which parts of the proposed framework survive independent scrutiny and what stronger structures can replace the parts that do not.

**A useful research relay preserves the right to disagree—and the evidence needed to make disagreement productive.**

---

*Prepared for the BUI-DSI v1.0.0 research repository. Authors / initial curators: Sizhe Tan & GPT-Obot.*

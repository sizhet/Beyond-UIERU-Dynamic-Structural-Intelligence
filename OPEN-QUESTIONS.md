# Open Questions — Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay

**Version:** 1.0.0 (research agenda)  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Open research questions; no theorem, empirical result, or biological mechanism is asserted as established by this document.  
**Repository:** `Beyond-UIERU-Dynamic-Structural-Intelligence`

## 1. Purpose and Research Discipline

This document turns the BUI-DSI research directions into **addressable, falsifiable, and transferable research questions**. Each question includes its scope, prerequisites, a proposed investigation, potential counter-evidence, and an expected Research Relay output. The questions are hypotheses and design challenges, not demonstrated properties of UIERU implementations.

A dynamic Universal Intelligence Evolution and Relay Unit (UIERU) is considered here as a *candidate structural abstraction* for a context-dependent, perspective-sensitive system that observes, scores, selects, acts, receives feedback, and may modify its organization. Neither an LLM agent nor a biological neural circuit is presumed to instantiate this abstraction without evidence.

**Research principles:** distinguish observation from intervention; state the comparison contract; preserve provenance and negative findings; distinguish local improvement from system-level gain; require independent replication where practical.

## 2. Shared Research Notation

Let a candidate dynamic unit be represented by

$$
U_t=(S_t, C_t, P_t, F_t, K_t, H_t, G_t),
$$

where \(S\) denotes observable state, \(C\) context, \(P\) perspective or valuation configuration, \(F\) behavioral transition mechanism, \(K\) interface contracts, \(H\) history/evidence, and \(G\) governance constraints. This is a **proposed modeling convention**, not a universal ontology.

A comparison contract is

$$
\Gamma=(\mathcal T,\mathcal C,\mathcal P,\mathcal H,\mathcal O,T,\epsilon,\mathcal E),
$$

specifying task distribution, context, perspective, permitted histories, observation mapping, horizon, tolerance, and evidence requirements. Write \(U\sim_{\Gamma}V\) only for an equivalence claim explicitly tied to \(\Gamma\).

**Priority:** P0 = foundational and immediately actionable; P1 = important after P0 semantics; P2 = exploratory or dependent on stronger evidence. Priority is a research-planning recommendation, not a scientific ranking.

## 3. Perspective Masking: Semantics and Algebra

### OQ-001 — What is the minimal typed semantics of a perspective mask? [P0]

**Question.** Can observational projection, rescoring, replay, simulation, intervention, and counterfactual estimation be represented in one typed operator framework without conflating their epistemic status?

**Dependencies:** SPEC-001, SPEC-002, RELAY-001.  
**Approach:** Define input/output types, permitted transformations, provenance, and causal claims for each operator.  
**Counter-evidence:** A proposed common operator type silently converts simulated outcomes into observed outcomes.  
**Relay output:** A typed semantics, examples, and machine-checkable invalid compositions.

### OQ-002 — When do masking operators commute, compose, or become idempotent? [P0]

**Question.** Which restricted classes of masks satisfy \(M_aM_b=M_bM_a\), \(M^2=M\), or associative composition, and which do not?

**Dependencies:** OQ-001.  
**Approach:** Prove conditional propositions for pure projections; construct counterexamples for rescoring and interventions.  
**Counter-evidence:** Order-sensitive context updates invalidate a claimed identity.  
**Relay output:** Theorems with assumptions, executable counterexamples, and a small property-test suite.

### OQ-003 — How should masking information loss be measured? [P1]

**Question.** Can an information preorder or task-specific sufficient-statistic criterion quantify whether one masked view retains what another decision procedure needs?

**Dependencies:** OQ-001, explicit task distributions.  
**Approach:** Compare refinement order, mutual information, and decision-regret bounds under stated distributions.  
**Counter-evidence:** A mask with low global information loss destroys a rare but safety-critical signal.  
**Relay output:** A task-conditioned information-loss measure and failure cases.

### OQ-004 — Under what conditions is a masked view decision-preserving? [P1]

**Question.** What sufficient conditions ensure that decisions computed from a mask agree with decisions from the full admissible observation?

**Dependencies:** OQ-002, OQ-003.  
**Approach:** Derive conditions using score margins, bounded approximation error, and tie-breaking policies.  
**Counter-evidence:** Tiny omitted features flip decisions near a score boundary.  
**Relay output:** Conditional preservation bounds and adversarial boundary tests.

## 4. Dynamic Differentials, Localization, and Query

### OQ-005 — How can scoring, decision, trajectory, and learning differentials be separated? [P0]

**Question.** What measurement protocol distinguishes a change in valuation from a change in selected action, realized behavior, or persistent adaptation?

**Dependencies:** SPEC-001–003, CASE-001.  
**Approach:** Paired observations and controlled replays with separate outcome fields and confidence intervals.  
**Counter-evidence:** A claimed learning differential vanishes after resetting transient state.  
**Relay output:** A differential taxonomy, paired dataset specification, and diagnostic tests.

### OQ-006 — What makes a Perspective Differential Tree (PDT) sound and useful? [P0]

**Question.** Can a PDT index dynamic differences without misrepresenting uncertainty, incomplete observations, or comparison-contract changes?

**Dependencies:** OQ-005, SPEC-003.  
**Approach:** Define node invariants, lineage, validity intervals, and invalidation rules; compare with flat event logs.  
**Counter-evidence:** A stale PDT branch continues to answer queries after structural evolution.  
**Relay output:** PDT semantics, reference schema, and consistency tests.

### OQ-007 — Which PASQ query rewrites preserve meaning? [P1]

**Question.** When can perspective filtering, aggregation, temporal joins, and differential operations be reordered without changing query meaning?

**Dependencies:** OQ-001, OQ-005, OQ-006.  
**Approach:** Define relational/temporal semantics and derive rewrite conditions.  
**Counter-evidence:** Aggregation before context filtering produces misleading equivalence.  
**Relay output:** Query algebra, rewrite rules, and counterexample queries.

### OQ-008 — Can dynamic localization be incremental and reliable? [P1]

**Question.** How should PDT and PASQ update when units, perspectives, contracts, or histories evolve?

**Dependencies:** OQ-006–007.  
**Approach:** Incremental maintenance with versioned event sourcing and explicit dependency invalidation.  
**Counter-evidence:** An update protocol loses an affected branch or falsely retains a prior guarantee.  
**Relay output:** Incremental algorithm, complexity analysis, and mutation-test corpus.

## 5. Dynamic Behavioral Equivalence and Substitution

### OQ-009 — Which notion of dynamic equivalence is appropriate for UIERUs? [P0]

**Question.** How do finite-trace similarity, distributional distance, approximate bisimulation, and contract substitutability differ under \(\Gamma\)?

**Dependencies:** RELAY-002, CASE-002.  
**Approach:** Define each relation, show implications under explicit assumptions, and produce non-implication counterexamples.  
**Counter-evidence:** Units with equal observed outputs diverge under a previously untested context.  
**Relay output:** Formal comparison lattice and benchmark examples.

### OQ-010 — How can an equivalence claim remain calibrated under distribution shift? [P0]

**Question.** When should a previously accepted \(U\sim_\Gamma V\) claim be weakened, expired, or revoked?

**Dependencies:** OQ-009, evidence provenance.  
**Approach:** Monitor drift, validity domains, and sequential evidence thresholds.  
**Counter-evidence:** Performance differences emerge only in rare contexts outside the original sample.  
**Relay output:** Revocation policy and change-point evaluation protocol.

### OQ-011 — What guarantees safe relay substitution? [P1]

**Question.** Under which interface, assumption–guarantee, temporal, and resource constraints can one unit replace another inside a relay graph?

**Dependencies:** OQ-009, RELAY-003.  
**Approach:** Model substitutability as contextual contract refinement; test both isolated and composed behavior.  
**Counter-evidence:** A locally equivalent replacement violates downstream latency or safety constraints.  
**Relay output:** Substitution theorem candidates, integration tests, and rollback criteria.

### OQ-012 — Can equivalence survive learning and structural modification? [P1]

**Question.** What bounds on adaptive updates suffice to preserve a specified behavioral relation over a finite horizon?

**Dependencies:** OQ-009–011.  
**Approach:** Study stability and approximate simulation under bounded transition drift.  
**Counter-evidence:** Two initially equivalent learners diverge after feedback exposure.  
**Relay output:** Conditional stability bounds and adversarial learning sequences.

## 6. Relay Composition, Contracts, and Governance

### OQ-013 — When do local contracts imply a global system contract? [P0]

**Question.** Which assumptions on interface matching, feedback, resource contention, and shared state permit compositional guarantees?

**Dependencies:** RELAY-003, SPEC-001–003.  
**Approach:** Assume–guarantee reasoning, trace contracts, and model checking of small relay graphs.  
**Counter-evidence:** Locally valid units deadlock, oscillate, or amplify errors when connected.  
**Relay output:** Compositional proof obligations and minimal failing graphs.

### OQ-014 — How should conflicting perspectives and scoring sovereignty be resolved? [P1]

**Question.** Can governance specify who may choose or override perspectives without collapsing multiple legitimate objectives into a single opaque score?

**Dependencies:** OQ-001, OQ-013, SSI/UCPSF background.  
**Approach:** Explicit authority graph, precedence rules, and conflict-resolution audit logs.  
**Counter-evidence:** An optimizer silently overrides a protected stakeholder's constraint.  
**Relay output:** Governance contract patterns and conflict scenarios.

### OQ-015 — How should counter-evidence propagate backward through a relay? [P0]

**Question.** Can a failed downstream guarantee be traced to upstream assumptions, evidence, or component versions without over-attributing causality?

**Dependencies:** OQ-013, SPEC-004.  
**Approach:** Versioned provenance graph and Two-Way CCC-style dependency invalidation.  
**Counter-evidence:** A failure report names a cause unsupported by intervention or dependency evidence.  
**Relay output:** Counter-evidence propagation protocol and provenance benchmark.

### OQ-016 — What constitutes a governable feedback loop? [P1]

**Question.** How can cyclic relay compositions avoid uncontrolled positive feedback, repeated unsafe actions, and contract drift?

**Dependencies:** OQ-013–015.  
**Approach:** Temporal contracts, rate limits, termination conditions, and stability analysis.  
**Counter-evidence:** A locally bounded loop produces unbounded global resource usage.  
**Relay output:** Feedback-loop safety properties and stress tests.

## 7. Open Structural Evolution and RSI–UIERU Convergence

### OQ-017 — What is a measurable structural improvement? [P0]

**Question.** How can genuine generalizable structural gain be distinguished from benchmark overfitting, transient performance, or mere accumulation of execution traces?

**Dependencies:** RELAY-005, OQ-005.  
**Approach:** Held-out tasks, cross-context transfer, cost accounting, and longitudinal evaluation.  
**Counter-evidence:** Gains disappear under new perspectives or after controlling for compute.  
**Relay output:** Multi-objective improvement protocol and negative-result registry.

### OQ-018 — Which evolution operators preserve critical invariants? [P1]

**Question.** Under what conditions do ADD, REPLACE, COMPOSE, SPLIT, MERGE, REWIRE, REWEIGHT, LOCALIZE, IMPORT, and RETIRE preserve specified contracts?

**Dependencies:** OQ-011, OQ-013, RELAY-005.  
**Approach:** Typed graph rewriting, proof obligations, and sandbox testing.  
**Counter-evidence:** A permitted local rewrite breaks a global guarantee.  
**Relay output:** Operator pre/postconditions and counterexample library.

### OQ-019 — Can RSI-generated candidates be evaluated through UIERU contracts? [P0]

**Question.** Can an LLM/RSI workflow expose enough observation, versioning, and evaluator evidence to support structural comparisons without claiming access to internal model reasoning?

**Dependencies:** SPEC-001–004, RELAY-005.  
**Approach:** Instrument two or more agent workflows; compare opaque-only and structured-audit protocols.  
**Counter-evidence:** Required state is unobservable, or auditing costs outweigh measured benefits.  
**Relay output:** Interoperability adapter, benchmark, and auditability report.

### OQ-020 — Does UIERU-style governance improve RSI reliability? [P1]

**Question.** Relative to matched baselines, do explicit contracts, counter-evidence, provenance, and adversarial sandboxes reduce unsafe or non-generalizing self-modifications?

**Dependencies:** OQ-019, OQ-017.  
**Approach:** Randomized or carefully paired evaluations with compute/time overhead recorded.  
**Counter-evidence:** No statistically meaningful reliability improvement or excessive performance penalty.  
**Relay output:** Reproducible comparative study, including negative findings.

### OQ-021 — How should evaluator drift and Goodhart effects be detected? [P0]

**Question.** Can an evolving system detect when it has learned to optimize the evaluator rather than the intended task?

**Dependencies:** OQ-017, OQ-019.  
**Approach:** Independent evaluators, hidden tests, adversarial probes, and periodic human review.  
**Counter-evidence:** All visible scores improve while independently measured task quality falls.  
**Relay output:** Evaluator governance protocol and failure taxonomy.

### OQ-022 — When does repeated execution become useful evidence relay? [P1]

**Question.** Which trace-quality, diversity, provenance, and update conditions convert repeated execution into reusable evidence or structural learning?

**Dependencies:** OQ-005, OQ-017.  
**Approach:** Ablate trace storage, evidence aggregation, policy updates, and structural rewrites separately.  
**Counter-evidence:** More traces increase storage but not decision quality or transfer.  
**Relay output:** Evidence-relay criteria and longitudinal ablation results.

## 8. Biological Dynamic Intelligence

### OQ-023 — Can dynamic functional boundaries be identified from neural and behavioral data? [P2]

**Question.** Do context-sensitive functional coalitions provide predictive explanatory value beyond fixed-module or simple reweighting models?

**Dependencies:** BUI-007, CASE-003, RELAY-004.  
**Approach:** Competing model fits with held-out behavioral predictions and preregistered contrasts.  
**Counter-evidence:** Simpler models predict equally well; inferred boundaries are unstable artifacts.  
**Relay output:** Model-comparison protocol and uncertainty report.

### OQ-024 — What can intervention establish beyond observational masking? [P2]

**Question.** Which causal claims about context-dependent valuation or coordination survive controlled perturbation?

**Dependencies:** OQ-001, OQ-023, appropriate experimental ethics.  
**Approach:** Separate observational, perturbational, and counterfactual analyses with explicit assumptions.  
**Counter-evidence:** Observed correlation disappears or reverses under intervention.  
**Relay output:** Causal-identification checklist and study design.

### OQ-025 — When is a UIERU-like biological analogy scientifically useful? [P2]

**Question.** Can the analogy generate discriminating predictions rather than merely redescribe known neural behavior?

**Dependencies:** OQ-023–024.  
**Approach:** Predefine predictions that distinguish UIERU-like organization from established alternatives.  
**Counter-evidence:** No unique testable predictions or consistently inferior fit.  
**Relay output:** Falsifiable prediction set and explicit limits of analogy.

## 9. Open Research Relay and Scientific Infrastructure

### OQ-026 — What is the minimal portable Research Relay Piece? [P0]

**Question.** Which required fields allow independent researchers to understand, reproduce, dispute, and extend a claim?

**Dependencies:** SPEC-004, RESEARCH-COLLABORATION.  
**Approach:** Validate a six-part core (Problem, Model, Hypotheses, Evidence, Validation, Interfaces) with governance and lineage metadata.  
**Counter-evidence:** Independent teams cannot reconstruct the claim or its boundary conditions.  
**Relay output:** RRP conformance examples and schema tests.

### OQ-027 — How should contradictory research pieces coexist? [P1]

**Question.** Can a provenance-aware research graph retain conflicting results without premature winner-take-all resolution?

**Dependencies:** OQ-026, OQ-015.  
**Approach:** Typed claim relations, contested status, independent replication, and scoped reconciliation.  
**Counter-evidence:** The registry silently suppresses valid negative evidence.  
**Relay output:** Contradiction-handling protocol and sample research graph.

### OQ-028 — How can credit, versioning, and research sovereignty be preserved? [P1]

**Question.** Which attribution and change-management rules enable open relay while respecting contributors, datasets, licenses, and independent interpretations?

**Dependencies:** OQ-026–027.  
**Approach:** Versioned contribution records, provenance, licensing review, and explicit attribution policies.  
**Counter-evidence:** Contributions are merged without traceable authorship or consent where required.  
**Relay output:** Governance and contribution templates.

### OQ-029 — How do we measure the usefulness of Open Research Relay? [P1]

**Question.** Does an RRP-based workflow improve reproducibility, counterexample discovery, collaboration efficiency, or research reuse relative to ordinary narrative sharing?

**Dependencies:** OQ-026–028.  
**Approach:** Comparative multi-team study with preregistered outcome metrics.  
**Counter-evidence:** Additional formalism creates overhead without measurable benefits.  
**Relay output:** Evaluation protocol and transparent results.

## 10. Cross-Cutting Proof Obligations

Before presenting a formal result as established, document:

1. **Definitions:** types, state spaces, observables, and admissible contexts.
2. **Assumptions:** stationarity, observability, independence, resource bounds, and time horizon.
3. **Quantifiers:** whether a result is universal, distributional, local, or finite-sample.
4. **Error model:** deterministic tolerance, probabilistic confidence, or approximation metric.
5. **Composition boundary:** what is and is not guaranteed under relay.
6. **Evolution boundary:** whether learning or structural rewrites invalidate the result.
7. **Counterexamples:** minimal examples that fail when assumptions are relaxed.
8. **Reproducibility:** executable tests or a complete proof artifact, as applicable.

A candidate theorem should never be promoted to a theorem merely because simulations support it.

## 11. Research Priority and Dependency Map

| Wave | Questions | Deliverable | Exit criterion |
|---|---|---|---|
| P0-A: Semantics | OQ-001, 005, 009, 013, 026 | Typed contracts and comparison semantics | Independent reviewers can distinguish claims and validate records |
| P0-B: Evidence | OQ-002, 006, 010, 015, 017, 019, 021 | Counterexamples, indexes, audit protocol | At least one reproducible test for each claim type |
| P1-A: Composition | OQ-003, 004, 007, 008, 011, 012, 014, 016 | Conditional theorems and integration tests | Explicit assumptions and failure conditions |
| P1-B: Evolution & relay | OQ-018, 020, 022, 027, 028, 029 | Comparative experiments and governance templates | Baselines, costs, negative findings documented |
| P2: Biology | OQ-023, 024, 025 | Competing biological models and study designs | Discriminating, ethically valid tests specified |

The waves may proceed in parallel when prerequisites are met. No timeline or result is guaranteed.

## 12. Minimal Experimental Packages

**Package A — Perspective-masked model selection.** Use fixed task sets, versioned model configurations, multiple perspectives, paired replays, and separate score/decision/trajectory/learning fields. Report uncertainty and operational cost. Links: OQ-001–008; CASE-001.

**Package B — Relay substitution.** Compare candidate units under a declared \(\Gamma\), insert them into the same relay graph, and test safety, latency, behavior, and drift. Links: OQ-009–016; CASE-002.

**Package C — RSI/UIERU governance.** Instrument a bounded self-improvement workflow; compare independent evaluator outcomes, auditability, and governance overhead. Links: OQ-017–022. Do not treat structural transparency as proof of internal neural interpretability.

**Package D — Biological model competition.** Compare fixed, reweighted, and dynamically reorganized functional models on held-out observations and, where ethically appropriate, causal perturbations. Links: OQ-023–025; CASE-003.

**Package E — Research relay usability.** Give independent teams the same research question through conventional prose versus structured RRPs; compare reproduction quality and discovery of invalid assumptions. Links: OQ-026–029.

All numerical examples in related cases are illustrative unless explicitly sourced from real measurements.

## 13. Research Relay Submission Template

```yaml
research_relay_piece:
  id: "BUI-RRP-EXAMPLE-001"
  title: "Conditional Decision Preservation under Perspective Masking"
  version: "0.1.0"
  status: "open_hypothesis"
  linked_open_questions: ["OQ-001", "OQ-004"]
  authors: []
  problem:
    statement: "State a precise decision-preservation condition."
    scope: "Finite action set and declared context distribution"
  model:
    definitions: []
    assumptions: []
    observation_mode: "observational_projection"
  hypotheses:
    - id: "H1"
      claim: "Decision is preserved under a bounded score-error and margin condition."
      epistemic_status: "candidate_proposition"
  evidence:
    supporting: []
    counter_evidence: []
    provenance: []
  validation:
    proof_obligations: []
    test_plan: []
    failure_conditions: []
  interfaces:
    inputs: []
    outputs: []
    dependencies: ["SPEC-002", "SPEC-004"]
  governance:
    review_status: "not_reviewed"
    limitations: []
  lineage:
    derived_from: []
    supersedes: []
```

A valid submission may consist of a **counterexample only**, provided it clearly identifies the claim being challenged and supplies reproducible conditions.

## 14. Recommended Entry Points by Discipline

- **Mathematics / formal methods:** OQ-001–004, 009–013, 018; RELAY-001–003.
- **Databases / information retrieval:** OQ-005–008; BUI-003, BUI-004, SPEC-003.
- **LLM agents / RSI:** OQ-017–022; CASE-001, RELAY-005, SPEC-001–004.
- **Neuroscience / cognitive science:** OQ-023–025; BUI-007, CASE-003, RELAY-004.
- **Research infrastructure / governance:** OQ-015, 026–029; BUI-008, SPEC-004, RESEARCH-COLLABORATION.

## 15. Relationship to Repository Documents

- **Foundations:** `docs/BUI-001` through `docs/BUI-008` (use the full `.md` filenames listed in `CONTENTS.md`).
- **Worked cases:** `cases/CASE-001` through `cases/CASE-003`.
- **Research questions by domain:** `research-relay/RELAY-001` through `research-relay/RELAY-005`.
- **Formal interfaces:** `specs/SPEC-001` through `specs/SPEC-004`.
- **Future agenda:** [`FUTURE-DIRECTIONS.md`](FUTURE-DIRECTIONS.md).
- **Validation program:** `TESTABLE-HYPOTHESES.md` and `VALIDATION-ROADMAP.md` (planned companion documents).
- **Collaboration protocol:** [`research-relay/RESEARCH-COLLABORATION.md`](research-relay/RESEARCH-COLLABORATION.md).

The proposed **RSI–UIERU Convergence and Structural Governance** research line is included in OQ-019–022; a dedicated `RELAY-006` may be added in a later release. It is not assumed to exist in v1.0.0.

## 16. Closing Perspective

BUI-DSI is intended to be an **open, revisable research program**, not a finished theory of dynamic intelligence. Its most useful output may be a rigorously defined problem, a decisive counterexample, a transferable observation schema, or an independently reproducible experiment.

The central question is not whether every intelligent system can be described as a UIERU. It is **where UIERU-like abstractions yield explanatory, predictive, compositional, or governance advantages—and where they fail**.

---

**Citation / attribution:** Sizhe Tan & GPT-Obot, *Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay*, v1.0.0, `OPEN-QUESTIONS.md`. Refer to `CITATION.cff` when available for repository-level citation metadata.

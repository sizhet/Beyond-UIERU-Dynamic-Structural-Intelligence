# Testable Hypotheses — Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay

**Version:** 1.0.0  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Proposed research hypotheses; not empirical findings  
**Companion documents:** [OPEN-QUESTIONS.md](OPEN-QUESTIONS.md) · [FUTURE-DIRECTIONS.md](FUTURE-DIRECTIONS.md) · [VALIDATION-ROADMAP.md](VALIDATION-ROADMAP.md) (planned)

## Abstract

This document converts the BUI-DSI research agenda into falsifiable hypotheses and reproducible study designs. The central concern is not whether a structural vocabulary can describe intelligent behavior after the fact, but whether perspective-aware observation, dynamic differential localization, contract-based composition, and evidence-governed evolution yield measurable advantages under controlled conditions. Every hypothesis specifies a baseline, intervention, measurable outcome, disconfirmation rule, and principal confounders. None is presented as validated. Formal mathematical conjectures require proofs or counterexamples and are distinguished from empirical hypotheses.

## 1. Research discipline and scope

BUI-DSI studies dynamic intelligence units whose scoring, decisions, actions, feedback, learning, and relay relationships may change over time. The framework proposes explicit interfaces for observing and comparing such units; it does not claim that all intelligence systems implement UIERU internally.

A valid evaluation must:

1. Pre-register the task distribution, unit of analysis, comparison conditions, primary metric, and stopping rule.
2. Record perspective, context, observation window, history, version, provenance, and missingness.
3. Separate **observational projection**, **deterministic replay**, **simulation**, **intervention**, and **counterfactual estimation**.
4. Distinguish scoring differences from decision, trajectory, and learning differences.
5. Compare against credible baselines at comparable resource budgets.
6. Publish null and negative results, contract violations, and counter-evidence.
7. Reassess claims after model updates, context shifts, or changes in evaluation criteria.

**Terminology:** An *effect* is a measured difference under a specified protocol, not automatically a causal effect. A *contract* is an explicit statement of assumptions and guarantees, not proof that an implementation satisfies them. A *research relay piece* (RRP) is a portable, versioned research claim or problem with evidence and validation interfaces.

## 2. Common experimental infrastructure

### 2.1 Experimental objects

- **Units:** LLM agents, tool-using workflows, or other dynamic decision units with instrumentable interfaces.
- **Tasks:** heterogeneous benchmark tasks with varied quality, cost, latency, safety, and long-horizon requirements.
- **Perspectives:** explicit, versioned objective and constraint configurations, including conflicting priorities.
- **Environments:** deterministic replay fixtures where feasible and live or stochastic settings for external-validity checks.
- **Events:** input, observation, score, candidate action, selected action, execution result, feedback, proposed update, approved update, and subsequent performance.

### 2.2 Baseline families

| ID | Baseline | What it controls |
|---|---|---|
| B0 | Static single-policy agent | No perspective-aware selection or structural evolution |
| B1 | Conventional weighted-score router | Simple preference adaptation without explicit masking contract |
| B2 | Full-scan event comparison | No differential index or incremental localization |
| B3 | Interface-only component substitution | No dynamic behavioral or history-aware verification |
| B4 | Unconstrained candidate-search loop | RSI-style improvement without explicit structural governance |
| B5 | Standard experiment registry | Research sharing without structured RRP dependency and counter-evidence links |

Use only baselines appropriate to the hypothesis. Stronger contemporary methods should be added where available; the above are experimental categories, not claims about the state of the art.

### 2.3 Common measurements

- **Decision quality:** task-specific outcome and calibrated regret against an available reference policy.
- **Reliability:** contract violation rate, severity-weighted failures, recovery time, and false acceptance rate.
- **Efficiency:** wall-clock latency, compute, token/API cost, storage, and human review effort.
- **Localization:** precision, recall, top-k hit rate, time to identify a change, and index freshness.
- **Explanatory utility:** blinded investigator success in identifying the decisive factor and reproducing a decision; not a claim of interpreting neural internals.
- **Evolution:** held-out improvement, regression rate, evaluator drift, novelty, rollback success, and performance persistence.
- **Research relay:** independent replication success, time to reproduce, provenance completeness, and counter-evidence propagation.

## 3. Hypothesis register

| ID | Hypothesis | Primary evaluation | Related research |
|---|---|---|---|
| H-001 | Explicit perspective contracts improve decision auditability | Blinded decision-reconstruction study | BUI-002; SPEC-002 |
| H-002 | Masked rescoring predicts decisions only within stated validity conditions | Replay versus live intervention | RELAY-001 |
| H-003 | Four-layer differentials reduce false learning attributions | Controlled perturbation study | BUI-003; SPEC-003 |
| H-004 | PDT improves change localization at bounded index cost | Indexed versus full scan | BUI-003 |
| H-005 | PASQ increases correct cross-perspective retrieval | Query benchmark | BUI-004; SPEC-003 |
| H-006 | Conditioned equivalence predicts substitution failures better than interface checks | Relay replacement test | RELAY-002; CASE-002 |
| H-007 | Contract-aware composition reduces system-level violations | Multi-unit integration test | RELAY-003 |
| H-008 | Two-way counter-evidence relay shortens failure containment | Fault-injection study | RELAY-003 |
| H-009 | Governed structural evolution improves held-out robustness | Matched-budget evolution study | RELAY-005 |
| H-010 | Repeated execution becomes useful evidence relay when provenance and selection are preserved | Experience reuse study | RELAY-005 |
| H-011 | UIERU-style observation increases RSI auditability without requiring model internals | LLM-agent RSI study | RSI–UIERU convergence |
| H-012 | RSI candidate generation plus contract governance improves safe improvement yield | Factorial comparison | RSI–UIERU convergence |
| H-013 | Dynamic coalition models predict selected biological context effects better than fixed-function baselines | Neural/behavioral model comparison | RELAY-004 |
| H-014 | RRP contracts improve independent research replication | Cross-team replication study | SPEC-004 |
| H-015 | Versioned counter-evidence links reduce persistence of invalidated claims | Research workflow simulation | BUI-008; SPEC-004 |

The register is a starting set, not a complete enumeration of the 29 open questions in `OPEN-QUESTIONS.md`. Identifier mappings are thematic; precise OQ crosswalks should be checked when the repository is integrated.

## 4. H-001 — Perspective contracts and auditability

**Claim.** Explicit perspective and masking contracts enable investigators to reconstruct and explain recorded model-selection decisions more accurately than equally detailed but unstructured logs.

**Design.** Randomly assign blinded reviewers to structured-contract or flat-log conditions, using identical underlying decisions and information access. Include cases where the perspective changes the winner and cases where it does not.

**Primary outcome.** Correct identification of the decisive constraints and selected option. **Secondary:** reconstruction time, confidence calibration, disagreement, and reviewer workload.

**Disconfirmation.** No meaningful gain over well-structured conventional logs, or gains explained entirely by additional information rather than representation. **Threats:** reviewer training, interface familiarity, and post hoc explanations.

## 5. H-002 — Limits of masked rescoring

**Claim.** Observational perspective rescoring predicts replayed choices when candidate sets, scoring inputs, tie-breaking, and policy versions are held fixed; its accuracy deteriorates under unmodeled interventions or history-dependent policy changes.

**Design.** Compare (A) offline rescoring, (B) deterministic replay, and (C) actual intervention across controlled and history-dependent tasks. Pre-specify the eligible inference type for each comparison.

**Primary outcome.** Agreement rate between predicted and observed decisions, stratified by assumption satisfaction.

**Disconfirmation.** Persistent disagreement even under verified deterministic assumptions, or no association between assumption violations and predictive degradation. **Threats:** hidden state, non-deterministic APIs, caching, tool side effects.

## 6. H-003 — Four-layer differential attribution

**Claim.** Recording separate scoring, decision, trajectory, and learning differentials reduces erroneous attribution of observed changes to learning.

**Design.** Introduce known perturbations: score-only changes, decision-policy changes, tool-execution changes, and persistent policy updates. Ask evaluators to identify the source using either one generic difference field or the four-layer schema.

**Primary outcome.** False-positive learning attribution rate. **Secondary:** detection sensitivity and investigator time.

**Disconfirmation.** No reduction after controlling for event detail and reviewer effort. **Threats:** correlated interventions and incomplete learning-state visibility.

## 7. H-004 — Perspective Differential Tree efficiency

**Claim.** A maintained PDT can identify relevant changes faster than a full event scan while retaining a specified top-k recall target.

**Design.** Generate event streams with controlled change frequency, branch density, perspective cardinality, and update rate. Compare PDT and full-scan search at identical hardware and correctness targets.

**Primary outcome.** Query latency at predeclared recall. **Secondary:** index build cost, update overhead, memory, stale-result frequency.

**Disconfirmation.** No net benefit at realistic update rates or unacceptable freshness loss. **Threats:** synthetic workloads that favor tree locality.

## 8. H-005 — Perspective-Aware Structural Query correctness

**Claim.** Explicit context, history, and perspective predicates in PASQ reduce invalid cross-perspective comparisons relative to conventional queries lacking these constraints.

**Design.** Build a benchmark of valid and invalid comparison requests with adjudicated ground truth. Compare PASQ-constrained queries with ordinary SQL written against the same data, controlling analyst expertise.

**Primary outcome.** Invalid-comparison acceptance rate. **Secondary:** query completeness, execution cost, authoring time.

**Disconfirmation.** No improvement, or improvement achievable by equivalent conventional schema constraints without PASQ-specific abstractions. **Threats:** benchmark leakage and schema familiarity.

## 9. H-006 — Conditional dynamic equivalence and substitution

**Claim.** Context-, perspective-, and history-conditioned equivalence tests predict relay substitution failures more accurately than interface compatibility tests alone.

**Design.** Pair units that share an interface but differ in statefulness, failure recovery, resource use, or learning behavior. Estimate equivalence on a calibration set and evaluate replacements on held-out contexts.

**Primary outcome.** False acceptance of unsafe or contract-violating substitutions. **Secondary:** false rejection and testing cost.

**Disconfirmation.** No reduction at matched testing budgets, or systematic failures outside the model's validity region. **Threats:** incomplete environment coverage and drift.

## 10. H-007 — Composition contract preservation

**Claim.** Assume–guarantee checks and explicit interface contracts reduce system-level violations in composed UIERU-like workflows compared with interface-only assembly.

**Design.** Construct multi-unit relay graphs with controlled dependency conflicts, feedback loops, timing constraints, and privilege boundaries. Randomize use of contract checks.

**Primary outcome.** Severity-weighted system contract violations per completed task. **Secondary:** throughput, false alarms, integration effort.

**Disconfirmation.** No reduction or excessive rejection of valid compositions. **Threats:** contract incompleteness and unrealistic integration scenarios.

## 11. H-008 — Two-way counter-evidence relay

**Claim.** Propagating downstream failures back to upstream unit selection and contract records reduces time to detect and contain repeated failures.

**Design.** Inject faults into a multi-stage relay system. Compare forward-only logging with two-way counter-evidence propagation and controlled rollback.

**Primary outcome.** Time to containment. **Secondary:** repeated failure rate, incorrect upstream blame, rollback cost.

**Disconfirmation.** No containment gain, or high rates of spurious blame and destabilizing rollback. **Threats:** fault-injection realism and monitoring asymmetry.

## 12. H-009 — Governed open structural evolution

**Claim.** At matched candidate-generation and evaluation budgets, contract-checked structural evolution yields a higher rate of persistent held-out improvement with fewer serious regressions than unconstrained candidate adoption.

**Design.** Compare candidate generation with and without sandbox evaluation, counter-evidence review, deployment gates, and rollback. Evaluate across time-separated and shifted test distributions.

**Primary outcome.** Fraction of adopted updates that improve held-out performance without violating safety contracts. **Secondary:** exploration cost, improvement magnitude, diversity, rollback frequency.

**Disconfirmation.** No robustness gain after accounting for extra evaluation resources, or governance suppresses useful improvement without compensating reliability. **Threats:** evaluator overfitting and unequal search budgets.

## 13. H-010 — Repeated execution as evidence relay

**Claim.** Repeated executions improve future selection only when their observations are retained with context, provenance, feedback quality, and a mechanism for incorporating evidence.

**Design.** Compare no-history, raw-history, and provenance-filtered history conditions under repeated tasks and controlled distribution shift.

**Primary outcome.** Held-out decision improvement. **Secondary:** contamination sensitivity, storage cost, recovery from misleading feedback.

**Disconfirmation.** Provenance-filtered history fails to outperform raw or absent history, or performance gains disappear on shifted tasks. **Threats:** memorization and leakage between repeated trials.

**Interpretive constraint.** More executions or a larger log alone do not demonstrate learning or structural growth.

## 14. H-011 — RSI observability and auditability

**Claim.** UIERU-style observation records improve external audit of LLM-agent recursive improvement loops without requiring access to internal model weights or reasoning traces.

**Design.** Instrument an RSI-like workflow at candidate, evaluator, selection, deployment, and rollback boundaries. Compare with standard experiment tracking at equal logging budgets.

**Primary outcome.** Accuracy of reconstructing why an update was accepted or rejected. **Secondary:** provenance completeness, missed evaluator changes, instrumentation overhead.

**Disconfirmation.** No improvement over strong tracking baselines or excessive overhead. **Threats:** selective logging and the distinction between structural and internal-model interpretability.

## 15. H-012 — RSI candidate generation plus UIERU governance

**Claim.** Combining RSI-style candidate generation with structural contracts and counter-evidence governance improves the yield of safe, generalizable updates relative to either component alone.

**Design.** Use a 2×2 factorial design: candidate generator absent/present × governance absent/present. Match overall compute budgets and report tradeoffs between search and evaluation.

**Primary outcome.** Safe improvement yield per unit compute. **Secondary:** false acceptance, novelty, held-out generalization, deployment cost.

**Disconfirmation.** No positive interaction or a negative net effect under realistic budgets. **Threats:** different candidate distributions, evaluator drift, and benchmark saturation.

## 16. H-013 — Biological dynamic organization

**Claim.** In a specified context-switching biological task, a dynamic functional-coalition model predicts held-out behavioral or neural dynamics better than matched-complexity fixed-function and context-reweighting baselines.

**Design.** Use an independently collected or established dataset with repeated context switches, held-out sessions, and, if available, perturbation data. Compare predictive performance with complexity controls and preregistered model selection.

**Primary outcome.** Held-out predictive log likelihood or task-appropriate prediction error. **Secondary:** generalization across contexts and perturbation response.

**Disconfirmation.** Dynamic coalition model does not outperform baselines after complexity adjustment, or its purported functional boundaries are unstable artifacts of analysis.

**Critical limitation.** Even positive evidence supports a comparative model, not a claim that biological brains literally implement UIERUs.

## 17. H-014 — Research Relay Piece reproducibility

**Claim.** Structured RRP contracts increase independent replication success and reduce reconstruction time compared with conventional unstructured research notes of similar informational completeness.

**Design.** Randomize external teams to RRP versus conventional documentation packages for the same small experiments. Blind adjudicators to condition.

**Primary outcome.** Replication of the prespecified analysis and outcome within declared tolerances. **Secondary:** time, clarification requests, provenance defects, interpretation disagreements.

**Disconfirmation.** No improvement at comparable documentation effort, or RRP fields introduce ambiguity and overhead. **Threats:** team skill imbalance and experiment difficulty.

## 18. H-015 — Counter-evidence lineage and correction

**Claim.** Versioned research dependencies and counter-evidence links reduce the persistence of invalidated downstream claims.

**Design.** Simulate or study a collaborative research network where an upstream assumption is invalidated. Compare ordinary document notification with structured RRP dependency propagation.

**Primary outcome.** Fraction of affected claims correctly flagged within a fixed review window. **Secondary:** time to correction, false alerts, missed dependencies.

**Disconfirmation.** No improvement or excessive false-positive propagation. **Threats:** incomplete dependency mapping and researcher notification fatigue.

## 19. Mathematical conjectures: separate proof track

The following are **not** empirical hypotheses and should not be evaluated solely by benchmark scores:

- **MC-001 — Projection idempotence:** Under an explicitly defined pure projection semantics, applying the same projection twice yields the same result. Identify precisely which mask operators satisfy this property.
- **MC-002 — Conditional commutativity:** Characterize when two perspective masks commute, and construct counterexamples involving stateful interventions.
- **MC-003 — Query preservation:** Give necessary or sufficient conditions under which a PASQ query result is invariant under a specified masking operation.
- **MC-004 — Substitution preservation:** Establish sufficient conditions for a local approximate behavioral relation to preserve a global relay contract, with explicit error bounds.
- **MC-005 — Evolution stability:** Determine conditions under which a previously certified equivalence relation remains valid after learning or structural modification.

**Acceptance criteria:** formal definitions, stated assumptions, proof or executable counterexample, boundary cases, and an independent check. A failed conjecture should be retained with its counterexample and revised scope.

## 20. Statistical and methodological plan

### 20.1 Pre-registration

Each study should publish: primary endpoint, target population, sample unit, randomization procedure, exclusions, minimum meaningful effect, statistical model, confidence or uncertainty interval, and planned sensitivity analyses. Report exploratory findings separately.

### 20.2 Power and sample size

No universal sample size is defensible across these heterogeneous tasks. Determine sample size from pilot variance, clustering by task/unit, target effect size, and desired power. For agent experiments, avoid treating repeated runs on the same prompt as independent task samples.

### 20.3 Multiple comparisons

Declare primary outcomes in advance. For hypothesis families with many metrics or perspectives, use a suitable multiplicity-control or hierarchical analysis; publish all measured endpoints to prevent selective reporting.

### 20.4 Reproducibility

Record model/provider versions, prompts or equivalent policies when releasable, environment snapshots, random seeds, task IDs, tool versions, scoring code, timestamps, and redaction rules. When proprietary systems prevent complete disclosure, mark the reproducibility limitation explicitly.

### 20.5 Distribution shift

Evaluate at least one out-of-distribution or time-separated test set for claims of robust improvement. Treat drift-triggered contract expiry as an expected governance behavior, not necessarily an implementation defect.

### 20.6 Causal interpretation

Use random assignment or justified causal identification for intervention claims. Replay agreement and observational association alone do not establish causality.

## 21. Evidence grading and claim lifecycle

| Status | Meaning | Allowed conclusion |
|---|---|---|
| Proposed | Hypothesis and protocol specified | Research question is testable |
| Piloted | Feasibility and instrumentation checked | Preliminary, not confirmatory |
| Tested | Preregistered experiment executed | Effect estimate with limitations |
| Replicated | Independent confirmation in stated conditions | Conditional empirical support |
| Contested | Counter-evidence or conflicting replication | Claim requires review |
| Revised | Scope, model, or protocol updated | New version supersedes prior claim |
| Rejected | Evidence contradicts the stated claim under valid test | Retain negative result and failure conditions |

Do not equate “replicated” with universal truth; scope and distribution remain part of every claim.

## 22. Example hypothesis record

```yaml
hypothesis_id: H-006
version: 1.0.0
status: proposed
claim: >
  Context- and history-conditioned equivalence testing reduces
  false acceptance of unsafe relay substitutions.
research_area: dynamic_behavioral_equivalence
source_documents:
  - research-relay/RELAY-002-Dynamic-Behavioral-Equivalence.md
  - cases/CASE-002-Dynamic-Equivalence-and-Relay-Substitution.md
unit_of_analysis: relay_substitution_attempt
baseline: interface_compatibility_only
intervention: conditional_equivalence_contract
primary_endpoint: false_acceptance_rate
comparison_scope:
  perspectives: [quality, latency, reliability]
  contexts: pre_registered_test_scenarios
  history_window: explicitly_recorded
  validity_horizon: version_and_context_bounded
counter_evidence:
  - matched_budget_no_reduction_in_false_acceptance
  - systematic_failures_outside_declared_validity_region
provenance:
  dataset_version: to_be_assigned
  evaluator_version: to_be_assigned
  protocol_registration: to_be_assigned
outputs:
  - raw_event_log
  - comparison_contracts
  - effect_estimates
  - negative_results
  - replication_instructions
```

## 23. Priority and dependency roadmap

| Phase | Initial focus | Rationale |
|---|---|---|
| P0 — Semantics | H-002, H-003; MC-001–003 | Ensure observation and comparison claims are well formed |
| P1 — Instrumentation | H-001, H-004, H-005 | Establish auditability, indexing, and query benchmarks |
| P2 — Composition | H-006, H-007, H-008; MC-004 | Test conditional substitution and relay guarantees |
| P3 — Evolution | H-009, H-010, H-011, H-012; MC-005 | Examine learning, RSI, and governance under drift |
| P4 — Cross-domain | H-013 | Compare biological hypotheses without presupposing mechanism |
| P5 — Research relay | H-014, H-015 | Validate whether the collaboration contract helps other researchers |

Phases express logical dependencies, not a promise of calendar dates. Small parallel studies are encouraged where dependencies permit.

## 24. Counter-evidence reporting template

Every result that challenges a hypothesis should record:

- Hypothesis and protocol version;
- Context, perspective, history, and model versions;
- Observed result and uncertainty;
- Assumptions tested and possible violations;
- Reproduction artifacts and provenance;
- Severity and affected downstream claims;
- Proposed response: replicate, narrow scope, revise, suspend, or reject.

Counter-evidence is a first-class research output. A well-supported negative result can be more useful than an unqualified success report.

## 25. Relationship to the BUI-DSI repository

- **BUI-001–008:** conceptual framework and open research horizon.
- **CASE-001–003:** concrete settings and failure modes.
- **RELAY-001–005:** disciplinary research questions; the proposed RSI–UIERU RELAY-006 remains a future extension.
- **SPEC-001:** observation semantics and provenance.
- **SPEC-002:** masking and operation contracts.
- **SPEC-003:** differential and query schemas.
- **SPEC-004:** portable research relay piece contract.
- **OPEN-QUESTIONS.md:** broader question inventory; this file provides operational hypotheses.
- **VALIDATION-ROADMAP.md:** planned implementation sequencing, benchmarks, gates, and release criteria.

## 26. Closing perspective

The goal is not to confirm BUI-DSI by selecting favorable demonstrations. It is to identify precisely where perspective-aware structural observation, conditional equivalence, relay contracts, and governed evolution work, where they fail, and which assumptions explain the difference. A research ecosystem becomes more reliable when it can relay both successful findings and reasons to change its mind.

---

**Suggested citation:** Sizhe Tan & GPT-Obot (2026). *Testable Hypotheses — Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay*. Version 1.0.0. Research agenda; hypotheses not yet validated.

# Validation Roadmap — Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay

**Version:** 1.0.0  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Proposed research and validation roadmap; not a report of completed experiments  
**Repository:** `Beyond-UIERU-Dynamic-Structural-Intelligence`  
**Companion documents:** [OPEN-QUESTIONS.md](OPEN-QUESTIONS.md) · [TESTABLE-HYPOTHESES.md](TESTABLE-HYPOTHESES.md) · [FUTURE-DIRECTIONS.md](FUTURE-DIRECTIONS.md) · [RESEARCH-COLLABORATION.md](research-relay/RESEARCH-COLLABORATION.md)

---

## 1. Purpose and epistemic scope

This roadmap translates the BUI-DSI research program into staged, falsifiable, reproducible work. It is designed to help researchers distinguish a useful conceptual framework from an empirically supported system, and a candidate mathematical claim from a proven result.

BUI-DSI investigates dynamic Universal Intelligence Evolution and Relay Units (UIERUs), perspective-conditioned observation and comparison, dynamic behavioral equivalence, compositional relay, open structural evolution, and the transfer of research problems through Open Research Relay.

**No validation result is claimed by this document.** Numerical thresholds below are proposed preregistration defaults, not established performance figures. Any adopted threshold must be frozen before confirmatory evaluation and justified for its application.

### 1.1 Validation principles

1. **Separate observation from explanation:** visible behavior does not establish an internal mechanism.
2. **Separate replay from intervention:** recomputing a decision under an alternative perspective does not demonstrate the outcome of actually deploying it.
3. **Separate score, decision, trajectory, and learning:** improvement in one layer does not prove improvement in another.
4. **Scope every equivalence claim:** specify perspective, context, history, horizon, tolerance, contract, and evidence.
5. **Preserve counter-evidence:** failed tests and invalidated hypotheses remain first-class research outputs.
6. **Protect evaluator independence:** distinguish the mechanism proposing an improvement from the mechanism judging it.
7. **Require lineage:** record software, data, prompts, model versions, contracts, and experimental conditions.
8. **Prefer staged deployment:** offline analysis precedes sandbox interventions; high-impact deployments require independent approval.

---

## 2. Research objects and evidence levels

### 2.1 Core research objects

| Object | Question | Primary artifact |
|---|---|---|
| Dynamic UIERU observation | What happened, under which conditions? | Versioned observation record (`SPEC-001`) |
| Perspective masking | Which observations or computations are visible or modified? | Typed mask contract (`SPEC-002`) |
| Dynamic differential | What changed across conditions? | Scoring/decision/trajectory/learning differential (`SPEC-003`) |
| PDT and PASQ | Can differences be indexed and retrieved accurately? | Query schema, index, query result with provenance |
| Dynamic equivalence | When can units be treated as behaviorally similar? | Scoped equivalence claim and tests |
| Relay composition | Do local guarantees survive composition? | Assume–guarantee contracts and integration tests |
| Open structural evolution | Does a structural change improve generalizable outcomes? | Versioned candidate, evaluator report, rollback record |
| Open Research Relay | Can independent researchers inherit and challenge a problem? | Research Relay Piece (`SPEC-004`) |

### 2.2 Evidence ladder

- **E0 — Proposal:** definitions, diagrams, or hypotheses only.
- **E1 — Internal consistency:** schema validation, worked examples, and executable checks.
- **E2 — Controlled simulation:** synthetic benchmarks with known ground truth.
- **E3 — Independent replication:** separate implementation or research team reproduces findings.
- **E4 — External validity:** heterogeneous real workloads, datasets, or environments.
- **E5 — Governed operational evidence:** monitored deployment within an explicit safety and review boundary.

Progress along this ladder is claim-specific; a project cannot receive a single universal “validated” label. Mathematical theorems additionally require proof review, while neuroscience claims require appropriate empirical evidence.

---

## 3. Program structure and dependencies

```text
P0  Definitions, contracts, and provenance
 |\
 | +--> P1  Minimal executable observations and masks
 |         |\
 |         | +--> P2  Differential indexing and PASQ
 |         |          \
 |         +----------> P3  Equivalence and relay composition
 |                         \
 |                          +--> P4  Structural evolution and RSI governance
 |                          |
 +--------------------------+--> P5  Biological comparative studies
                              \
                               P6  Independent Open Research Relay
```

The phases are **dependency-based**, not calendar promises. Workstreams may proceed in parallel when prerequisite contracts are stable.

---

## 4. P0 — Semantic foundations and preregistration

**Objective:** eliminate ambiguous claims before writing experiments.

### Tasks

- Freeze a candidate vocabulary for *perspective*, *context*, *history*, *mask*, *observation*, *intervention*, *contract*, *equivalence*, and *structural growth*.
- Map each claim in `OPEN-QUESTIONS.md` to a hypothesis or a formal proof obligation.
- Specify admissible evidence and known counterexamples for each claim.
- Define a canonical observation identity: unit/version, run, time, perspective, context, history snapshot, evaluator, and provenance.
- Identify sensitive or proprietary fields and their redaction policies.
- Record preregistered primary metrics, comparison baselines, stopping rules, and negative-result reporting requirements.

**Deliverables:** terminology freeze candidate, schema examples, claims register, preregistration template, and risk register.

**Exit criteria:** independent reviewers can distinguish observation, replay, simulation, intervention, and counterfactual estimates from each example; no hypothesis is labeled a theorem without proof.

**Failure trigger:** two implementers derive incompatible operational meanings from the same supposedly normative field.

---

## 5. P1 — Minimal executable observation and masking

**Objective:** establish that dynamic UIERU-like systems can be recorded and perspective-masked reproducibly.

### Minimal testbed

Use a small tool-using agent or model router with two or more candidate models, at least three perspectives (e.g., quality, latency, cost), fixed task inputs, and versioned scoring policies. This is an engineering proxy, **not proof that any LLM internally implements a UIERU**.

### Experimental conditions

- **B0:** ordinary application logs without the proposed observation schema.
- **B1:** `SPEC-001` structured observations, no masking.
- **T1:** structured observations plus typed `SPEC-002` perspective masks.
- **T2:** same as T1, but with deliberately incomplete provenance or shifted context to test rejection behavior.

### Measures

- Schema validity and field completeness.
- Deterministic replay agreement under pinned dependencies.
- Correct distinction of observed and inferred values.
- Mask information leakage and redaction violations.
- Auditor accuracy and time to reconstruct a decision path.
- Runtime and storage overhead.

**Suggested acceptance gate:** all safety-critical validation rules pass; deterministic replay discrepancies are either eliminated or explicitly classified; no unsupported causal claim is emitted by the reporting layer. Do not replace these requirements with an arbitrary aggregate score.

**Deliverables:** minimal reference traces, masking examples, replay scripts or procedures, and a negative-test corpus.

---

## 6. P2 — Dynamic differentials, PDT, and PASQ

**Objective:** test whether structural indexing and query semantics faithfully expose perspective-conditioned differences.

### Experimental matrix

Vary one factor at a time where feasible: perspective, context, scoring weights, candidate set, history, evaluator version, and learning update. Include factorial experiments to identify interactions.

### Differential classes

1. **Scoring differential:** change in score vectors or ranking.
2. **Decision differential:** change in selected action/model or policy branch.
3. **Trajectory differential:** change in realized sequences, outcomes, and costs.
4. **Learning differential:** change in subsequent policy, structure, or behavior attributable to an update under specified assumptions.

### Baselines

- Full trace scan with explicit filters.
- Conventional relational queries without perspective-aware indexing.
- PDT/PASQ implementation under the same hardware and data volume.

### Measures

Query precision/recall against a manually verified or synthetic oracle; false differential rate; provenance completeness; latency, storage, update cost, and index staleness; detection of confounded comparisons.

**Exit criteria:** differential results agree with a trusted oracle on preregistered tests, carry their comparison contracts, and expose invalid or incomparable pairs rather than silently treating them as equal.

**Counterexample probes:** hidden history changes, aggregation reversals, evaluator drift, missing observations, and noncommuting mask operations.

---

## 7. P3 — Dynamic equivalence and relay composition

**Objective:** identify when local similarity supports substitution and when composition invalidates it.

### Study A: scoped behavioral equivalence

Construct paired units with (i) different internals but matched task behavior, (ii) identical interfaces but different tail risks, and (iii) initially similar behavior that diverges after learning. Define the context distribution, observation horizon, tolerances, and contract before comparing them.

Candidate distances may include task-conditioned outcome divergence, trajectory distribution distance, resource deviation, and contract violation probability. A small observed distance is evidence of similarity only **under the specified test distribution and horizon**.

### Study B: relay substitution

Replace a unit inside a two- or three-stage relay graph while holding other components fixed. Compare local acceptance tests with end-to-end system properties. Add feedback loops, timeouts, retries, and upstream/downstream perspective mismatches.

### Formal proof obligations

- State the assumptions under which observational equivalence is reflexive, symmetric, or transitive.
- Define an appropriate approximate bisimulation or simulation relation for selected restricted systems.
- Determine whether substitution preserves contracts under stated environment assumptions.
- Construct counterexamples when contract preservation fails.

**Deliverables:** equivalence benchmark, substitution counterexample catalog, assume–guarantee templates, and reviewed formal statements.

**Exit criteria:** no unconditional substitution claim; each accepted substitution includes explicit validity conditions, uncertainty, revocation triggers, and rollback provisions.

---

## 8. P4 — Open structural evolution and RSI–UIERU convergence

**Objective:** test whether structural governance improves the reliability of proposed self-improvements without conflating search success with general intelligence growth.

### Evolution operators

Test controlled variants of ADD, REPLACE, COMPOSE, SPLIT, MERGE, REWIRE, REWEIGHT, LOCALIZE, IMPORT, and RETIRE. Every candidate is assigned a lineage identifier and a rollback path.

### RSI comparison arms

| Arm | Candidate generation | Evaluation and governance |
|---|---|---|
| R0 | Fixed human-defined baseline | Fixed benchmark and review |
| R1 | LLM/RSI candidate generation | Ordinary evaluator loop |
| R2 | Same candidate generator as R1 | UIERU-like explicit contracts, provenance, counter-evidence, sandbox gates |
| R3 | Non-LLM search baseline | Same governance as R2 |

Control compute budget, evaluator access, task mix, and candidate count. Separate training/development tasks from held-out tasks and independent red-team evaluations.

### Primary outcomes

- Held-out task performance and regression frequency.
- Contract violation rate and severity.
- Improvement persistence after environment or perspective shift.
- Auditor reconstruction accuracy and review effort.
- Evaluator exploitation and Goodhart failure rate.
- Compute and human-review cost per accepted, independently verified improvement.

### Safety gates

All candidate changes run in a bounded sandbox with tool permissions and resource quotas. High-impact actions, deployment, or self-modification require explicit authorization. Evaluation must be capable of rejecting changes that increase benchmark score while violating safety or contract constraints.

**Exit criteria:** any asserted benefit of R2 over R1 is supported by independent, held-out evaluation and reported with uncertainty and costs. Null or negative results remain publishable.

---

## 9. P5 — Biological dynamic intelligence: comparative validation

**Objective:** determine whether UIERU-inspired abstractions yield testable predictions or useful analysis, without claiming biological identity.

### Competing models

- **M1:** fixed functional modules.
- **M2:** fixed connectivity with context-dependent reweighting.
- **M3:** dynamically reconfigured functional coalitions.

Select a concrete task such as context-dependent choice, foraging under threat, or switching between exploration and exploitation. Define behavioral observations first; add neural measurements only where available and ethically approved.

### Experiments

1. **Context switch:** measure changes in behavior and predictive model fit.
2. **History and learning:** test whether the same immediate context yields different actions after different experiences.
3. **Intervention:** where ethically and technically feasible, distinguish causal mechanisms from observational associations.
4. **Cross-task generalization:** test whether inferred functional boundaries transfer to unseen contexts.
5. **Engineering transfer:** evaluate whether a biomimetic design improves an artificial system against simpler baselines.

### Critical controls

Match model capacity and regularization; avoid interpreting flexible models' higher training fit as evidence of dynamic biological boundaries. Require out-of-sample prediction, uncertainty reporting, and alternative explanations.

**Exit criteria:** state exactly which model is favored for which dataset and task. Even a successful M3 result does **not** demonstrate that brains literally implement UIERUs, Scoring Forests, or Relay Contracts.

---

## 10. P6 — Open Research Relay and independent reproduction

**Objective:** test whether a structured Research Relay Piece helps another team understand, reproduce, refute, or extend a research problem.

### RRP minimum contract

Each piece must contain:

- **Problem:** precise question and motivation.
- **Model:** definitions, assumptions, scope, and limitations.
- **Hypotheses:** falsifiable empirical claims or clearly labeled proof obligations.
- **Evidence:** supporting results, negative findings, counterexamples, and provenance.
- **Validation:** procedures, baselines, metrics, and rejection criteria.
- **Interfaces:** data/schema dependencies, collaboration entry points, version, and lineage.

Governance and attribution are required metadata, not substitutes for the six core elements.

### Replication trial

Randomly assign independent researchers or teams to a conventional narrative research brief versus an RRP-structured brief of equivalent substantive content. Evaluate time to reconstruct the problem, reproducibility success, correct identification of assumptions, counterexample discovery, and contribution traceability. Report learning effects and disciplinary background.

**Exit criteria:** publish the complete replication protocol and results, including cases where RRP adds overhead or fails to help. Update `SPEC-004` based on those findings.

---

## 11. Hypothesis-to-phase traceability

The following table is a **planning alignment**, not a substitute for the authoritative definitions and exact numbering in [TESTABLE-HYPOTHESES.md](TESTABLE-HYPOTHESES.md).

| Hypothesis IDs | Primary phase | Main evidence type |
|---|---|---|
| H-001–H-002 | P1 | Masking/replay correctness, auditability |
| H-003–H-005 | P2 | Differential fidelity, query accuracy and efficiency |
| H-006–H-008 | P3 | Scoped equivalence and composition tests |
| H-009–H-010 | P4 | Evolution quality, robustness, regression controls |
| H-011–H-012 | P4 | RSI governance and held-out evaluation |
| H-013 | P5 | Comparative biological model evidence |
| H-014–H-015 | P6 | Independent research relay and replication |

Formal propositions from `TESTABLE-HYPOTHESES.md` require separate proof or counterexample work; experimental agreement is not a proof.

---

## 12. Open-question coverage

Use [OPEN-QUESTIONS.md](OPEN-QUESTIONS.md) as the authoritative source for the precise wording and status of OQ-001–OQ-029.

| Question family | Primary phases |
|---|---|
| OQ-001–004: masking algebra | P0–P1, formal work in P3 |
| OQ-005–008: differential/PDT/PASQ | P1–P2 |
| OQ-009–012: dynamic equivalence | P3 |
| OQ-013–016: composition/governance | P3–P4 |
| OQ-017–022: evolution/RSI | P4 |
| OQ-023–025: biological dynamics | P5 |
| OQ-026–029: research relay | P6 |

---

## 13. Preregistration and statistical analysis

For each empirical study, register before confirmatory data collection:

1. Unit of analysis, sampling method, inclusion/exclusion rules, and context distribution.
2. Primary and secondary endpoints, direction of improvement, and smallest practically meaningful effect.
3. Baseline and ablation conditions; compute and human-time budgets.
4. Power or precision rationale; uncertainty intervals and multiplicity handling.
5. Random seeds, repeated-run protocol, and stratification across task difficulty.
6. Handling of missing traces, failed runs, and non-deterministic model outputs.
7. Explicit success, failure, and inconclusive criteria.
8. Data governance, privacy, access restrictions, and responsible release plan.

Prefer effect sizes and confidence/credible intervals to a binary significance label. Report performance distributions and tail failures, not merely averages. Any exploratory analysis must be labeled exploratory.

---

## 14. Counter-evidence and failure taxonomy

| Failure code | Example | Required response |
|---|---|---|
| CE-OBS | Incomplete or misleading observation | Correct schema or narrow claim |
| CE-MASK | Mask leaks information or changes semantics unexpectedly | Revise operator contract |
| CE-CAUSAL | Replay mistaken for intervention | Retract causal interpretation |
| CE-DIFF | False or incomparable differential | Revise comparison contract |
| CE-QUERY | Stale PDT or incorrect PASQ result | Rebuild index and add regression test |
| CE-EQUIV | Similar units diverge outside tested horizon | Narrow or revoke equivalence claim |
| CE-COMP | Local contract passes, system contract fails | Add environmental assumptions and integration checks |
| CE-EVOL | Benchmark gain hides regression or exploitation | Reject candidate, update evaluator |
| CE-BIO | Biological result supports a simpler model | Revise biomimetic hypothesis |
| CE-RELAY | Independent team cannot reproduce claim | Repair RRP and publish replication failure |

Counter-evidence must reference the affected claim IDs and downstream dependencies. A revoked claim is retained with an audit trail rather than silently deleted.

---

## 15. Governance, safety, and evaluator sovereignty

Dynamic systems may generate candidates, but proposal generation does not confer authority to approve or deploy them. The governing actor, whether human or institution, must be explicit in the contract. Evaluation policy changes require versioning and independent review where risk warrants it.

Minimum controls include permission-bounded sandboxes, resource ceilings, audit logs, independent held-out evaluators, rollback tests, incident reporting, and stop conditions for unsafe behavior. Human-subject or animal research requires applicable ethical review and institutional oversight. Privacy-sensitive datasets must be protected; public relay pieces may describe reproducibility procedures without exposing restricted raw data.

**Structural interpretability is not the same as mechanistic interpretability.** An explicit UIERU contract may make selection and relay decisions easier to audit while leaving a neural model's internal computation opaque.

---

## 16. Conformance and reproducibility package

A reproducible study should provide, where licensing and privacy permit:

```text
validation/<study-id>/
├── README.md                 # question, claim IDs, study scope
├── preregistration.md        # frozen protocol and decision rules
├── environment.yaml          # software/hardware/model versions
├── contracts/                # observation, masking, comparison, relay
├── datasets/README.md       # provenance, access, sampling, exclusions
├── traces/README.md         # trace schema and permitted distribution
├── analysis/README.md       # scripts or exact analysis procedures
├── results.md               # effect sizes, uncertainty, negative findings
├── counter-evidence.md      # failures and affected claim IDs
└── relay-piece.yaml          # SPEC-004-compatible research handoff
```

If artifacts cannot be released, record the restriction, reason, and an independently inspectable alternative such as a synthetic fixture or controlled-access procedure.

### Minimal result record

```yaml
study_id: BUI-VAL-EXAMPLE-001
status: proposed  # proposed | preregistered | running | completed | replicated | contested
claims: [H-001]
phase: P1
perspective_contract: specs/SPEC-002-Perspective-Masking-Contract.md
observation_contract: specs/SPEC-001-Dynamic-UIERU-Observation-Model.md
baseline: ordinary_application_logs
intervention: typed_perspective_masking
primary_metric: auditor_decision_reconstruction_accuracy
outcome: null
uncertainty: null
counter_evidence: []
provenance:
  dataset_version: pending
  implementation_version: pending
  evaluator_version: pending
review:
  independent_reviewer: pending
  decision: pending
```

This example is illustrative, not an experimental result.

---

## 17. Decision gates and milestone ledger

| Gate | Evidence required | Decision options |
|---|---|---|
| G0: semantics | Definitions, schemas, preregistration | Proceed / revise |
| G1: observability | Valid records and replay controls | Proceed / narrow / stop |
| G2: comparison | Differential oracle and query tests | Proceed / repair |
| G3: substitutability | Scoped equivalence and integration evidence | Conditional accept / reject |
| G4: evolution | Held-out gains, regressions, governance checks | Sandbox continue / rollback |
| G5: biological relevance | Out-of-sample comparative evidence | Retain / revise / reject analogy |
| G6: open relay | Independent replication or documented failure | Extend / revise contract |

The ledger should store gate owner, decision date, supporting evidence, counter-evidence, and next review trigger. **No phase is considered completed merely because its document exists.**

---

## 18. First five recommended validation packages

**VP-01 — Perspective-Masked Model Selection:** reproduce the conceptual setup of [CASE-001](cases/CASE-001-Perspective-Masked-Model-Selection.md) using pinned model-router traces; evaluate perspective-conditioned rankings and provenance.

**VP-02 — Dynamic Substitution Under Drift:** extend [CASE-002](cases/CASE-002-Dynamic-Equivalence-and-Relay-Substitution.md) with history shifts and delayed feedback; record when initially valid substitution becomes invalid.

**VP-03 — PDT/PASQ Differential Benchmark:** generate synthetic ground-truth differential events; compare full scans, conventional SQL, and PDT/PASQ.

**VP-04 — RSI Candidate Governance:** compare a shared candidate generator under ordinary evaluator loops versus explicit UIERU-like contracts, independent tests, and rollback gates.

**VP-05 — RRP Reproduction Challenge:** give two independent teams the same research problem in narrative and structured-RRP form; assess reproducibility and counterexample discovery.

These packages are chosen for tractability. Biological validation is essential to the longer program but requires discipline-specific data, expertise, and approvals.

---

## 19. Research collaboration and ownership

Each validation package should identify a question owner, implementation owner, independent evaluator, and reviewer. These roles may be held by different people or institutions; role separation is especially important for RSI experiments and claims of safety or improvement.

External contributions are welcomed as proofs, counterexamples, datasets, benchmarks, competing models, negative results, schema revisions, or independent replication. Attribution should follow actual contribution and applicable publication norms. Refer to [RESEARCH-COLLABORATION.md](research-relay/RESEARCH-COLLABORATION.md) for handoff conventions.

---

## 20. Dependencies on the BUI-DSI corpus

**Core papers:**

- [BUI-001 — From Static SI to Dynamic Intelligence Units](docs/BUI-001-From-Static-Structural-Intelligence-to-Dynamic-Intelligence-Units.md)
- [BUI-002 — Perspective Masking](docs/BUI-002-Perspective-Masking-and-Dynamic-Structural-Observation.md)
- [BUI-003 — Perspective Differential Trees](docs/BUI-003-Perspective-Differential-Trees-and-Dynamic-Localization.md)
- [BUI-004 — PASQ](docs/BUI-004-Perspective-Aware-Structural-Query-and-SQL.md)
- [BUI-005 — Dynamic Equivalence and Relay](docs/BUI-005-Dynamic-Equivalence-Relay-Composition-and-Emergent-Relations.md)
- [BUI-006 — Mathematical Foundations](docs/BUI-006-Mathematical-Foundations-and-Open-Formal-Problems.md)
- [BUI-007 — Biological Intelligence](docs/BUI-007-Biological-Intelligence-and-Dynamic-Organizational-Biomimicry.md)
- [BUI-008 — Open Research Relay](docs/BUI-008-Open-Research-Relay-and-the-Next-Horizon-of-Structural-Intelligence.md)

**Specifications:** [SPEC-001](specs/SPEC-001-Dynamic-UIERU-Observation-Model.md) · [SPEC-002](specs/SPEC-002-Perspective-Masking-Contract.md) · [SPEC-003](specs/SPEC-003-Dynamic-Differential-and-Query-Schema.md) · [SPEC-004](specs/SPEC-004-Research-Relay-Piece-Contract.md)

**Research relays:** [RELAY-001](research-relay/RELAY-001-Perspective-Masking-Algebra.md) · [RELAY-002](research-relay/RELAY-002-Dynamic-Behavioral-Equivalence.md) · [RELAY-003](research-relay/RELAY-003-Relay-Composition-and-Contracts.md) · [RELAY-004](research-relay/RELAY-004-Biological-Dynamic-Intelligence.md) · [RELAY-005](research-relay/RELAY-005-Open-Structural-Evolution.md)

**Proposed extension:** `RELAY-006-RSI-UIERU-Convergence-and-Structural-Governance.md` is a planned research piece, not a prerequisite for this roadmap.

---

## 21. Success, failure, and the next research horizon

The program succeeds only to the extent that its claims become clearer, more testable, more reproducible, and more useful under independently scrutinized conditions. Some proposals may fail; a rigorous failure that identifies an invalid assumption is still a productive Research Relay outcome.

The intended trajectory is:

> **Explicit observation → disciplined perspective comparison → scoped equivalence → governed composition → evidence-based evolution → independently reusable research.**

This roadmap is itself a versioned research artifact. New counterexamples, formal results, neuroscience evidence, or RSI findings should revise its gates and priorities through documented changes, not be retrofitted into claims of prior validation.

---

**Citation and contribution:** Sizhe Tan & GPT-Obot, *Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay — Validation Roadmap*, v1.0.0 (2026). This is a proposed research program, not a peer-reviewed experimental report.

# CASE-001 — Perspective-Masked Model Selection

**Project:** Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay (BUI-DSI)  
**Version:** 1.0.0 (research proposal)  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Illustrative case; hypotheses and synthetic data, not empirical findings  
**Companion papers:** BUI-002, BUI-003, BUI-004, BUI-005, BUI-006

## Abstract

This case develops a reproducible conceptual experiment for comparing decisions made by a dynamic intelligence unit under cost, quality, and latency perspectives. It separates observational perspective masking from interventions that change decision policy, introduces a comparison contract, and traces scoring, decision, trajectory, and learning differentials. A small synthetic example demonstrates how Perspective Differential Trees (PDT) and Perspective-Aware Structural Query (PASQ) can expose both shared structure and consequential behavioral variation. The case is designed as an open Research Relay Piece: its assumptions, data, counterexamples, and validation criteria can be replaced independently by later investigators.

## 1. Research question

Given one UIERU-like model-selection unit and a fixed task, what changes when the active evaluation perspective changes? Which changes can be observed without modifying the unit, and which require a controlled intervention or replay? Can these changes be indexed and queried without confusing correlation with causation?

The central distinction is between **a masked view of a recorded decision** and **a decision recomputed under a different policy**. Only the latter can establish what a specified policy would select, and even that requires a validated replay model.

## 2. Case boundary and terminology

The example unit, `U-select`, chooses among three candidate language models for a coding task. The models are anonymized as A, B, and C. Its structural core includes a task interface, candidate registry, evaluation contract, scoring adapters, a decision rule, an execution adapter, and an evidence log.

A *perspective* specifies an explicit weighting of cost, quality, and latency objectives. A *mask* is a declared operation over observations or permitted evaluation variables. A *trajectory* includes selection, execution, measured outcome, and any subsequent update. A *relay* transmits the selected task and contract to the execution component.

No claim is made that a particular LLM internally uses an explicit scoring forest. The forest in this case is an engineering abstraction implemented outside candidate models.

## 3. Minimal dynamic model

Let a unit state at step `t` be

$$
X_t=(G_t, H_t, K_t, E_t),
$$

where `G` is its structural configuration, `H` its evidence history, `K` its policy and scoring configuration, and `E` its environment description. Given task `q`, perspective `p`, and candidate set `C`, the unit computes

$$
s_p(c\mid q,X_t)=\sum_{j\in\{cost,quality,latency\}}w_{p,j}r_j(c\mid q,X_t),
$$

and selects

$$
a_t=\arg\max_{c\in C}s_p(c\mid q,X_t).
$$

The observed transition is

$$
(X_{t+1},o_t)=T(X_t,q,p,a_t,\xi_t),
$$

with `o` denoting measured outcomes and `ξ` uncontrolled environmental factors. A score is a decision input, not a verified measure of real-world success.

## 4. Comparison contract

A comparison is valid only if the following are recorded or controlled:

| Field | Requirement |
|---|---|
| Task | Same coding task, input, acceptance criteria, and difficulty |
| Candidates | Identical available models and model versions |
| Measurement | Common definitions and normalization for cost, quality, latency |
| State | Same frozen unit snapshot or explicitly paired snapshots |
| Environment | Same tool permissions, hardware class, load assumptions, and time window |
| Perspective | Explicit weights, constraints, and tie-breaking rule |
| Mask | Observation-only, intervention, or counterfactual replay explicitly labeled |
| Evidence | Raw measurements, provenance, missingness, and uncertainty |
| Execution | Repetitions, random seeds where controllable, and failure records |

A masked observation must never be presented as evidence that a different perspective *caused* a different action unless the action was actually recomputed or executed under that perspective.

## 5. Synthetic candidate evidence

The following values are deliberately invented to illustrate the method; all normalized scores are higher-is-better, on a 0–100 scale.

| Candidate | Cost efficiency | Quality | Latency efficiency |
|---|---:|---:|---:|
| A | 95 | 70 | 75 |
| B | 45 | 98 | 50 |
| C | 70 | 83 | 96 |

Three candidate perspectives use normalized weights:

| Perspective | Cost | Quality | Latency |
|---|---:|---:|---:|
| `P-cost` | 0.70 | 0.20 | 0.10 |
| `P-quality` | 0.10 | 0.80 | 0.10 |
| `P-latency` | 0.10 | 0.20 | 0.70 |

Weighted scores follow directly from the table:

| Perspective | A | B | C | Selected |
|---|---:|---:|---:|---|
| `P-cost` | 88.0 | 56.1 | 75.2 | A |
| `P-quality` | 73.0 | 87.9 | 83.0 | B |
| `P-latency` | 76.0 | 59.1 | 90.8 | C |

The different selections demonstrate a property of this synthetic policy, not a universal feature of UIERU or any real model. In particular, normalized criteria can hide measurement uncertainty or incomparable quality dimensions.

## 6. Perspective masking protocol

**Mode O — observational masking.** Keep the recorded state and action unchanged. Display only a selected subset of scores, attributes, or traces. This supports inspection but cannot answer what would have happened under another policy.

**Mode R — deterministic replay.** Freeze `X_t`, task, candidate measurements, and tie-breaking rule; change only perspective weights and recompute the score and selected candidate. This isolates the policy effect *within the stated scoring model*.

**Mode I — live intervention.** Execute the selected candidate under each perspective in matched or randomized trials. Collect actual outcomes and state transitions. This can test downstream effects, but is sensitive to stochasticity and environmental drift.

Each record should carry `mask_mode`, `state_snapshot_id`, `policy_version`, `evidence_version`, `replay_or_trial_id`, and `provenance_uri`.

## 7. Four levels of differential

### 7.1 Scoring differential

For two perspectives `p` and `p'`:

$$
\Delta S_{p,p'}(c)=s_p(c)-s_{p'}(c).
$$

For candidate A, `P-cost` minus `P-quality` is `88.0 - 73.0 = 15.0`. Such differences are meaningful only because the same normalized scoring dimensions and candidate evidence are used.

### 7.2 Decision differential

Define

$$
\Delta D_{p,p'}=\mathbf{1}[a_p\ne a_{p'}].
$$

Here every pair among the three perspectives has a different selected candidate. Score changes need not always produce decision changes; this is a counterexample to equating scoring differential with decision differential.

### 7.3 Trajectory differential

Compare sequences such as `score → select → relay → execute → validate → update`. A selection change may alter tool use, latency, cost, correctness, and later learning. A trajectory comparison needs actual execution traces, not only the synthetic score table.

### 7.4 Learning differential

After repeated executions, a unit may update calibration, candidate metadata, or routing policy. Compare versions `X_t` and `X_{t+k}` under matched evaluation conditions. Distinguish evidence accumulation from policy updates and structural changes; repeated execution alone does not establish learning.

## 8. Perspective Differential Tree (PDT)

An illustrative PDT is:

```text
U-select / task=coding / snapshot=S0
└── Shared comparison contract
    ├── Scoring differential
    │   ├── P-cost → A (88.0)
    │   ├── P-quality → B (87.9)
    │   └── P-latency → C (90.8)
    ├── Decision differential
    │   └── Three distinct selected candidates
    ├── Trajectory differential
    │   └── Pending live execution evidence
    └── Learning differential
        └── Pending longitudinal evidence
```

The tree indexes *evidence-qualified differences*. It must not imply that missing trajectory evidence is evidence of no difference. Every node should link to the comparison contract, source measurements, masking mode, and relevant counterevidence.

## 9. Perspective-Aware Structural Query (PASQ)

A minimal relational design includes:

```sql
CREATE TABLE perspective_scores (
    trial_id TEXT NOT NULL,
    state_snapshot_id TEXT NOT NULL,
    task_id TEXT NOT NULL,
    perspective_id TEXT NOT NULL,
    candidate_id TEXT NOT NULL,
    score DOUBLE PRECISION NOT NULL,
    mask_mode TEXT NOT NULL,
    evidence_version TEXT NOT NULL,
    PRIMARY KEY (trial_id, perspective_id, candidate_id)
);

CREATE TABLE perspective_decisions (
    trial_id TEXT NOT NULL,
    state_snapshot_id TEXT NOT NULL,
    task_id TEXT NOT NULL,
    perspective_id TEXT NOT NULL,
    selected_candidate_id TEXT NOT NULL,
    mask_mode TEXT NOT NULL,
    PRIMARY KEY (trial_id, perspective_id)
);
```

For a paired deterministic replay stored under one `trial_id`, identify trials with perspective-dependent choices:

```sql
SELECT trial_id, state_snapshot_id, task_id,
       COUNT(DISTINCT selected_candidate_id) AS distinct_choices
FROM perspective_decisions
WHERE mask_mode = 'deterministic_replay'
GROUP BY trial_id, state_snapshot_id, task_id
HAVING COUNT(DISTINCT selected_candidate_id) > 1;
```

This query reports variation, not causal identification or substitutability. Production schemas should additionally include versioned measurement definitions, provenance, timestamps, missingness indicators, and contract IDs.

## 10. MET architecture and execution plan

1. **Structural descriptor:** Register task contract, model versions, scoring dimensions, and relay interface.
2. **Evidence plane:** Measure candidate outcomes with uncertainty and retain raw records.
3. **Perspective plane:** Define weights, hard constraints, and decision tie-breaking.
4. **Masking service:** Expose observational views separately from replay and intervention.
5. **Differential engine:** Compute score and decision differences; align observed trajectories.
6. **PDT index:** Materialize evidence-qualified differential branches.
7. **PASQ interface:** Query by task, perspective, version, mask mode, and confidence.
8. **Governance:** Audit comparisons, surface counterexamples, and prevent unsupported generalization.

A first prototype can use SQL and a simple deterministic scorer; a new database engine or bespoke query language is not a prerequisite.

## 11. Counterexamples and failure modes

- **Different measurement scales:** A score difference is invalid if candidate quality is normalized differently between perspectives.
- **Hidden hard constraints:** A cheap model might violate minimum accuracy, changing the feasible candidate set.
- **Policy-induced observation bias:** Only selected candidates receive execution feedback, leaving unselected candidates undermeasured.
- **Stochastic execution:** The same selected model may produce different outcomes across trials.
- **State drift:** A learning update between perspectives invalidates a supposedly matched comparison.
- **Masking as intervention:** Suppressing a scoring component can change behavior; it is not merely hiding a field.
- **Equivalent decision, different trajectory:** Two perspectives may select the same model yet use different budgets or validation paths.
- **Goodhart effects:** Optimizing a proxy quality score may reduce real task success.

Each counterexample should be retained in the research record even when it weakens the proposed method.

## 12. Testable hypotheses

**H1 — Observability.** Under a fixed comparison contract, PDT exposes perspective-dependent decisions more reliably than unstructured logs. Measure retrieval precision and analyst agreement.

**H2 — Queryability.** PASQ reduces time to locate matched cross-perspective cases relative to ad hoc log inspection. Measure latency and correctness.

**H3 — Provenance.** Explicit mask-mode and evidence-version fields reduce misinterpretation of replay results as live causal evidence. Test with blinded reviewers.

**H4 — Dynamic localization.** Adding behavior-qualified descriptors improves retrieval of units suitable for a target perspective relative to static descriptors alone. Measure held-out task performance.

**H5 — Robustness.** Small changes in weights do not always preserve selection; measure decision-boundary sensitivity and instability rates.

These are proposals, not established results.

## 13. Validation roadmap

**Phase 1:** Reproduce the synthetic score table and verify arithmetic, tie-breaking, and schema integrity.

**Phase 2:** Add measurement uncertainty and hard feasibility constraints; characterize sensitivity of selections.

**Phase 3:** Execute randomized or paired coding tasks across model candidates, preserving costs, latency, correctness, and failures.

**Phase 4:** Run longitudinal experiments with and without evidence-driven updates; separate learning effects from environmental drift.

**Phase 5:** Compare static localization against PDT/PASQ-assisted dynamic localization on held-out tasks, including negative results.

Report sample sizes, statistical uncertainty, costs, and limitations before claiming engineering benefit.

## 14. RSI–UIERU research bridge

An LLM-based recursive self-improvement agent may generate candidates, run evaluators, update workflows, and retain execution history. These features make it a useful adjacent system for this case. A proposed experiment would wrap such an agent with explicit UIERU-like contracts and perspective logging, then compare interpretability, auditability, decision quality, and adaptation against the unwrapped baseline.

This is a potential **two-way relay**: RSI may improve candidate generation and search, while UIERU-like interfaces may improve structural observation and evaluator governance. Structural traceability does not imply interpretability of the internal neural model. No superiority claim is made without comparative evidence.

## 15. Research Relay Piece contract

```yaml
relay_piece_id: BUI-DSI-CASE-001
version: 1.0.0
problem: Perspective-dependent selection by a dynamic intelligence unit
model: Weighted multi-objective model selection with explicit state snapshot
status: illustrative_hypothesis
inputs:
  - task_and_candidate_contract
  - versioned_candidate_evidence
  - perspective_weights
  - masking_mode
outputs:
  - perspective_scores
  - perspective_decisions
  - evidence_qualified_differentials
  - provenance_links
validation:
  - arithmetic_reproduction
  - controlled_replay
  - matched_live_trials
counterevidence:
  - scale_mismatch
  - state_drift
  - hidden_constraints
  - stochastic_execution
interfaces:
  - BUI-002
  - BUI-003
  - BUI-004
  - BUI-005
  - BUI-006
```

External researchers may substitute another decision rule, introduce Pareto selection, test nonlinear scoring, use real benchmark evidence, or refute the usefulness of the PDT index. Each extension should retain a precise comparison contract and provenance.

## 16. Open questions

1. Which perspective families admit reusable differential summaries without hiding decision-relevant details?
2. Can decision-boundary geometry support more efficient dynamic localization?
3. Under what conditions do observational masks commute with query operations?
4. What evidence is required to distinguish selection changes from downstream trajectory changes?
5. Can policy-sensitive equivalence classes improve safe model substitution?
6. How should learning-induced structural changes alter the identity and versioning of a unit?
7. Which claims about an RSI agent remain auditable when the agent's evaluator is itself modified?

## 17. Conclusion

Perspective-masked model selection is a compact entry point into dynamic structural intelligence. The synthetic example shows that a fixed structural unit can select different capabilities under different declared perspectives. More importantly, it establishes a disciplined boundary between observed evidence, deterministic policy replay, live interventions, and claims about learning. PDT and PASQ are proposed as reusable MET mechanisms for indexing and querying these differences. Their actual value must be established by controlled studies, counterexamples, and independent research relay.

## References and companion work

- BUI-001 — *From Static Structural Intelligence to Dynamic Intelligence Units*.
- BUI-002 — *Perspective Masking and Dynamic Structural Observation*.
- BUI-003 — *Perspective Differential Trees and Dynamic Localization*.
- BUI-004 — *Perspective-Aware Structural Query and SQL*.
- BUI-005 — *Dynamic Equivalence, Relay Composition, and Emergent Relations*.
- BUI-006 — *Mathematical Foundations and Open Formal Problems*.
- BUI-008 — *Open Research Relay and the Next Horizon of Structural Intelligence*.

**Citation note:** This case is a proposed framework and synthetic illustration. It should not be cited as an empirical benchmark or as proof of a general property of biological or artificial intelligence.

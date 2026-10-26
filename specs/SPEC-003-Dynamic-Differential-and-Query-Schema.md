# SPEC-003 — Dynamic Differential and Query Schema

**Project:** Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay (BUI-DSI)  
**Version:** 1.0.0 — Research Specification / Proposed Interface  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Draft research contract; not an implemented standard  
**Related:** SPEC-001, SPEC-002, BUI-003, BUI-004, BUI-005, RELAY-001, RELAY-002, CASE-001, CASE-002

## Abstract

This specification defines a proposed, implementation-neutral representation for **dynamic differentials** and **perspective-aware structural queries** over evolving intelligence units. It links observations (SPEC-001), perspective masking contracts (SPEC-002), four differential families, provenance-aware comparison, a Perspective Differential Tree (PDT) index, and Perspective-Aware Structural Query (PASQ) semantics. The objective is to make dynamic claims inspectable and falsifiable, not to assert that a universal query language or mathematical algebra has already been established. Examples are synthetic and do not demonstrate empirical system performance.

## 1. Scope and Normative Language

The keywords **MUST**, **MUST NOT**, **SHOULD**, **SHOULD NOT**, and **MAY** express proposed conformance requirements within this draft. They do not imply endorsement by a standards organization.

This document specifies:

- A comparison context and its admissibility checks.
- Typed differential records for scoring, decision, trajectory, and learning.
- A minimal PDT node/edge representation and index validity rules.
- A PASQ query envelope, relational projection, and example SQL.
- Evidence, uncertainty, counter-evidence, and invalidation handling.
- Conformance tests and open research questions.

Out of scope: a universal ontology of intelligence, direct inference of neural mechanisms, proof of causal effects from passive traces, and a complete production SQL engine.

## 2. Design Principles

1. **Compare under a declared contract.** Differences have meaning only relative to compatible tasks, perspectives, contexts, histories, and observation windows.
2. **Preserve epistemic type.** Observed, replayed, simulated, intervened, and counterfactually estimated records MUST remain distinguishable.
3. **Separate differential levels.** Score, decision, trajectory, and learning differences MUST NOT be silently collapsed.
4. **Record missingness.** Missing fields, censored observations, and unsupported claims are not zeros.
5. **Keep claims revocable.** New counter-evidence MAY invalidate a comparison or an index branch without deleting its historical record.
6. **Make query provenance first-class.** A result SHOULD link to its input observations, transformations, contracts, and validation state.
7. **Allow heterogeneous internals.** UIERUs MAY encapsulate LLMs, rules, neural models, workflows, or hybrid systems.

## 3. Core Entities and Identifiers

| Entity | Identifier | Purpose |
|---|---|---|
| Intelligence unit | `unit_id` | Stable identity for a bounded UIERU-like system |
| Unit version | `unit_version` | Snapshot of interfaces, policy, and structural configuration |
| Observation | `observation_id` | Event or bounded trace conforming to SPEC-001 |
| Perspective | `perspective_id` | Named valuation/selection viewpoint and its version |
| Mask contract | `mask_contract_id` | Explicit operator and semantics from SPEC-002 |
| Comparison | `comparison_id` | One admissibility-scoped pair or group comparison |
| Differential | `differential_id` | Typed finding derived from a comparison |
| PDT node | `pdt_node_id` | Index node for a conditioned differential |
| Query | `query_id` | Reproducible PASQ request |
| Evidence | `evidence_id` | Input, measurement, test, or counter-evidence record |
| Contract | `contract_id` | Assumptions, guarantees, and validity boundaries |

Identifiers MUST be unique within a declared namespace. Versioned objects MUST NOT be silently overwritten. Content hashes MAY supplement identifiers but are not substitutes for provenance metadata.

## 4. Dynamic Observation Basis

A dynamic observation is modeled as

$$
 o=(u,v,t,c,p,h,a,y,f,e,g,m),
$$

where \(u\) is unit identity, \(v\) version, \(t\) time/window, \(c\) context, \(p\) perspective, \(h\) bounded history reference, \(a\) action or decision, \(y\) outcome, \(f\) feedback, \(e\) evidence, \(g\) governance state, and \(m\) observation mode.

This tuple is an analytical shorthand; it does not imply that every field is observable or that every system exposes internal state. Records SHOULD reference SPEC-001 observations rather than duplicate potentially inconsistent copies.

### 4.1 Observation modes

`observed`, `deterministic_replay`, `stochastic_replay`, `simulation`, `intervention`, and `counterfactual_estimate` are distinct modes. A query MUST NOT aggregate these into a single empirical sample without an explicit, disclosed aggregation policy.

### 4.2 Time semantics

All timestamps MUST declare time zone or UTC offset; intervals SHOULD be half-open `[start, end)`. Event time and ingestion time MUST be separately representable. Ordering assumptions MUST be recorded where distributed events lack a total order.

## 5. Comparison Contract

A comparison is represented by

$$
 C=(U_A,U_B,P,K,H,W,O,M,A,\epsilon,E,V),
$$

with units/versions \(U_A,U_B\), perspective \(P\), context constraints \(K\), history constraints \(H\), window \(W\), observables \(O\), observation modes \(M\), alignment rule \(A\), tolerance policy \(\epsilon\), evidence requirements \(E\), and validation policy \(V\).

**Admissibility** is a separate result, not a property assumed by creating a comparison.

Possible states:

- `admissible`: declared preconditions checked and met.
- `admissible_with_limitations`: permitted with explicit caveats.
- `inadmissible`: a required precondition failed.
- `indeterminate`: evidence is insufficient to decide.

A comparison MUST record the specific failed or uncertain preconditions. A result in an inadmissible or indeterminate state MUST NOT be presented as a validated equivalence finding.

## 6. Differential Families

A differential is a typed claim about two aligned observations, traces, or bounded unit histories.

### 6.1 Scoring differential

$$
 \Delta_S= S_{P}(U_B\mid K,H)-S_{P}(U_A\mid K,H).
$$

The score scale, direction, calibration, and normalization MUST be recorded. Scores on incomparable scales MUST NOT be subtracted without an explicit conversion with evidence.

### 6.2 Decision differential

$$
 \Delta_D = d\bigl(\pi_B(K,H,P),\pi_A(K,H,P)\bigr),
$$

where \(d\) is a declared decision-distance function. A categorical mismatch, probability divergence, and ranked-choice displacement are different measures and MUST be labeled accordingly. A score change need not imply a decision change.

### 6.3 Trajectory differential

$$
 \Delta_T = D_T\bigl(\tau_B[W],\tau_A[W]\bigr),
$$

where \(\tau\) is an observable execution trace and \(D_T\) is a declared alignment and distance measure. The metric MAY include output quality, latency, resource usage, safety events, and contract violations, but its dimensions and weights MUST be explicit.

### 6.4 Learning differential

$$
 \Delta_L = D_L\bigl(\mathcal{B}_{B,t_1:t_2},\mathcal{B}_{A,t_1:t_2}\bigr),
$$

where \(\mathcal{B}\) denotes a specified behavior or structural property over an evaluation sequence. A learning claim MUST include a before/after protocol, evidence of a persistent update or change, and controls against context leakage and measurement drift. Repeated execution or growing logs alone MUST NOT be labeled learning.

### 6.5 Cross-family relationships

The schema does not assume implications such as \(\Delta_S\neq 0\Rightarrow\Delta_D\neq 0\), \(\Delta_D\neq0\Rightarrow\Delta_T\neq0\), or \(\Delta_T\neq0\Rightarrow\Delta_L\neq0\). These implications require additional assumptions and may be false.

## 7. Canonical Differential Record

```yaml
schema: bui.differential.v1
id: diff-001
comparison_id: cmp-001
family: decision
claim_status: candidate
left:
  unit_id: uieru-A
  unit_version: v1
  observation_id: obs-A-101
right:
  unit_id: uieru-B
  unit_version: v2
  observation_id: obs-B-101
perspective:
  id: latency-sensitive
  version: p1
context_ref: ctx-17
history_policy: matched-prefix
window:
  start: '2026-10-20T12:00:00Z'
  end: '2026-10-20T12:10:00Z'
comparison:
  admissibility: admissible_with_limitations
  limitations: [small_sample, nonrandom_assignment]
  alignment_method: matched-task-id
  observation_modes: [observed]
measure:
  metric: categorical_mismatch
  value: 1
  unit: boolean
  tolerance: 0
uncertainty:
  type: not_estimated
  reason: illustrative_single_pair
provenance:
  source_observations: [obs-A-101, obs-B-101]
  mask_contract_id: mask-007
  evaluator_version: eval-3
  evidence_ids: [ev-101, ev-102]
validation:
  state: provisional
  checked_rules: [DIFF-01, DIFF-02, DIFF-04]
counter_evidence: []
```

This example is synthetic. It establishes neither a performance advantage nor causal attribution.

## 8. Difference, Equivalence, and Substitutability

A zero measured differential is not automatically equivalence. A small estimated distance may be compatible with a wide confidence interval, incomplete observability, or an inadmissible comparison.

A conditional equivalence claim MAY take the form

$$
 U_A \approx_{P,K,H,W,O,\epsilon,E} U_B.
$$

Such a claim MUST specify its comparison contract, empirical or formal evidence, uncertainty, and validity interval. Substitutability requires additional interface, safety, resource, governance, and composition constraints, as developed in RELAY-002 and RELAY-003.

## 9. Perspective Differential Tree (PDT)

A PDT is a **proposed index over conditioned differences**, not necessarily a mathematical tree over all perspectives. Its purpose is to locate and explain where comparisons diverge.

### 9.1 Minimal node schema

```yaml
schema: bui.pdt-node.v1
pdt_node_id: pdt-0007
parent_id: pdt-0002
comparison_id: cmp-001
partition:
  field: perspective_id
  predicate: 'latency-sensitive'
differential_refs: [diff-001, diff-002]
summary:
  decision_mismatch_count: 1
  trajectory_comparisons: 1
  learning_claims_validated: 0
coverage:
  compared_pairs: 1
  missing_pairs: 3
validation_state: provisional
lineage:
  created_from: [obs-A-101, obs-B-101]
  evaluator_version: eval-3
  mask_contract_id: mask-007
```

### 9.2 PDT edge semantics

Edges MUST declare their meaning, e.g. `partition_refinement`, `temporal_successor`, `causal_hypothesis`, or `relay_dependency`. A causal-hypothesis edge MUST NOT be treated as a proven causal relationship.

### 9.3 Index maintenance

PDT summaries MUST be invalidated or recomputed when any dependency changes: observation correction, perspective version, metric definition, alignment policy, evidence retraction, or evaluator revision. Incremental updates MAY be used if their consistency conditions are documented.

### 9.4 Forests and graphs

Multiple perspectives and overlapping context partitions can produce non-tree relations. Implementations MAY expose a PDT forest or DAG, but MUST disclose when shared nodes or multiple parent paths invalidate ordinary tree assumptions.

## 10. PASQ — Perspective-Aware Structural Query

PASQ is a conceptual query layer whose results retain comparison semantics and provenance. It MAY be implemented using SQL, graph queries, or a dedicated language.

A PASQ query envelope SHOULD declare:

```yaml
schema: bui.pasq.v1
query_id: pasq-001
source: dynamic_differentials
perspective: latency-sensitive
context_filter:
  task_family: summarization
observation_modes: [observed]
family_filter: [scoring, decision, trajectory]
validation_filter: [validated, provisional]
window:
  start: '2026-10-20T00:00:00Z'
  end: '2026-10-21T00:00:00Z'
result_policy:
  include_provenance: true
  include_uncertainty: true
  include_counter_evidence: true
  exclude_inadmissible: true
```

The response MUST disclose the filters and the effective comparison population. It SHOULD include counts for excluded and missing records.

## 11. Minimal Relational Schema (Illustrative SQL)

The following is PostgreSQL-oriented pseudocode, not a certified migration. Production implementations need access controls, indexes, normalization, and retention policies.

```sql
CREATE TABLE observation (
  observation_id TEXT PRIMARY KEY,
  unit_id TEXT NOT NULL,
  unit_version TEXT NOT NULL,
  perspective_id TEXT NOT NULL,
  perspective_version TEXT NOT NULL,
  event_time TIMESTAMPTZ NOT NULL,
  observation_mode TEXT NOT NULL,
  context_ref TEXT,
  history_ref TEXT,
  payload JSONB NOT NULL,
  evidence_refs JSONB NOT NULL DEFAULT '[]'::jsonb
);

CREATE TABLE comparison_contract (
  comparison_id TEXT PRIMARY KEY,
  left_observation_id TEXT NOT NULL REFERENCES observation(observation_id),
  right_observation_id TEXT NOT NULL REFERENCES observation(observation_id),
  perspective_id TEXT NOT NULL,
  context_policy JSONB NOT NULL,
  alignment_policy JSONB NOT NULL,
  admissibility TEXT NOT NULL,
  limitations JSONB NOT NULL DEFAULT '[]'::jsonb,
  mask_contract_id TEXT,
  validation_state TEXT NOT NULL
);

CREATE TABLE differential (
  differential_id TEXT PRIMARY KEY,
  comparison_id TEXT NOT NULL REFERENCES comparison_contract(comparison_id),
  family TEXT NOT NULL CHECK (family IN ('scoring','decision','trajectory','learning')),
  metric_id TEXT NOT NULL,
  metric_version TEXT NOT NULL,
  value_numeric DOUBLE PRECISION,
  value_structured JSONB,
  uncertainty JSONB NOT NULL,
  provenance JSONB NOT NULL,
  claim_status TEXT NOT NULL,
  validation_state TEXT NOT NULL,
  CHECK (value_numeric IS NOT NULL OR value_structured IS NOT NULL)
);

CREATE TABLE pdt_node (
  pdt_node_id TEXT PRIMARY KEY,
  parent_id TEXT REFERENCES pdt_node(pdt_node_id),
  comparison_id TEXT REFERENCES comparison_contract(comparison_id),
  partition_rule JSONB NOT NULL,
  summary JSONB NOT NULL,
  dependency_versions JSONB NOT NULL,
  validation_state TEXT NOT NULL
);

CREATE TABLE counter_evidence (
  counter_evidence_id TEXT PRIMARY KEY,
  differential_id TEXT NOT NULL REFERENCES differential(differential_id),
  evidence_ref TEXT NOT NULL,
  challenge_type TEXT NOT NULL,
  resolution_state TEXT NOT NULL,
  recorded_at TIMESTAMPTZ NOT NULL
);
```

### 11.1 Example: decision differences by perspective

```sql
SELECT c.perspective_id,
       COUNT(*) AS compared_pairs,
       SUM(CASE WHEN d.value_numeric > 0 THEN 1 ELSE 0 END) AS mismatches
FROM differential d
JOIN comparison_contract c USING (comparison_id)
WHERE d.family = 'decision'
  AND d.metric_id = 'categorical_mismatch'
  AND c.admissibility = 'admissible'
  AND d.validation_state = 'validated'
GROUP BY c.perspective_id;
```

This query is meaningful only if metric version, population, and sampling policy are compatible; implementations SHOULD additionally group or filter by those dimensions.

### 11.2 Example: evidence-challenged claims

```sql
SELECT d.differential_id, d.family, d.claim_status,
       ce.challenge_type, ce.resolution_state
FROM differential d
JOIN counter_evidence ce ON ce.differential_id = d.differential_id
WHERE ce.resolution_state IN ('open', 'confirmed')
ORDER BY d.differential_id;
```

### 11.3 Example: compare two perspective policies

```sql
SELECT c.perspective_id,
       d.family,
       d.metric_id,
       d.metric_version,
       AVG(d.value_numeric) AS mean_difference,
       COUNT(*) AS n
FROM differential d
JOIN comparison_contract c USING (comparison_id)
WHERE c.perspective_id IN ('cost-sensitive', 'quality-sensitive')
  AND c.admissibility = 'admissible'
  AND d.validation_state = 'validated'
  AND d.value_numeric IS NOT NULL
GROUP BY c.perspective_id, d.family, d.metric_id, d.metric_version;
```

These averages MUST NOT be interpreted as causal effects of perspective changes without a valid experimental or causal identification design.

## 12. Query Result Contract

Every PASQ response SHOULD include:

- `query_id`, execution time, schema and engine version.
- Effective filters, population size, excluded count, missing count.
- Data snapshot/version and relevant observation windows.
- Comparison admissibility and validation distribution.
- Metric definitions, uncertainty, and sampling limitations.
- Evidence references, counter-evidence, and transformation lineage.
- Permission/redaction metadata where relevant.

A query result MUST NOT silently upgrade `provisional` findings to `validated` or treat counterfactual estimates as observations.

## 13. Perspective Masking Integration

SPEC-002 defines masking operators; SPEC-003 consumes their outputs. Each differential MUST identify whether its inputs derive from:

1. Non-intervening projection or filtering.
2. Replay with stated reproducibility guarantees.
3. Simulation with an explicit model.
4. Intervention with an experimental assignment policy.
5. Counterfactual estimation with stated identification assumptions.

The mask contract MUST be versioned. If a mask changes the selection population, that change MUST be visible in comparison admissibility and query provenance.

## 14. Relay and Compositional Queries

For a Relay graph \(G=(V,E)\), local differential records MAY be associated with nodes and edges. A system-level claim requires an explicit aggregation rule:

$$
 \Delta_G = \mathcal{A}(\{\Delta_v\},\{\Delta_e\},K,P,W),
$$

where \(\mathcal{A}\) is a documented composition operator, not presumed additive. Local performance gains can be offset by coordination costs, latency tails, safety failures, or contract violations. A PASQ engine SHOULD support tracing a system-level finding back to constituent unit and Relay observations.

## 15. Evolution-Aware Queries

An evolving unit SHOULD carry version lineage, structural-change events, and evaluator versions. PASQ SHOULD support queries such as:

- Which perspective-specific decisions changed after a unit upgrade?
- Did a candidate replacement preserve the prior contract under the same evaluation protocol?
- Did observed performance improve while safety counter-evidence increased?
- Did an apparent learning gain persist on held-out tasks?
- Which PDT branches became stale after evaluator revision?

A before/after comparison without appropriate controls MUST be labeled observational and non-causal.

## 16. Synthetic Worked Example

Two UIERU-like selectors, A and B, choose between Model-X and Model-Y for matched synthetic tasks.

| Perspective | A decision | B decision | Decision differential | Observed latency delta | Learning claim |
|---|---|---|---|---|---|
| Cost-sensitive | Model-X | Model-X | Match | Not measured | None |
| Quality-sensitive | Model-Y | Model-Y | Match | Not measured | None |
| Latency-sensitive | Model-X | Model-Y | Mismatch | +12 ms (synthetic) | None |

A PDT can index the latency-sensitive branch while preserving matching branches. A PASQ query can locate the mismatch and retrieve its comparison contract. The table does **not** establish that B is better or worse: output quality, sample size, variance, and experimental design are unspecified. No learning is inferred.

## 17. Validation Rules

| Rule | Proposed requirement |
|---|---|
| DIFF-01 | Every differential references a comparison contract |
| DIFF-02 | Both compared observations exist and are versioned |
| DIFF-03 | Observation modes are declared and compatible with the claim |
| DIFF-04 | Perspective and metric versions are explicit |
| DIFF-05 | Context/history alignment is checked |
| DIFF-06 | Window semantics and timestamp offsets are valid |
| DIFF-07 | Missing values are not coerced to zero |
| DIFF-08 | Uncertainty or its absence is documented |
| DIFF-09 | Provenance references are resolvable |
| DIFF-10 | Counter-evidence links are retained |
| DIFF-11 | Learning claims include a longitudinal protocol |
| DIFF-12 | Equivalence claims disclose tolerances and coverage |
| DIFF-13 | PDT dependencies are versioned and invalidated when stale |
| DIFF-14 | PASQ returns effective filters and exclusion counts |
| DIFF-15 | Inadmissible comparisons cannot be labeled validated |
| DIFF-16 | Query access and redaction policies are enforced |
| DIFF-17 | Causal claims cite intervention or identification assumptions |
| DIFF-18 | Contract substitutions preserve required safety checks |

A conformance report MUST identify each rule as `pass`, `fail`, `not_applicable`, or `not_tested`; `not_tested` is not `pass`.

## 18. Suggested Conformance Levels

**D0 — Recordable:** observations and comparison contracts are schema-valid; DIFF-01 through DIFF-09 tested.

**D1 — Differential:** typed scoring/decision/trajectory/learning records with explicit limitations; DIFF-10 through DIFF-12 tested.

**D2 — Queryable:** PDT lineage and PASQ provenance/exclusions supported; DIFF-13 and DIFF-14 tested.

**D3 — Governed:** causal claims, access policies, substitution constraints, and counter-evidence lifecycle tested; DIFF-15 through DIFF-18 tested.

Levels are proposed capability profiles, not externally certified grades. Higher levels inherit lower-level requirements.

## 19. Counterexamples and Failure Modes

1. **Perspective aliasing:** two different policy versions share one name, producing misleading aggregation.
2. **Context mismatch:** a latency gain arises from easier tasks, not a better unit.
3. **Score-scale mismatch:** subtracting uncalibrated scores yields a meaningless differential.
4. **Replay leakage:** evaluation tasks influence a candidate during adaptation.
5. **Temporal misalignment:** asynchronous events are joined as if simultaneous.
6. **Selection bias:** a masking rule removes failed executions.
7. **Causal overreach:** observational differences are attributed to a perspective intervention.
8. **False learning:** repeated logs are counted as evidence of structural improvement.
9. **Index staleness:** PDT nodes retain results after evaluator revision.
10. **Composition failure:** locally acceptable replacements violate system latency or safety.
11. **Hidden missingness:** absent observations are interpreted as equivalence.
12. **Counter-evidence suppression:** adverse findings are dropped from summary queries.

Implementations SHOULD include regression tests for these failures.

## 20. Security, Privacy, and Governance

Observations may contain prompts, personal data, proprietary model outputs, or sensitive execution traces. Implementations MUST apply least-privilege access, retention rules, redaction, and audit logging appropriate to their deployment. A provenance pointer MUST NOT be treated as authorization to reveal its underlying artifact. Query permissions SHOULD be enforced before aggregation to prevent cross-tenant or cross-subject inference. Research collaboration SHOULD permit publication of schema-level examples without exposing protected data.

## 21. Open Mathematical and Systems Problems

**Q1 — Admissibility algebra.** Under which alignment and context constraints is comparison admissibility compositional?

**Q2 — Metric invariance.** Which differential properties survive monotone transformations or score recalibration?

**Q3 — Perspective refinement.** When does a refined perspective preserve an earlier comparison order?

**Q4 — Query preservation.** Which PASQ queries commute with non-intervening perspective projections?

**Q5 — PDT soundness.** Under what assumptions does an indexed branch faithfully summarize all underlying differentials?

**Q6 — Approximate equivalence.** How should finite-sample uncertainty interact with tolerance-bounded behavioral equivalence?

**Q7 — Relay composition.** When do local differential bounds imply meaningful system-level bounds?

**Q8 — Evolution invalidation.** Can dependency-aware incremental maintenance remain correct under structural self-modification?

**Q9 — Counter-evidence updates.** What is the minimal revision calculus for retracting unsupported claims without losing history?

**Q10 — Query cost.** How can provenance-complete dynamic queries scale without sacrificing auditability?

These are open questions, not established theorems.

## 22. Testable Hypotheses

- **H1:** Explicit comparison contracts reduce invalid cross-context comparisons relative to untyped trace comparison.
- **H2:** A PDT index reduces time-to-localize perspective-specific mismatches against a specified scan baseline.
- **H3:** PASQ provenance requirements increase the rate at which independent reviewers can reproduce differential claims.
- **H4:** Counter-evidence-aware queries detect more false equivalence assertions than queries omitting adverse evidence.
- **H5:** Evolution-aware invalidation reduces stale comparison findings after evaluator or unit upgrades.
- **H6:** Separating differential families reduces erroneous inferences of learning from decision or trajectory changes.

Each hypothesis requires pre-registered datasets or task generators, operational metrics, baselines, and failure thresholds. None is asserted as experimentally confirmed here.

## 23. Validation Roadmap

**Phase A — Schema fixtures:** construct valid, invalid, missing, and contradictory observation/comparison records.

**Phase B — Metric fixtures:** verify typed differences, alignment, and uncertainty behavior on synthetic controlled traces.

**Phase C — PDT indexing:** test lineage, partition coverage, invalidation, and reproducibility.

**Phase D — PASQ execution:** compare relational/graph implementations for semantic agreement and provenance completeness.

**Phase E — Adversarial sandbox:** inject selection bias, drift, masking errors, hidden counter-evidence, and contract violations.

**Phase F — Dynamic deployment:** evaluate evolving UIERU-like and LLM-Agent/RSI systems under governance controls.

Report negative findings and resource overhead alongside successes.

## 24. Research Relay Piece Interface

```yaml
research_relay_piece:
  id: BUI-SPEC-003
  version: 1.0.0
  title: Dynamic Differential and Query Schema
  problem: >
    How can perspective-conditioned dynamic differences be represented,
    queried, validated, and revised across evolving intelligence units?
  models:
    - comparison_contract
    - typed_differential
    - perspective_differential_tree
    - perspective_aware_structural_query
  hypotheses: [H1, H2, H3, H4, H5, H6]
  evidence_status: proposed_not_empirically_validated
  validation:
    - schema_conformance
    - synthetic_differential_tests
    - provenance_reproduction
    - adversarial_counterexamples
  interfaces:
    upstream: [SPEC-001, SPEC-002]
    downstream: [SPEC-004, RELAY-002, RELAY-003, RELAY-005]
  contribution_types:
    - formal_proof
    - counterexample
    - reference_implementation
    - benchmark
    - empirical_replication
  authors: [Sizhe Tan, GPT-Obot]
```

## 25. Interoperability and RSI–UIERU Convergence

An LLM-Agent or RSI system can be observed as a bounded unit without claiming access to hidden weights or reasoning. Its external evaluator, candidate generation, tool invocation, feedback, and version transitions can be represented as observable events when available. This enables **structural interpretability at the system boundary**, not automatic interpretability of the internal model.

Potential two-way Relay:

- RSI generates candidate policy or workflow changes; PASQ measures their conditioned behavioral differences.
- UIERU contracts and PDT expose drift, substitution risk, and evidence gaps.
- Adverse evidence can trigger rollback or further evaluation rather than automatic acceptance.
- RSI research may suggest more efficient candidate-generation strategies for SI structural growth.

Any improvement in reliability, cost, or auditability must be empirically measured.

## 26. Relationship to the BUI-DSI Series

- **BUI-003:** Perspective Differential Trees and Dynamic Localization.
- **BUI-004:** Perspective-Aware Structural Query and SQL.
- **BUI-005:** Dynamic Equivalence, Relay Composition, and Emergent Relations.
- **CASE-001:** Perspective-Masked Model Selection.
- **CASE-002:** Dynamic Equivalence and Relay Substitution.
- **RELAY-001:** Perspective Masking Algebra.
- **RELAY-002:** Dynamic Behavioral Equivalence.
- **RELAY-003:** Relay Composition and Contracts.
- **SPEC-001:** Dynamic UIERU Observation Model.
- **SPEC-002:** Perspective Masking Contract.
- **SPEC-004:** Research Relay Piece Contract (planned companion).

## 27. Limitations and Research Status

This specification proposes a vocabulary, data model, and validation approach. It does not prove completeness of the differential families, optimality of PDT indexing, universal SQL portability, causal identifiability, or stability under unrestricted self-modification. All mathematical propositions are research candidates; all example measurements are synthetic. Implementations should publish deviations and limitations.

## 28. Conclusion

A dynamic structural intelligence system requires more than logs and scores. It needs explicit comparison conditions, typed differentials, traceable queries, and a disciplined mechanism for revising conclusions when evidence changes. SPEC-003 proposes such an interface: **observe under contract, compare by differential type, localize through PDT, query through PASQ, and preserve the evidence that makes each claim defensible or refutable**.

---

**Citation:** Sizhe Tan & GPT-Obot (2026). *SPEC-003 — Dynamic Differential and Query Schema*. Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay, v1.0.0. Research specification.

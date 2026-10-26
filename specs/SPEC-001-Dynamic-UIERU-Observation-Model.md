# SPEC-001 — Dynamic UIERU Observation Model

**Project:** Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay (BUI-DSI)  
**Version:** 1.0.0 (research draft)  
**Status:** Proposed specification; not an implemented or validated standard  
**Authors:** Sizhe Tan & GPT-Obot  
**Repository path:** `specs/SPEC-001-Dynamic-UIERU-Observation-Model.md`  
**Related:** BUI-001–008; CASE-001–003; RELAY-001–005; SPEC-002–004 (planned)

## 1. Purpose

This specification proposes a **portable, evidence-aware observation record** for a dynamic Universal Intelligence Evolution and Relay Unit (UIERU). Its purpose is to support reproducible comparison, perspective masking, differential analysis, query, relay substitution, and governed structural evolution **without presuming access to a unit's internal model weights or private reasoning**.

A UIERU observation is a *bounded assertion about a unit's state and behavior*, made by an identified observer under declared conditions. It is not a complete description of intelligence, a causal explanation by default, or proof of biological equivalence.

The specification separates:

1. **Unit identity and version** — which unit or composition was observed.
2. **Observation conditions** — context, perspective, task, history boundary, and observer.
3. **Behavioral event** — inputs, decisions, actions, outputs, and feedback, where observable.
4. **Evidence and uncertainty** — measurements, missingness, provenance, confidence and limitations.
5. **Governance** — consent, visibility, retention, and permitted uses.
6. **Evolution and relay linkage** — how observations relate to prior events and subsequent revisions.

A conforming record MAY omit inaccessible internal details but MUST make missingness explicit. This is a **research interchange contract**, not a mandate that every implementation expose private chain-of-thought or proprietary internals.

## 2. Normative Vocabulary and Conformance Levels

**MUST**, **MUST NOT**, **SHOULD**, **SHOULD NOT**, and **MAY** express requirements within this proposed specification.

| Level | Name | Minimum capabilities |
|---|---|---|
| O1 | Identifiable observation | Schema version, event ID, unit ID/version, timestamp, observer, observation mode, task/context references, evidence provenance |
| O2 | Behavioral trace | O1 plus input/output references, observed decision/action, result status, and temporal linkage |
| O3 | Perspective-aware trace | O2 plus perspective descriptor, scoring claims, mask reference, and explicit observability distinctions |
| O4 | Evolution-aware trace | O3 plus history snapshot, contract/version references, revision or learning links, and evaluation boundaries |

Levels are **capability profiles**, not intelligence rankings. A valid O1 observation need not expose a score or action. Every claimed level MUST satisfy all lower-level requirements, except where a field is explicitly inapplicable and marked accordingly.

## 3. Scope and Non-Goals

### In scope

- Single units and composed/relayed units.
- Online observations, deterministic replay records, simulations, and intervention records.
- Multi-perspective comparison, including cost, quality, latency, safety, and stakeholder-defined perspectives.
- Explicit references to artifacts, contracts, evaluation policies, and evidence.
- Traceable transitions from execution repetition to evidence accumulation and possible structural learning.

### Out of scope

- A universal ontology of intelligence or consciousness.
- An assertion that a neural network, animal brain, or RSI system literally implements a UIERU.
- Mandatory disclosure of model parameters, secrets, private data, or hidden reasoning.
- Proof that observed behavioral similarity implies causal or mechanistic equivalence.
- A complete distributed consensus, cryptographic signing, or security protocol.

## 4. Conceptual Model

Let a unit be represented abstractly as

$$
U_t = (I_t, B_t, C_t, P_t, F_t, H_t, G_t),
$$

where \(I\) is interface identity, \(B\) is the behavioral implementation or composition, \(C\) is the contract set, \(P\) is perspective/scoring configuration, \(F\) is feedback/evaluator configuration, \(H\) is history, and \(G\) is governance. These are **analytical categories**, not a claim that every implementation stores seven literal objects.

An observation is

$$
O_t = operatorname{Observe}(U_t, X_t, K_t, M_t, W_t; E_t),
$$

where \(X_t\) is a task/input, \(K_t\) a context, \(M_t\) a perspective or observation mask, \(W_t\) an observation window, and \(E_t\) the observation environment and instrumentation. The observed record is generally a **partial projection** of the underlying system.

An observation MAY refer to a counterfactual, but **a predicted counterfactual is not an observed outcome**. See §8.

## 5. Canonical Envelope

All records use UTF-8 JSON-compatible data. YAML MAY be used as a human-readable serialization if it preserves the same types and semantics. Unknown extension fields MUST be namespaced, for example `x_lab_a`.

| Field | Type | Required | Semantics |
|---|---|---|---|
| `spec_version` | string | MUST | `1.0.0` for this draft |
| `record_id` | string | MUST | Unique, immutable observation identifier within the issuer's namespace |
| `record_type` | enum | MUST | `observation`, `replay`, `intervention`, `simulation`, `counterfactual_estimate` |
| `observed_at` | RFC 3339 timestamp | MUST | Observation time; time zone explicit |
| `observer` | object | MUST | Observer/measurement agent identity and instrumentation version |
| `unit` | object | MUST | Stable unit ID, revision, composition reference if applicable |
| `task` | object | MUST | Task identifier and input reference or privacy-preserving digest |
| `context` | object | MUST | Declared context and scope; unknown variables acknowledged |
| `observation_window` | object | MUST | Start/end times or explicit point-event window |
| `perspective` | object/null | MUST | Perspective reference or explicit null with reason |
| `observability` | object | MUST | What was directly measured, inferred, hidden, or unavailable |
| `behavior` | object | MUST | Observed or estimated event details; missingness allowed |
| `evidence` | array | MUST | At least one provenance entry, including instrumentation evidence |
| `governance` | object | MUST | Visibility, use restrictions, retention class |
| `lineage` | object | MUST | Parent/previous record references, if any; empty arrays permitted |
| `extensions` | object | MAY | Namespaced research-specific fields |

The distinction between **required field presence** and **required underlying information** is deliberate. A required object can state `status: unavailable` with a reason, rather than inventing a value.

## 6. Identifier and Version Rules

- `record_id` MUST be unique within its issuer namespace and MUST NOT be reassigned to a modified record.
- `unit.id` identifies a logical unit; `unit.revision` identifies an immutable configuration or snapshot.
- `unit.composition_ref` SHOULD identify the relay graph or composition manifest when applicable.
- `contract_ref`, `perspective.ref`, `mask_ref`, `evaluator_ref`, and `history_ref` SHOULD resolve to versioned artifacts or content-addressed digests.
- An update to an existing observation MUST create a new `record_id` with a `supersedes` lineage edge; silent overwrite is nonconforming.
- Timestamp alone MUST NOT be treated as sufficient ordering evidence in distributed systems. Causal/event references SHOULD supplement clock time.

## 7. Observation Context and Perspective

`context` SHOULD include relevant environment version, locale or operating conditions, resource limits, actor/subject boundary, external dependencies, and known confounders. A declared context is **not** presumed complete.

`perspective` SHOULD specify:

```yaml
perspective:
  ref: "perspective:quality-first@2"
  owner: "stakeholder:research-team"
  objectives: ["answer_quality", "safety"]
  constraints: ["latency_p95_ms <= 3000"]
  scoring_policy_ref: "sha256:example-policy-digest"
  mask_ref: "mask:visible-quality-signals@1"
  status: "declared"
```

`perspective.owner` identifies whose evaluative interests are represented. A scoring policy MUST NOT silently substitute one stakeholder's objectives for another's. Conflicting perspectives SHOULD be preserved rather than collapsed into an unexplained scalar.

## 8. Observation Modes and Causal Semantics

| `record_type` | Meaning | Permitted claim |
|---|---|---|
| `observation` | Passive measurement of an executed event | Association/observed behavior |
| `replay` | Re-execution under a declared replay protocol | Reproducibility under replay conditions |
| `intervention` | Deliberate modification of an input, policy, or environment | Intervention effect, subject to design validity |
| `simulation` | Output of a simulated environment | Simulated outcome only |
| `counterfactual_estimate` | Model-based estimate of an unobserved alternative | Estimated, assumption-dependent outcome only |

An observation record MUST NOT label a passive difference as a causal effect. A replay MUST disclose whether the model, tools, random seeds, and external dependencies were fixed. A counterfactual MUST identify the estimating model, assumptions, and uncertainty. `record_type` MUST NOT be inferred merely from the presence of a `mask_ref`.

Perspective masking may change **visibility**, **evaluation**, or **execution**; these are distinct operations and MUST be labeled:

- `mask_semantics: observation_projection`
- `mask_semantics: scoring_filter`
- `mask_semantics: execution_intervention`

These values are not interchangeable. See SPEC-002 for the planned masking contract.

## 9. Behavioral Event Model

The `behavior` object represents observable events without assuming internal cognitive access:

```yaml
behavior:
  input_ref: "artifact:input-017"
  selected_action: "route_to_model_b"
  action_status: "executed"
  output_ref: "artifact:output-017"
  outcome_status: "completed"
  feedback_refs: ["evidence:feedback-017"]
  score_observations:
    - metric: "latency_ms"
      value: 920
      unit: "ms"
      source_ref: "evidence:latency-017"
      role: "measured"
    - metric: "quality_estimate"
      value: 0.82
      unit: "dimensionless"
      source_ref: "evidence:evaluator-017"
      role: "estimated"
  unobserved_fields: ["internal_reasoning", "model_weights"]
```

`selected_action` is an observed routing/action label, not a claim about why the unit selected it. `score_observations` MUST identify the scoring policy or instrument if their meaning depends on an evaluator. Scores with different metrics or evaluator versions MUST NOT be treated as directly comparable without an explicit normalization or mapping contract.

## 10. Evidence, Missingness, and Uncertainty

Each evidence entry SHOULD contain:

| Field | Meaning |
|---|---|
| `id` | Stable evidence identifier |
| `kind` | `log`, `measurement`, `human_rating`, `instrumentation`, `simulation_output`, `inference`, `external_reference` |
| `artifact_ref` | URI, repository path, or digest; may be access-controlled |
| `producer` | Responsible source or instrument |
| `collected_at` | Collection timestamp |
| `method_ref` | Measurement/evaluation protocol version |
| `integrity` | Digest/signature metadata if available |
| `access` | Public, restricted, or withheld |
| `limitations` | Biases, sampling limits, uncertainty, confounders |

Missing data MUST distinguish `not_applicable`, `not_observed`, `withheld`, `unavailable`, and `unknown`. Zero MUST NOT be used as a missing-value sentinel. Confidence SHOULD identify its meaning (for example calibrated probability, interval coverage, or subjective confidence); an unlabeled numeric confidence is insufficient for scientific comparison.

A claim's provenance MUST survive downstream Relay when the claim is reused. Counter-evidence SHOULD be linked with an explicit `challenges` relation, not deleted or silently averaged away.

## 11. History, Feedback, and Evolution Linkage

A dynamic observation MAY participate in an evolution chain:

$$
O_t \xrightarrow{\text{feedback}} E_t
\xrightarrow{\text{candidate revision}} U_{t+1}
\xrightarrow{\text{validation}} O_{t+1}.
$$

This is a **possible workflow**, not a guarantee that feedback produces learning. `lineage` SHOULD capture:

- `previous_record_ids` — temporally or causally prior observations.
- `parent_record_ids` — derived observations or aggregated evidence.
- `supersedes_record_ids` — corrected records.
- `revision_event_ref` — proposed or applied structural change.
- `history_snapshot_ref` — state boundary against which comparison is meaningful.
- `evaluation_run_ref` — independent validation result.

Repeated execution MAY accumulate evidence even when the unit does not learn. A claim of **structural evolution** MUST identify an actual structural revision and its validation status, not merely a growing execution count.

## 12. Contract and Governance Semantics

An observation SHOULD identify applicable `contract_ref` and `evaluator_ref`. Contract outcomes MUST distinguish `pass`, `fail`, `not_tested`, and `indeterminate`. A missing test MUST NOT be recorded as a pass.

`governance` MUST declare:

```yaml
governance:
  visibility: "restricted"
  permitted_uses: ["research_comparison", "contract_audit"]
  prohibited_uses: ["training_without_authorization"]
  retention_class: "project_policy_v1"
  consent_or_authority_ref: "policy:approved-study-04"
  redactions: ["personal_identifiers", "secrets"]
```

No field requires storing personal data or secrets. A digest is not necessarily anonymization; small or predictable inputs can be reidentified by guessing. Access control, data minimization, and applicable research ethics remain implementation responsibilities.

## 13. Canonical Illustrative Record

The following is a **synthetic example**, not evidence of actual LLM performance or biological behavior.

```yaml
spec_version: "1.0.0"
record_id: "urn:bui:lab-example:obs-00017"
record_type: "observation"
observed_at: "2026-10-21T12:00:00Z"
observer:
  id: "instrument:relay-logger"
  version: "0.2.0"
unit:
  id: "unit:model-router"
  revision: "r12"
  composition_ref: "relay-graph:example@3"
task:
  id: "task:answer-question"
  input_ref: "artifact:input-017"
context:
  environment_ref: "environment:testbed@2"
  resource_budget_ref: "budget:standard@1"
  known_confounders: ["nonstationary-provider-latency"]
observation_window:
  start: "2026-10-21T11:59:59Z"
  end: "2026-10-21T12:00:03Z"
perspective:
  ref: "perspective:quality-first@2"
  owner: "stakeholder:research-team"
  objectives: ["answer_quality", "safety"]
  mask_ref: "mask:quality-observation@1"
  mask_semantics: "observation_projection"
observability:
  directly_measured: ["selected_action", "latency_ms", "output_ref"]
  inferred: ["quality_estimate"]
  withheld: []
  unavailable: ["internal_reasoning", "model_weights"]
behavior:
  input_ref: "artifact:input-017"
  selected_action: "route_to_model_b"
  action_status: "executed"
  output_ref: "artifact:output-017"
  outcome_status: "completed"
  feedback_refs: ["evidence:evaluator-017"]
  score_observations:
    - metric: "latency_ms"
      value: 920
      unit: "ms"
      source_ref: "evidence:latency-017"
      role: "measured"
    - metric: "quality_estimate"
      value: 0.82
      unit: "dimensionless"
      source_ref: "evidence:evaluator-017"
      role: "estimated"
  unobserved_fields: ["internal_reasoning", "model_weights"]
evidence:
  - id: "evidence:latency-017"
    kind: "measurement"
    artifact_ref: "artifact:trace-017"
    producer: "instrument:relay-logger"
    collected_at: "2026-10-21T12:00:03Z"
    method_ref: "method:wall-clock-latency@1"
    access: "restricted"
    limitations: ["includes-network-variance"]
  - id: "evidence:evaluator-017"
    kind: "inference"
    artifact_ref: "artifact:rating-017"
    producer: "evaluator:quality-rubric@4"
    collected_at: "2026-10-21T12:00:03Z"
    method_ref: "method:quality-rubric@4"
    access: "restricted"
    limitations: ["not-human-validated"]
governance:
  visibility: "restricted"
  permitted_uses: ["research_comparison", "contract_audit"]
  prohibited_uses: ["training_without_authorization"]
  retention_class: "project_policy_v1"
  consent_or_authority_ref: "policy:approved-study-04"
  redactions: []
lineage:
  previous_record_ids: []
  parent_record_ids: []
  supersedes_record_ids: []
  history_snapshot_ref: "history:model-router@r12"
  revision_event_ref: null
  evaluation_run_ref: null
extensions: {}
```

The example deliberately includes an evaluator-derived estimate alongside a direct timing measurement. The two are **not** epistemically equivalent.

## 14. Validation Rules

A validator for this proposed specification SHOULD apply at least the following checks:

| Rule | Severity | Requirement |
|---|---|---|
| V-001 | Error | Required envelope fields are present with valid types |
| V-002 | Error | `record_type` is an allowed value |
| V-003 | Error | Timestamps are parseable RFC 3339 values and window end is not before start |
| V-004 | Error | Record ID and unit revision are nonempty |
| V-005 | Error | Every numeric score has metric, unit, source reference, and measured/estimated role |
| V-006 | Error | Evidence references used by scores resolve within the record or declared external registry |
| V-007 | Error | Missingness does not masquerade as zero or observed success |
| V-008 | Error | An `observation` record does not assert intervention causality as directly observed |
| V-009 | Warning | Context confounders are undeclared |
| V-010 | Warning | No immutable contract/evaluator/perspective references are supplied |
| V-011 | Error | Lineage graph contains a self-reference or a known cycle in `supersedes` edges |
| V-012 | Warning | Restricted evidence is referenced without a declared access policy |
| V-013 | Error | Claimed conformance level exceeds populated capabilities |
| V-014 | Warning | Distributed event ordering relies solely on wall-clock timestamps |

A validator checks **record consistency**, not truth of the recorded scientific claims. External replication and independent evidence remain necessary.

## 15. Query and Differential Interoperability

The observation model is intended to support Perspective Differential Trees (PDT) and Perspective-Aware Structural Query (PASQ), without imposing a specific database engine.

Candidate normalized relations:

```sql
CREATE TABLE observation (
  record_id TEXT PRIMARY KEY,
  spec_version TEXT NOT NULL,
  unit_id TEXT NOT NULL,
  unit_revision TEXT NOT NULL,
  record_type TEXT NOT NULL,
  observed_at TIMESTAMP NOT NULL,
  perspective_ref TEXT,
  context_ref TEXT,
  history_snapshot_ref TEXT
);

CREATE TABLE score_observation (
  record_id TEXT NOT NULL,
  metric TEXT NOT NULL,
  value DOUBLE PRECISION,
  unit TEXT NOT NULL,
  role TEXT NOT NULL,
  evaluator_ref TEXT,
  evidence_ref TEXT NOT NULL,
  FOREIGN KEY (record_id) REFERENCES observation(record_id)
);
```

These tables are **illustrative projections**, not a lossless replacement for the canonical record. Production schemas need additional tables for evidence, governance, masking semantics, contract versions, and lineage.

A PDT comparison MUST declare a **comparison contract** covering task equivalence, context matching, history/version boundary, perspective mapping, observation mode, evaluator calibration, and tolerances. Otherwise the system SHOULD return `not_comparable` rather than a fabricated numerical distance.

## 16. Differential Categories

For comparable records \(O_a\) and \(O_b\), define candidate differential categories:

- **Scoring differential:** changed metric/evaluator outcomes under declared calibration.
- **Decision differential:** changed selected action under a common decision context.
- **Trajectory differential:** changed action/feedback sequence across a declared window.
- **Learning differential:** changed revision, policy, or history-dependent behavior with a documented update path.
- **Governance differential:** changed permissions, contract status, or stakeholder evaluation authority.

A score difference does not establish a decision difference; a decision difference does not establish an outcome difference; an outcome difference does not establish learning. The comparison MUST preserve these distinctions.

## 17. Relay and RSI Interoperability

For RSI or LLM-Agent systems, a unit MAY expose observations at the **agent/workflow boundary** rather than at the model's internal representation. An RSI-generated candidate revision SHOULD be recorded as a new immutable unit revision and linked to its evaluation, counter-evidence, and approval outcome.

This enables two-way research:

- RSI proposes candidate policies, tools, workflows, or structural changes.
- UIERU-style observation and contracts evaluate those candidates across perspectives and histories.
- Failed experiments and adverse evidence feed back into future candidate generation.

Such an interface does **not** establish that RSI and UIERU are structurally identical, or that governance improves automatically. These are testable hypotheses.

## 18. Threats to Validity and Security

- **Instrumentation effects:** logging can change latency and behavior.
- **Partial observability:** internal states and external confounders may be hidden.
- **Evaluator gaming:** optimized scores may cease to track intended quality.
- **Selection bias:** only successful or visible executions may be recorded.
- **Replay mismatch:** external services and stochastic sampling may drift.
- **Causal overclaiming:** passive observation may be mistaken for intervention.
- **Privacy leakage:** raw prompts, digests, or traces can expose sensitive data.
- **Lineage tampering:** mutable artifacts can invalidate historical comparisons.
- **Cross-perspective coercion:** one stakeholder's scoring policy may override another's authority.

Mitigations SHOULD include independent evaluators, negative-case retention, signed or hashed immutable artifacts where feasible, access controls, explicit uncertainty, and adversarial sandbox validation.

## 19. Testable Hypotheses

**H1 — Comparison quality.** Explicit context and perspective fields reduce false equivalence claims relative to comparison using outputs alone.

**H2 — Auditability.** Evidence-linked observation records improve independent reconstruction of model-routing decisions compared with unstructured logs.

**H3 — Evolution attribution.** Revision and history linkage reduces misclassification of repeated execution as structural learning.

**H4 — Counter-evidence retention.** Explicit negative evidence and `challenges` links improve detection of regressions after substitution.

**H5 — RSI interoperability.** A subset of LLM-Agent RSI revisions can be represented without disclosing model internals, while retaining enough information for contract-level evaluation.

Each hypothesis requires a specified baseline, dataset, evaluation metric, and falsification criterion before empirical testing. None is asserted as established.

## 20. Minimal Validation Program

1. **Schema tests:** valid/invalid fixtures for field presence, enums, timestamps, missingness, and evidence references.
2. **Replay tests:** paired observations with fixed and drifting dependencies; measure reproducibility.
3. **Perspective tests:** compare identical execution under distinct observation masks and scoring policies.
4. **Differential tests:** verify score, decision, trajectory, and learning differences remain distinguishable.
5. **Substitution tests:** replace a unit under a contract and test whether downstream properties survive.
6. **Adversarial tests:** inject misleading metrics, stale evaluator versions, omitted counter-evidence, and lineage tampering.
7. **Interoperability tests:** exchange records between independent research implementations and check semantic preservation.

A future conformance suite SHOULD publish machine-readable fixtures and expected validation outcomes. This document does not claim that such a suite currently exists.

## 21. Open Formal Problems

**OP-001 — Minimal sufficiency.** What smallest observation schema preserves a chosen family of contract-level behavioral properties?

**OP-002 — Observation equivalence.** Under what conditions do two masked records imply equivalent observable behavior, and when is that inference unsound?

**OP-003 — Composition.** Which local observation properties compose across relay graphs with feedback and shared state?

**OP-004 — Evolution stability.** What conditions guarantee that an observation-based comparison remains valid after bounded unit revisions?

**OP-005 — Query preservation.** Which PASQ queries are invariant under lossless or lossy observation projections?

**OP-006 — Provenance completeness.** What evidence graph is sufficient for independent verification without exposing private internals?

**OP-007 — Causal identifiability.** When can perspective-specific intervention effects be identified from mixed observational and interventional traces?

These are research questions, not solved theorems.

## 22. Open Research Relay Interface

```yaml
research_relay_piece:
  id: "BUI-SPEC-001"
  title: "Dynamic UIERU Observation Model"
  status: "proposed"
  version: "1.0.0"
  authors: ["Sizhe Tan", "GPT-Obot"]
  problem: "Portable, evidence-aware observation of dynamic intelligence units"
  model: "Partial, perspective-conditioned, versioned event records"
  hypotheses: ["H1", "H2", "H3", "H4", "H5"]
  evidence:
    available: ["synthetic illustrative record", "candidate validation rules"]
    missing: ["independent implementations", "empirical validation", "formal proofs"]
  validation: ["schema fixtures", "replay", "differential analysis", "adversarial tests"]
  interfaces:
    upstream: ["BUI-001", "BUI-002", "BUI-003", "BUI-004"]
    downstream: ["SPEC-002", "SPEC-003", "SPEC-004", "RELAY-002", "RELAY-003"]
  counter_evidence_policy: "Preserve failed tests, conflicting traces, and revision history"
  contribution_types: ["formalization", "counterexample", "implementation", "benchmark", "replication"]
```

## 23. Relationship to the BUI-DSI Series

- **BUI-001:** transition from static structural representations to dynamic units.
- **BUI-002 / RELAY-001:** perspective masking semantics and candidate algebra.
- **BUI-003:** perspective differential trees and localization.
- **BUI-004:** PASQ and structural query.
- **BUI-005 / RELAY-002:** conditional behavioral equivalence and substitution.
- **RELAY-003:** composition and contract preservation.
- **BUI-006:** mathematical foundations and open formal problems.
- **BUI-007 / RELAY-004:** careful, testable biological analogies.
- **BUI-008 / RESEARCH-COLLABORATION:** open research relay and contribution governance.
- **RELAY-005:** evidence-driven open structural evolution.
- **SPEC-002–004:** planned companion contracts for masking, differential/query exchange, and research relay pieces.

## 24. Revision and Adoption Policy

Version `1.0.0` is a **research proposal**, not a ratified industry standard. Revisions SHOULD preserve explicit changelogs and migration notes. Breaking changes to record meaning require a major version increment; adding optional namespaced fields can be backward-compatible if existing semantics remain unchanged. A specification amendment SHOULD include motivating evidence, counterexamples, compatibility analysis, and independent review.

Implementers MAY experiment with subsets but MUST state their actual conformance level and deviations. Public adoption should follow—not precede—interoperability tests and independent replication.

## 25. Conclusion

A dynamic UIERU cannot be understood from a single output or score. Its observed behavior is conditioned by task, context, perspective, history, evaluator, contracts, and governance. A portable observation model makes these conditions explicit, links claims to evidence, and creates a basis for comparing, querying, composing, and evolving intelligence units without overstating what is known.

**The core design principle is: observe explicitly, compare conditionally, preserve counter-evidence, and evolve under accountable contracts.**

---

*Research status: proposed formalization and interface. Synthetic examples are illustrative; no empirical validation or mathematical completeness is claimed.*

**Sizhe Tan & GPT-Obot — BUI-DSI v1.0.0**

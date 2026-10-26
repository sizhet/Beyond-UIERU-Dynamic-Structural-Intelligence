# SPEC-002 — Perspective Masking Contract

**Project:** Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay (BUI-DSI)  
**Version:** 1.0.0 (research draft)  
**Status:** Proposed research interchange specification; not a ratified standard or validated implementation  
**Authors:** Sizhe Tan & GPT-Obot  
**Repository path:** `specs/SPEC-002-Perspective-Masking-Contract.md`  
**Related:** SPEC-001 (Dynamic UIERU Observation Model); SPEC-003 (Dynamic Differential and Query Schema, planned); SPEC-004 (Research Relay Piece Contract, planned); BUI-002–006; CASE-001–003; RELAY-001–005

## Abstract

A **Perspective Masking Contract (PMC)** describes how a dynamic intelligence unit, observation record, or relay composition is viewed, filtered, transformed, compared, or deliberately intervened upon from a declared perspective. Its central purpose is to prevent an ambiguous use of the word *mask*: a view that hides fields is not the same operation as a policy that changes a decision, an intervention that changes a running system, or a counterfactual estimate of what might have happened.

This specification proposes a portable contract with typed operators, scope and authority, state and time boundaries, information-loss declarations, evidence provenance, composition conditions, and falsifiable validation obligations. It aims to support Perspective Differential Trees (PDT), Perspective-Aware Structural Query (PASQ), UIERU comparison and relay governance. Mathematical properties are treated as **conditional propositions** requiring explicit assumptions, not universal laws of masking.

## 1. Purpose and Research Position

A dynamic UIERU may change its scores, decisions, action trajectories, and learned structure across contexts, histories, and perspectives. Two observers may legitimately obtain different descriptions of the same event. A comparison is meaningful only if the relevant observation and transformation conditions are declared.

The PMC answers:

1. What is being masked, and for whom?
2. Is the operation read-only, simulated, replayed, or causally applied?
3. Which fields, events, perspectives, and time windows are in scope?
4. What information is removed, aggregated, transformed, or newly inferred?
5. Which comparisons and compositions are authorized and defensible?
6. What evidence could invalidate a masking claim?

**Design rule:** A PMC MUST NOT claim that a masked view explains an underlying mechanism merely because it is easier to inspect.

## 2. Normative Language and Conformance

The terms **MUST**, **MUST NOT**, **SHOULD**, **SHOULD NOT**, and **MAY** denote obligations within this proposed specification, not requirements imposed on existing SI or LLM systems.

| Profile | Name | Required capability |
|---|---|---|
| M1 | Descriptive | Identity, type, scope, operator parameters, source references, declared information loss |
| M2 | Reproducible | M1 plus deterministic semantics where applicable, versioned inputs, output references, validation checks |
| M3 | Differential | M2 plus comparison contract, alignment conditions, uncertainty, PDT/PASQ-ready differential references |
| M4 | Governed | M3 plus authorization, intervention guardrails, provenance, revocation, and counter-evidence handling |

A profile is a contract-completeness level, **not** a claim of superior intelligence or proof of causal validity. Inapplicable fields MUST be marked explicitly rather than silently omitted when their absence could change interpretation.

## 3. Scope and Non-Goals

**In scope:** read-only observation projection; field and event filtering; time-window aggregation; perspective-dependent score selection; versioned replay transformations; sandbox interventions; model-based counterfactual estimation; composed masks; differential analysis; audit and access-control linkage.

**Out of scope:** requiring disclosure of private chain-of-thought, neural weights, personal data, or proprietary implementation details; inferring causal effects from observational filtering alone; claiming that masking algebra is universally commutative or idempotent; treating a synthetic example as measured model performance; imposing a single universal scoring sovereignty.

## 4. Terminology

- **Subject:** unit or composition whose behavior is described.
- **Observer:** actor or process producing a view or estimate.
- **Perspective:** declared valuation, measurement, or query frame, including objectives and constraints.
- **Mask:** typed operator over an identified input domain.
- **View:** resulting representation, which may be lossy.
- **Source observation:** evidence record compatible with SPEC-001.
- **Replay:** re-execution of recorded or frozen conditions with declared determinism limitations.
- **Intervention:** action intended to alter a running or sandboxed system, rather than merely describe it.
- **Counterfactual estimate:** model-dependent claim about an unobserved alternative; not a measured outcome.
- **Differential:** comparison of aligned records under a declared comparison contract.
- **Governance authority:** actor or policy entitled to approve operations on the subject.

## 5. Typed Masking Operators

The contract MUST select exactly one primary `operator_type`. A pipeline MAY contain several steps, each with its own type and lineage.

| Type | Symbol (illustrative) | Input → output | Causal claim permitted? |
|---|---|---|---|
| `OBSERVATION_PROJECTION` | \(P_{\pi}\) | record → view | No |
| `FIELD_FILTER` | \(F_S\) | record → subset | No |
| `TEMPORAL_AGGREGATION` | \(A_W\) | event stream → summary | No |
| `PERSPECTIVE_RESCORING` | \(R_{\pi}\) | evidence/score inputs → derived scores | No, absent intervention |
| `DETERMINISTIC_REPLAY` | \(D_{h}\) | frozen snapshot + inputs → replay trace | Only within replay assumptions |
| `SIMULATION` | \(S_{m}\) | model + scenario → synthetic trace | No real-world causal identification |
| `SANDBOX_INTERVENTION` | \(I_{a}\) | sandbox state → modified state/trace | Limited to tested intervention |
| `COUNTERFACTUAL_ESTIMATE` | \(C_{m,a}\) | causal/model assumptions → estimate | Only conditional on identified model assumptions |

`PERSPECTIVE_RESCORING` changes a *derived evaluation*, not necessarily the unit's actual policy. An implementation MUST distinguish `predicted_decision` from `observed_decision`.

## 6. Minimal Mathematical Semantics

Let an observation domain be \(\mathcal O\), perspective descriptors \(\Pi\), and a view domain \(\mathcal V\). A read-only perspective projection can be represented as

$$
P_{\pi}:\mathcal O\rightarrow\mathcal V_{\pi}, \qquad \pi\in\Pi.
$$

For a stateful system with hidden state \(x_t\), context \(c_t\), history \(h_t\), and policy \(\mu\), a separate intervention operator may alter transition or policy semantics:

$$
x_{t+1}\sim T(x_t,a_t,c_t),\quad a_t\sim\mu(x_t,c_t,h_t),
$$

$$
I_a(T,\mu,x_t)=(T',\mu',x'_t).
$$

These expressions are **candidate modeling abstractions**. They do not imply that a given UIERU exposes an identifiable state-space model or that an observation projection uniquely determines its behavior.

A mask contract is represented conceptually by

$$
\mathrm{PMC}=(\mathrm{id},\mathrm{type},\mathrm{scope},\pi,\mathrm{params},\mathrm{lineage},\mathrm{authority},\mathrm{claims},\mathrm{tests}).
$$

This tuple is an organizational definition, not a theorem.

## 7. Contract Envelope

Every PMC record MUST identify:

| Field | Required | Semantics |
|---|---|---|
| `schema_version` | Yes | Contract schema version, e.g. `1.0.0` |
| `mask_id` | Yes | Stable unique ID for this mask invocation or reusable definition |
| `mask_definition_version` | Yes | Immutable operator definition version |
| `operator_type` | Yes | One of the eight types in Section 5 |
| `subject_ref` | Yes | Unit or composition identifier and version |
| `source_observation_refs` | Conditional | Source event IDs, or explicit `not_applicable_reason` |
| `perspective` | Yes | ID, version, objective, measurement/valuation basis |
| `scope` | Yes | Fields, task/context predicates, time and history boundaries |
| `parameters` | Yes | Operator-specific, typed parameters |
| `output` | Yes | View/trace reference and output status |
| `loss_and_uncertainty` | Yes | Missingness, aggregation loss, uncertainty, non-identifiability |
| `claims` | Yes | Permitted interpretation and forbidden inferences |
| `provenance` | Yes | Producer, timestamp, software/definition references |
| `governance` | Yes | Authorization, access restrictions, retention, revocation |
| `validation` | Yes | Checks performed and unverified assumptions |

All timestamps SHOULD use offset-aware ISO 8601. Content hashes SHOULD use an explicit algorithm and SHOULD NOT be mistaken for semantic equivalence proofs.

## 8. Perspective Descriptor

A perspective MUST NOT be represented solely by a free-text label such as `quality`. It SHOULD declare:

- `perspective_id` and immutable `version`;
- objectives and optimization direction;
- measurements or proxies, including units;
- scoring weights, thresholds, and normalization versions when applicable;
- constraint and veto policies;
- owner or authority for the valuation policy;
- task and context applicability;
- known exclusions and proxy failure risks.

When multiple actors own different perspectives, the contract MUST NOT silently merge their preferences into a single allegedly neutral objective.

## 9. Scope and Alignment Boundaries

A mask's scope SHOULD specify `task_set`, `context_predicate`, `history_snapshot`, `time_window`, `subject_version`, `input_population`, `event_types`, and `field_paths` as applicable.

For comparisons, alignment MUST identify whether the two views share:

1. the same task and input distribution;
2. the same context and time horizon;
3. comparable unit versions and available tools;
4. the same history snapshot or a justified history mapping;
5. the same evidence and measurement definitions;
6. the same permission and privacy restrictions.

If alignment fails, the result MUST be labeled `non_comparable`, `partially_comparable`, or `requires_adjustment`, not silently presented as an ordinary differential.

## 10. Information Loss and Uncertainty

Each contract MUST declare at least one of `lossless`, `lossy`, or `unknown` and describe affected dimensions. A view that omits fields MAY still be valid for a narrow query but MUST NOT be used to claim full-state equivalence.

Relevant loss types include field omission, temporal coarsening, score rounding, identity pseudonymization, sampling, context elision, history truncation, and model-based imputation. Missingness SHOULD be typed as `not_observed`, `not_available`, `withheld`, `not_applicable`, or `unknown`.

Uncertainty SHOULD distinguish measurement error, sampling error, model uncertainty, intervention variance, and identification uncertainty. A single confidence score MUST NOT be presented as resolving all these categories.

## 11. Canonical YAML Example — Read-Only Mask

The following is **synthetic**, illustrative, and not a claim about a deployed model.

```yaml
schema_version: "1.0.0"
mask_id: "pmc-demo-cost-view-001"
mask_definition_version: "1.0.0"
profile: "M3"
operator_type: "OBSERVATION_PROJECTION"
subject_ref:
  unit_id: "synthetic-model-selector"
  unit_version: "demo-1"
source_observation_refs:
  - "obs-demo-1001"
perspective:
  perspective_id: "cost-conscious-selection"
  version: "1"
  owner: "demo-evaluation-authority"
  objectives:
    - metric: "estimated_cost_usd"
      direction: "minimize"
  constraints:
    - metric: "quality_gate"
      rule: "must_pass"
  limitations:
    - "Cost estimate is not a verified bill."
scope:
  task_set: ["synthetic-task-A"]
  context_predicate: "context_id == 'demo-context-1'"
  history_snapshot: "history-demo-v1"
  time_window:
    start: "2026-10-21T10:00:00-07:00"
    end: "2026-10-21T10:05:00-07:00"
  field_paths:
    - "evaluation.estimated_cost_usd"
    - "evaluation.quality_gate"
    - "decision.observed_choice"
parameters:
  projection_mode: "allowlist"
  missing_field_policy: "explicit_missing"
output:
  view_ref: "view-demo-cost-001"
  status: "synthetic_example"
loss_and_uncertainty:
  loss_class: "lossy"
  omitted_dimensions: ["latency", "internal_policy_state"]
  uncertainty:
    - kind: "measurement"
      note: "Estimated cost is approximate."
claims:
  allowed:
    - "Compare disclosed cost estimates within the stated scope."
  prohibited:
    - "Infer an intervention effect."
    - "Infer full behavioral equivalence."
provenance:
  produced_by: "illustrative-spec-author"
  produced_at: "2026-10-21T10:10:00-07:00"
  source_kind: "synthetic"
governance:
  authorization: "read_only_demo"
  data_classification: "synthetic_public"
  retention_policy: "illustrative_only"
  revocation_status: "active"
validation:
  checks:
    - id: "type_matches_operation"
      status: "pass"
    - id: "source_alignment"
      status: "illustrative_not_executed"
  unverified_assumptions:
    - "The synthetic source observation is schema-compatible."
```

A production profile MUST replace illustrative statuses with real evidence or mark validation as pending.

## 12. Intervention Extension

A `SANDBOX_INTERVENTION` contract MUST additionally contain:

- `intervention_target`: policy, tool routing, score weight, state, or environment;
- `baseline_ref` and intervention `treatment_ref`;
- `authorized_actor` and `approval_ref`;
- `sandbox_boundary` and prohibited side effects;
- `rollback_plan` and termination conditions;
- `outcome_measurement_plan`;
- `randomization_or_assignment_method`, if causal estimation is intended;
- `observed_outcome_refs`, distinct from predictions.

An intervention MAY be reported as technically successful without establishing a general causal effect. A mask definition MUST NOT grant operational authority merely by naming an intervention type.

## 13. Counterfactual Extension

A `COUNTERFACTUAL_ESTIMATE` MUST declare the structural or statistical model, intervention semantics, identification assumptions, alternative explanations, model version, and sensitivity tests. It MUST label outputs as `estimated`, not `observed`.

Counterfactual results SHOULD be rejected or downgraded when relevant confounding, unmeasured state, or support mismatch makes the estimand non-identifiable. The absence of a known confounder is not evidence that confounding is absent.

## 14. Composition Semantics

For typed operators \(M_1:A\to B\) and \(M_2:B\to C\), composition \(M_2\circ M_1\) is defined only if the output domain, provenance, scope, authority, and semantic mode of \(M_1\) satisfy the input requirements of \(M_2\).

A composition contract MUST record operator order and MUST reject implicit coercion between read-only views and interventions. It SHOULD retain intermediate lineage so information loss can be attributed to a specific stage.

**Illustrative admissible chain:** field filtering followed by temporal aggregation, if aggregation inputs remain present.

**Illustrative inadmissible inference:** projecting away context and then claiming that the resulting equal scores establish context-independent decision equivalence.

## 15. Conditional Algebraic Properties

The following are **candidate propositions for investigation**, not guaranteed axioms:

| Property | Candidate claim | Conditions / failure modes |
|---|---|---|
| Idempotence | \(P(P(o))=P(o)\) | Same projection definition, stable schema and domain; fails for stateful transformations or repeated rounding |
| Commutativity | \(M_1M_2=M_2M_1\) | Potentially for independent read-only filters; fails for ordered interventions and many aggregations |
| Associativity | \((M_3M_2)M_1=M_3(M_2M_1)\) | Typed pure operators with fixed semantics; may fail if intermediate effects or policies differ |
| Refinement | \(P_{\pi_1}\preceq P_{\pi_2}\) | Requires an explicit information ordering and reconstruction relation |
| Query preservation | \(Q(P(o))=Q(o)\) | Only for queries whose sufficient inputs and semantics are preserved |
| Decision preservation | \(d(P(o))=d(o)\) | Requires decision-relevant sufficiency, stable policy, and matched context/history |
| Relay compatibility | \(R(P(o))\sim P(R(o))\) | Requires typed relay semantics and no hidden feedback or side-effect mismatch |

A proof about a pure projection MUST NOT be extended without justification to learning, feedback, policy changes, or interventions.

## 16. Perspective Differential Contract

A differential comparison SHOULD declare:

```yaml
comparison_id: "comparison-demo-001"
left_view_ref: "view-cost-001"
right_view_ref: "view-quality-001"
alignment:
  same_task: true
  same_context: true
  same_history_snapshot: true
  same_subject_version: true
  evidence_compatible: true
comparison_mode: "paired_observational"
differential_categories:
  - "scoring"
  - "decision"
  - "trajectory"
  - "learning"
causal_claim: false
result_status: "pending_evidence"
```

**Scoring differential** measures evaluation changes; **decision differential** compares choices; **trajectory differential** compares action sequences and outcomes; **learning differential** compares subsequent state or policy changes. A difference in one category does not imply a difference in another.

## 17. PDT and PASQ Interoperability

A Perspective Differential Tree node SHOULD retain `comparison_id`, `perspective_refs`, `context_ref`, `history_ref`, `differential_type`, `magnitude_or_relation`, `evidence_refs`, `uncertainty`, `contract_ref`, and `counter_evidence_refs`.

PASQ implementations SHOULD allow queries over declared evidence without treating missing data as zero or interpreting projection results as intervention outcomes. A conceptual SQL query:

```sql
SELECT d.comparison_id, d.differential_type, d.result_status,
       d.evidence_ref, d.uncertainty_class
FROM perspective_differentials AS d
JOIN masking_contracts AS m
  ON d.left_mask_id = m.mask_id
WHERE m.operator_type = 'OBSERVATION_PROJECTION'
  AND d.alignment_status = 'comparable'
  AND d.causal_claim = FALSE;
```

This is a schema sketch, not an executable migration or a promise that SPEC-003 adopts these exact table names.

## 18. Governance and Evaluation Sovereignty

A perspective may belong to a user, organization, application, or autonomous unit. The PMC MUST identify whose evaluation policy is applied and MUST NOT allow a downstream relay to silently override the owner's hard constraints.

For governed use, record the authority to observe, rescore, simulate, intervene, export, and retain. These permissions are distinct. A unit authorized to observe another unit is not thereby authorized to modify it.

Privacy, access controls, and security checks SHOULD be enforced by the underlying system; recording them in YAML alone does not enforce them. Revocation MUST be reflected in downstream eligibility checks and audit lineage where technically and legally applicable.

## 19. Failure Modes and Counter-Evidence

| ID | Failure mode | Required response |
|---|---|---|
| CE-01 | Mask omits a decision-relevant feature | Mark decision-preservation claim unsupported |
| CE-02 | Same name, changed perspective weights | Reject version-ambiguous comparison |
| CE-03 | Context differs across compared views | Require alignment or restrict claim |
| CE-04 | Temporal aggregation conceals failure spikes | Preserve finer-grained counter-evidence |
| CE-05 | Replay is nondeterministic or incomplete | Declare replay limitations and repeatability bounds |
| CE-06 | Intervention has unrecorded side effects | Suspend causal interpretation and escalate review |
| CE-07 | Counterfactual depends on untested assumptions | Label as model-dependent and require sensitivity analysis |
| CE-08 | Privacy redaction alters query semantics | Mark information loss and constrain downstream queries |
| CE-09 | Learning changes policy between comparisons | Require version/history alignment |
| CE-10 | Relay amplifies a small masked difference | Revalidate system-level contract, not only local view |

Counter-evidence SHOULD be retained with provenance even when it contradicts a favored SI hypothesis. A contract MAY be superseded or revoked without deleting its historical evidence trail.

## 20. Validation Rules

A validator SHOULD implement the following checks, reporting `pass`, `fail`, `not_applicable`, or `not_tested` with evidence:

1. `PM-01`: unique mask ID and schema version.
2. `PM-02`: recognized operator type and valid type-specific parameters.
3. `PM-03`: immutable subject and mask definition versions.
4. `PM-04`: explicit perspective owner and valuation definition.
5. `PM-05`: explicit context, time, and history boundaries.
6. `PM-06`: source observation references resolve or absence is justified.
7. `PM-07`: output kind matches operator type.
8. `PM-08`: information loss and missingness declared.
9. `PM-09`: observed, simulated, and estimated values cannot be conflated.
10. `PM-10`: read-only operations do not assert intervention effects.
11. `PM-11`: interventions include authorization and rollback boundaries.
12. `PM-12`: counterfactuals include identification and sensitivity assumptions.
13. `PM-13`: composed operators are type-compatible and ordered.
14. `PM-14`: comparisons include alignment and comparability status.
15. `PM-15`: governance permissions cover the actual operation.
16. `PM-16`: provenance and evidence references are auditable.
17. `PM-17`: claimed conformance profile requirements are satisfied.
18. `PM-18`: counter-evidence and revocation status propagate to dependent claims.

Passing schema validation does **not** prove causal validity, behavioral equivalence, security, or fitness for deployment.

## 21. Conformance Test Suite (Proposed)

| Test | Setup | Expected outcome |
|---|---|---|
| T-01 | Pure allowlist projection twice on immutable record | Idempotence may hold under declared equality semantics |
| T-02 | Aggregate then filter vs filter then aggregate | Demonstrate noncommutativity where filters affect aggregation inputs |
| T-03 | Compare different perspective versions without version mapping | Comparison rejected or restricted |
| T-04 | Replace missing latency with zero | Validation fails missingness semantics |
| T-05 | Label a simulated outcome as observed | Validation fails provenance and claim type |
| T-06 | Invoke sandbox intervention with read-only permission | Authorization fails |
| T-07 | Learning update between paired observations | Requires history/version realignment |
| T-08 | Compose projection with query needing omitted fields | Query-preservation claim fails |
| T-09 | Substitute UIERU based only on masked scores | Substitution not certified |
| T-10 | Attach new counter-evidence to a previously accepted claim | Revalidation or revocation triggered |

Test outcomes are *expected normative behavior*, not reports of an implemented test runner.

## 22. Testable Research Hypotheses

**H1 — Explicit semantics improve interpretation.** Typed masking contracts reduce confusion between observational and intervention claims relative to untyped view descriptions. *Test:* blinded interpretation study with matched tasks.

**H2 — Provenance reduces false equivalence.** History/context-aware masking reduces false positive equivalence findings compared with score-only comparisons. *Test:* controlled synthetic UIERU pairs with known hidden-state differences.

**H3 — Conditional algebra is tractable.** A useful nontrivial subset of pure projection/filter operators admits machine-checkable composition laws. *Test:* formalize operators and produce proofs plus minimal counterexamples.

**H4 — Differential indexing improves investigation.** PDT/PASQ-compatible masking records improve retrieval of perspective-dependent decision changes compared with unstructured logs. *Test:* preregistered retrieval benchmarks with accuracy and cost metrics.

**H5 — Governance catches unsafe reinterpretation.** Permission-aware contracts prevent more unauthorized intervention attempts than metadata-only records. *Test:* adversarial sandbox with enforcement, not merely schema declarations.

**H6 — RSI observability benefits.** UIERU-like masking of LLM-Agent RSI traces improves structural auditability without requiring model-internal explanations. *Test:* compare audit coverage and overhead across systems; distinguish auditability from mechanistic interpretability.

All hypotheses are unverified until evaluated; negative results SHOULD be published.

## 23. Open Formal Problems

1. Define a typed algebra of projections, aggregations, and stateful interventions without collapsing their distinct semantics.
2. Characterize maximal subclasses of masks that are idempotent, commutative, or associative.
3. Define a partial information order that handles missingness, privacy redaction, and uncertainty.
4. Establish sufficient conditions for query preservation under perspective projection.
5. Establish conditions under which a mask preserves a decision policy over a specified input distribution.
6. Relate masking-induced observational equivalence to approximate behavioral bisimulation.
7. Derive compositional error bounds for relay pipelines with lossy masks.
8. Formalize counterfactual identification limits when UIERU state and history are only partially observed.
9. Specify temporal validity of masking claims under learning and recursive self-improvement.
10. Design machine-checkable proof obligations and counterexample certificates for PMC claims.

These are research invitations, not solved propositions.

## 24. Minimal Validation Roadmap

**Phase A — Syntax and semantics:** publish a JSON Schema or equivalent typed validator, example fixtures, and a precise operator semantics document.

**Phase B — Algebra and counterexamples:** test projection identities and noncommutativity with property-based testing; pursue formal proofs for restricted operators.

**Phase C — Dynamic UIERU replay:** capture SPEC-001 records, apply read-only masks, and measure scoring/decision/trajectory/learning differentials.

**Phase D — Intervention and governance:** compare replay, simulation, and sandbox interventions; test authorization and evidence provenance.

**Phase E — Open research relay:** release reproducible cases, counterexamples, formal conjectures, and versioned results with independent review.

Every phase SHOULD report implementation cost, coverage gaps, false positives, and conditions under which the approach fails.

## 25. Research Relay Piece Interface

```yaml
research_relay_piece:
  id: "RELAY-PMC-ALGEBRA-001"
  title: "Typed Perspective Masking and Preservation Conditions"
  problem: "When do masking operations preserve queries, decisions, or relay contracts?"
  model:
    objects: ["observation", "perspective", "typed_mask", "view", "contract"]
    assumptions:
      - "Operator types have explicit input/output domains."
      - "Context and history boundaries are declared."
  hypotheses:
    - "Restricted pure projections admit checkable preservation laws."
  evidence:
    positive: []
    counter_evidence: []
    status: "open"
  validation:
    methods: ["formal_proof", "property_based_testing", "paired_replay"]
    acceptance: "Publish assumptions, proofs or counterexamples, and reproducible fixtures."
  interfaces:
    observation_spec: "SPEC-001"
    masking_spec: "SPEC-002"
    differential_spec: "SPEC-003-planned"
  provenance:
    authors: ["Sizhe Tan", "GPT-Obot"]
    version: "1.0.0"
```

The interface is illustrative; SPEC-004 will define the canonical Research Relay Piece contract.

## 26. Relationship to the BUI-DSI Research Program

- **BUI-002** motivates perspective masking as dynamic structural observation.
- **BUI-003** connects masking to Perspective Differential Trees and localization.
- **BUI-004** connects masked views to Perspective-Aware Structural Query.
- **BUI-005–006** motivate dynamic equivalence, compositionality, and formal open problems.
- **CASE-001** offers a model-selection setting in which scores and decisions must remain distinct.
- **CASE-002** shows why masking alone cannot certify relay substitution.
- **CASE-003 / RELAY-004** caution against mistaking observational similarity for biological mechanism identity.
- **RELAY-001** is the mathematical research agenda; **SPEC-002** is its proposed exchange contract.
- **SPEC-001** provides observation records; **SPEC-003** is expected to provide differential/query schemas; **SPEC-004** will formalize research relay exchange.

The contract may also describe LLM-Agent RSI traces through observable interfaces. Such use does not imply that an LLM's internal computation is fully transparent or that RSI and UIERU are architecturally equivalent.

## 27. Versioning, Compatibility, and Adoption

The schema version identifies this proposal, not a standards-body endorsement. A change to operator meaning, causal claim rules, or required governance semantics SHOULD increment the major version. New optional fields with backward-compatible defaults MAY increment the minor version. Editorial fixes MAY increment the patch version.

Consumers MUST NOT silently reinterpret old records using newer perspective definitions. Implementations SHOULD preserve original records, explicit migrations, and immutable source references. Formal conformance requires published validation fixtures and implementation evidence; this draft does not claim such certification.

## 28. Conclusion

Perspective Masking becomes scientifically and operationally useful when its semantics are explicit: **a view is not an intervention; a score is not a decision; a decision is not a trajectory; and a trajectory is not proof of learning**. The proposed PMC provides a common interface for making those distinctions inspectable, comparable, and open to counter-evidence.

The larger goal is not to declare a completed masking algebra. It is to offer a disciplined research boundary at which SI engineers, formal-methods researchers, LLM/RSI practitioners, and other investigators can exchange problems, proofs, failures, and improvements through Open Research Relay.

---

**Citation / attribution:** Sizhe Tan & GPT-Obot. *SPEC-002 — Perspective Masking Contract*. BUI-DSI research draft, v1.0.0, 2026. This document is a proposed specification, not a verified implementation or ratified standard.

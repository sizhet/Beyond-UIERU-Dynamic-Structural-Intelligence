# SPEC-004 — Research Relay Piece Contract

**Project:** Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay (BUI-DSI)  
**Version:** 1.0.0 (proposed research specification)  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Draft specification for research interoperability; not a ratified standard  
**Repository location:** `specs/SPEC-004-Research-Relay-Piece-Contract.md`

## Abstract

A Research Relay Piece (RRP) is a portable, versioned research object designed to convey not merely a conclusion but a tractable problem, its assumptions, competing hypotheses, supporting and countervailing evidence, validation obligations, and interfaces for independent continuation. This specification defines a minimal contract, an extensible record schema, validation rules, lifecycle states, provenance requirements, and cross-disciplinary handoff procedures. It complements SPEC-001 (dynamic observation), SPEC-002 (perspective masking), and SPEC-003 (dynamic differential and query). The purpose is to make open structural-intelligence research *contestable, reproducible where feasible, composable, and evolvable*. It does not assert that proposed UIERU mechanisms are proven, or that biological systems literally implement them.

## 1. Scope and non-goals

This document specifies how a research problem and its evolving evidence are packaged for relay among independent contributors. It applies to mathematical propositions, experimental protocols, computational hypotheses, negative results, implementation comparisons, and interdisciplinary analogies.

It does **not** prescribe a universal scientific method, certify truth, replace peer review, guarantee reproducibility, or grant automatic permission to share restricted data. The contract describes research claims and their traceability, not an intrinsic measure of scientific merit.

Normative keywords **MUST**, **MUST NOT**, **SHOULD**, and **MAY** describe requirements for implementations claiming conformance to this proposed specification.

## 2. Research Relay versus artifact transfer

A document can be copied without transferring the conditions needed to evaluate it. A useful research relay transfers:

1. The question and its boundary conditions.
2. The formal or operational model and assumptions.
3. Competing, falsifiable hypotheses.
4. Evidence, uncertainty, provenance, and counter-evidence.
5. An executable or inspectable validation pathway, where feasible.
6. Interfaces, dependencies, and attribution for subsequent research.

A relay is successful when a receiving investigator can identify what remains unresolved and how their contribution could change the record. Success does not require agreement with the originating hypothesis.

## 3. Canonical RRP model

Define an RRP as

\[
R = (P, M, H, E, V, I; G, L),
\]

where the six core components are:

- **P — Problem:** research question, scope, intended contribution, exclusions.
- **M — Model:** definitions, assumptions, variables, observation and comparison conditions.
- **H — Hypotheses:** competing propositions, predictions, and failure conditions.
- **E — Evidence:** supporting observations, counter-evidence, limitations, and provenance.
- **V — Validation:** tests, proof obligations, protocols, acceptance/rejection criteria.
- **I — Interfaces:** related work, data/schema interfaces, dependencies, handoff tasks.

Two governance envelopes are required for trustworthy exchange:

- **G — Governance:** ethics, permissions, safety, privacy, evaluator independence, and decision authority.
- **L — Lineage:** stable identifiers, authorship, revisions, forks, supersession, and citations.

The notation is an organizing abstraction, **not** a theorem about research completeness.

## 4. Unit identity and granularity

An RRP SHOULD be small enough that its central research question can be independently investigated. A large research agenda SHOULD be decomposed into linked RRPs, each with one primary problem and explicitly identified subproblems.

Every RRP MUST have a stable `rrp_id`, a version, a title, a lifecycle status, a named maintainer or maintaining group, and an origin reference. Identifiers MUST remain stable across revisions. Substantive changes SHOULD increment the version and preserve prior records. A fork MUST declare its parent and must not silently impersonate the original.

## 5. Required schema fields

| Field | Requirement | Purpose |
|---|---|---|
| `schema_version` | MUST | Interchange contract version |
| `rrp_id`, `version`, `title`, `status` | MUST | Identity and lifecycle |
| `authors`, `maintainers`, `created_at`, `updated_at` | MUST | Accountability and lineage |
| `problem` | MUST | Question, scope, exclusions |
| `model` | MUST | Terms, assumptions, observables |
| `hypotheses` | MUST | At least one testable claim or explicitly open proposition |
| `evidence` | MUST | Evidence register, possibly empty with explanation |
| `validation` | MUST | Proof/test tasks and evaluation criteria |
| `interfaces` | MUST | Inputs, outputs, dependencies, handoff |
| `governance` | MUST | Access, ethics, risks, authority |
| `lineage` | MUST | Origin, relations, citation policy |
| `uncertainties` | SHOULD | Unknowns and unresolved confounders |
| `counterexamples` | SHOULD | Known failures or search plan |
| `artifacts` | SHOULD | Code, datasets, diagrams, notebooks, proofs |

Empty evidence is permitted for a newly proposed problem, but it MUST be marked `not_yet_collected` rather than presented as validation.

## 6. Canonical YAML example

The following record is **illustrative**, not an empirical finding or an implementation-ready JSON Schema.

```yaml
schema_version: "1.0.0"
rrp_id: "bui-rrp-masking-001"
version: "1.0.0"
title: "Conditions for perspective-mask composition"
status: "open"
authors:
  - "Sizhe Tan"
  - "GPT-Obot"
maintainers:
  - "BUI-DSI research maintainers"
created_at: "2026-10-21"
updated_at: "2026-10-25"
problem:
  question: "Under what conditions do two observational masks commute?"
  scope: ["finite observation records", "typed projection operators"]
  exclusions: ["causal interventions", "unrestricted counterfactual claims"]
  motivation: "Support reliable perspective-aware comparison"
model:
  definitions:
    - "M_a and M_b are typed observational transformations"
  assumptions:
    - "Both masks operate on the same immutable source snapshot"
    - "Their output types and compositions are well defined"
  observables: ["input record", "mask definitions", "result records"]
  comparison_contract:
    context_id: "example-context"
    perspective_ids: ["a", "b"]
    time_window: "fixed snapshot"
hypotheses:
  - id: "H1"
    kind: "candidate_proposition"
    claim: "Independent field projections commute under compatible schemas"
    expected_result: "M_a(M_b(x)) = M_b(M_a(x))"
    falsifier: "A valid counterexample under the stated assumptions"
  - id: "H2"
    kind: "competing_hypothesis"
    claim: "Schema-dependent filtering can make composition order-sensitive"
    expected_result: "At least one well-typed counterexample exists"
evidence:
  collection_status: "not_yet_collected"
  items: []
  counter_evidence_items: []
validation:
  proof_obligations:
    - "Formalize projection domains and type preservation"
  empirical_tests:
    - "Enumerate small typed records and compare both compositions"
  acceptance_criteria:
    - "Proof checked against declared assumptions, or reproducible tests"
  rejection_criteria:
    - "Well-formed counterexample invalidates an unrestricted claim"
  limitations:
    - "Finite enumeration does not prove the general proposition"
interfaces:
  depends_on:
    - "specs/SPEC-002-Perspective-Masking-Contract.md"
  input_schema: "SPEC-001 observation reference"
  output_schema: "proof, counterexample, or experimental report"
  handoff_tasks:
    - "Specify algebraic domains"
    - "Provide smallest counterexample"
governance:
  access: "public-metadata"
  data_policy: "no restricted data in public records"
  risk_level: "low"
  review_authority: "named maintainers; independent verification encouraged"
lineage:
  origin: "research-relay/RELAY-001-Perspective-Masking-Algebra.md"
  parents: []
  supersedes: []
  citation: "Cite RRP ID, version, authors, and original artifact"
uncertainties:
  - "Which schema transformations preserve well-typed composition?"
artifacts: []
```

## 7. Claim types and epistemic status

Every central claim MUST identify its type:

| Type | Meaning | Permitted wording |
|---|---|---|
| `definition` | Convention established by this work | "We define..." |
| `candidate_proposition` | Formal claim awaiting proof | "We conjecture..." |
| `proved_result` | Proof with inspectable assumptions | "Under assumptions A, theorem T follows..." |
| `empirical_hypothesis` | Testable prediction | "We hypothesize..." |
| `observed_result` | Measured result with provenance | "In dataset D, we observed..." |
| `analogy` | Structural comparison, not identity | "This suggests a possible analogy..." |
| `engineering_design` | Proposed mechanism | "The design aims to..." |
| `open_question` | Unresolved question | "It remains unknown whether..." |

A claim MUST NOT be promoted from `candidate_proposition` to `proved_result` merely because simulations support it. A biological analogy MUST NOT be promoted to a biological mechanism without relevant evidence. A prototype MUST NOT be described as a validated general architecture solely on the basis of synthetic demonstrations.

## 8. Assumptions and validity domains

Each hypothesis SHOULD identify a validity domain

\[
\mathcal{D} = (\mathcal{C}, \mathcal{P}, \mathcal{H}, T, \mathcal{O}, \epsilon),
\]

where context, perspective, history, time horizon, observation semantics, and tolerance are explicitly represented when relevant. Claims of dynamic equivalence MUST state which observations are compared and which variations are allowed. A validity-domain change MUST trigger re-evaluation or a new version of the claim.

## 9. Evidence object contract

Each evidence item SHOULD contain:

```yaml
id: "evidence-001"
kind: "experiment"   # experiment | proof | simulation | observation | critique
claim_ids: ["H1"]
stance: "supports"   # supports | contradicts | inconclusive | contextualizes
source_uri: "https://example.org/replace-with-real-artifact"
source_hash: null
collection_time: null
method: "specified in attached protocol"
context: "declared experiment conditions"
provenance: "collector and transformation history"
uncertainty: "not yet quantified"
independence: "unknown"
access: "metadata_only"
limitations: ["illustrative record; no actual experiment performed"]
```

The placeholder URI above MUST be replaced or omitted before publication. Evidence metadata MUST distinguish raw observations from transformed or inferred outputs. Supporting and contradicting evidence SHOULD be retained together rather than filtered by favored conclusion.

## 10. Counter-evidence as a first-class object

Counter-evidence is not an optional criticism appended after publication. It is a structured input to the research lifecycle. Each counterexample MUST specify the challenged claim, applicable assumptions, observed failure, and reproducibility status. When a counterexample invalidates a broad claim, maintainers SHOULD narrow, withdraw, or revise the claim and retain the earlier record in lineage.

A minimal counterexample report includes `counterexample_id`, `target_claim_id`, `conditions`, `procedure`, `observed_failure`, `reproducibility`, `evidence_links`, and `disposition`.

## 11. Validation contract

Validation MUST distinguish:

- **Formal verification:** mathematical proof, proof assistant output, or independently checkable derivation.
- **Empirical evaluation:** measurements under a declared protocol and uncertainty model.
- **Computational exploration:** simulations, search, or finite tests that inform but do not establish universal results.
- **Replication:** independent reproduction with relevant conditions matched.
- **Adversarial evaluation:** targeted attempts to falsify a claim, reveal Goodhart effects, or expose contract violations.

Each validation plan SHOULD name a baseline, comparator, outcome measures, stopping rules, failure criteria, and the person or group authorized to interpret results. Absence of counterexamples is not itself proof.

## 12. Lifecycle and state transitions

Recommended states are:

`draft -> open -> under_review -> validated_scope_limited`

with alternate transitions to `contested`, `revised`, `superseded`, `withdrawn`, or `archived`.

`validated_scope_limited` denotes evidence or proof only within declared conditions. It MUST NOT be interpreted as universal truth. `contested` is a legitimate research state, not a failure of collaboration. A state transition MUST record the rationale, responsible party, time, and linked evidence.

## 13. Composition of research pieces

RRPs MAY form a directed dependency graph. Edges SHOULD be typed as `depends_on`, `extends`, `contradicts`, `tests`, `implements`, `generalizes`, or `supersedes`. A composition is *research-compatible* only if the required definitions, assumptions, and interface versions can be reconciled; compatible file formats alone are insufficient.

If RRP B uses a theorem from RRP A, B MUST reference A's version and validity conditions. If A is subsequently weakened, the dependency graph SHOULD flag B for review. This is a proposed mechanism for **two-way research relay**: new findings flow forward, while counter-evidence and changed assumptions propagate backward through affected claims.

## 14. Research sovereignty and attribution

The originating authors retain attribution for their published work; contributors retain attribution for independent results. An RRP contract MUST distinguish origin, contribution, review, and adoption. An open research problem does not imply ownership of all future solutions, nor does linking a later result imply endorsement by its originators.

A contribution policy SHOULD cover citations, license compatibility, contributor consent, conflict of interest, authorship disputes, and versioned acknowledgment. Scientific priority claims require independent historical scholarship; this specification does not establish novelty merely by naming a concept.

## 15. Privacy, safety, and ethical review

Public RRPs MUST NOT expose private participant records, credentials, or restricted datasets. Human and animal studies require appropriate ethics review and domain-specific safeguards. Safety-sensitive RSI experiments SHOULD use scoped permissions, rollback plans, independent evaluators, and sandbox boundaries. Research transparency does not override legal or ethical restrictions.

## 16. Cross-disciplinary relay profiles

**Mathematics / theoretical CS:** formal objects, assumptions, candidate propositions, countermodels, proof obligations, and proof artifacts.

**AI engineering / RSI:** system boundaries, evaluator design, reproducible traces, cost/quality/latency measures, safety contracts, and rollback evidence.

**Neuroscience / biology:** biological operationalization, task protocols, confounders, observational versus interventional evidence, and limitations of structural analogy.

**Governance / human factors:** decision authority, auditability, stakeholder perspectives, contested objectives, and misuse risk.

These profiles extend the common contract; none may omit the core epistemic-status and provenance fields.

## 17. Relationship to the BUI-DSI specification chain

| Specification | Primary concern | RRP link |
|---|---|---|
| SPEC-001 | Dynamic UIERU observation records | Reference trace and evidence objects |
| SPEC-002 | Perspective masking operations | Declare observation semantics and masking assumptions |
| SPEC-003 | Dynamic differential, PDT, PASQ | Register comparison contracts and reproducible queries |
| SPEC-004 | Research relay and claim lifecycle | Connect problems, validation, contributions, and revision |

An RRP may refer to observation and query artifacts without copying their entire contents. References MUST be resolvable or explicitly marked unavailable.

## 18. Conformance levels

**RRP-L1 — Descriptive:** identity, P/M/H/E/V/I, governance, lineage, explicit claim status.

**RRP-L2 — Traceable:** L1 plus evidence identifiers, versioned assumptions, provenance, typed dependencies, and revision history.

**RRP-L3 — Reproducible:** L2 plus inspectable validation protocols and artifacts, or an explicit explanation of non-reproducibility constraints.

**RRP-L4 — Federated:** L3 plus interoperable cross-repository references, change notifications, counter-evidence propagation, and independent review pathways.

A record MUST NOT claim a higher level when a required capability is absent. Reproducibility limitations MUST be disclosed, not concealed.

## 19. Validation rules

An implementation claiming RRP-L1 or higher MUST check:

1. `rrp_id`, version, title, and status are present and nonempty.
2. Required P/M/H/E/V/I sections are present.
3. At least one hypothesis or open proposition is explicitly typed.
4. Evidence status distinguishes uncollected from supportive evidence.
5. Every evidence item points to a claim or identifies its general relevance.
6. Validation criteria distinguish success, failure, and inconclusive outcomes.
7. Governance identifies access constraints and review authority.
8. Lineage includes origin and citation information.
9. Referenced artifacts do not masquerade as available when inaccessible.
10. Biological analogies are not labeled empirical findings without evidence.
11. Mathematical conjectures are not labeled proofs without checkable derivations.
12. Claims about RSI improvements identify evaluator, baseline, and conditions.

L2 additionally SHOULD verify dependency versions and source provenance. L3 SHOULD test reproduction steps where permitted. L4 SHOULD test change propagation and conflict handling.

## 20. Failure modes and adversarial tests

| Failure | Example | Required response |
|---|---|---|
| Assumption laundering | Broad theorem inferred from restricted tests | Restore validity domain |
| Evidence laundering | Simulation presented as real-world measurement | Relabel and correct provenance |
| Citation drift | Dependent claim cites superseded version | Trigger dependency review |
| Confirmation bias | Negative trials excluded | Register counter-evidence |
| Goodhart pressure | Metric improves while safety worsens | Multi-perspective evaluation |
| Hidden intervention | Masking operation changes execution | Reclassify operation |
| False biological equivalence | Analogous behavior treated as identical mechanism | Separate analogy from evidence |
| RSI self-certification | Modified evaluator validates its own changes | Independent evaluation |
| Permission leakage | Restricted data shared in open artifact | Remove and initiate review |
| Attribution erasure | Derived result loses provenance | Restore lineage and credit |

## 21. Open formal and engineering questions

1. Can RRP dependencies be assigned a compositional semantics that detects assumption incompatibility?
2. What is the smallest evidence representation that preserves reproducible disagreement?
3. Under what conditions can counter-evidence propagation be sound but not excessively disruptive?
4. How should probabilistic evidence and formal proof coexist in a common claim graph?
5. Can perspective-specific evaluations be compared without imposing a single sovereign objective?
6. Which portions of the RRP contract are machine-checkable, and which necessarily require expert judgment?
7. Can RSI-generated research candidates be admitted without allowing self-certification of validity?
8. How should long-lived research pieces handle changing datasets, models, and measurement regimes?
9. What provenance guarantees are feasible for federated research ecosystems?
10. When does decomposing a problem into RRPs improve research efficiency versus create coordination overhead?

These are research questions, not claimed solved properties.

## 22. Testable hypotheses

**H1 — Handoff completeness:** Compared with narrative-only descriptions, RRP-formatted problems reduce missing-assumption errors in independent handoffs. *Test:* randomized task allocation; measure omissions and clarification cycles.

**H2 — Counterexample discoverability:** Structured counter-evidence fields improve detection of invalid broad claims. *Test:* blinded reviewers on matched claim sets.

**H3 — Provenance resilience:** Typed lineage reduces citation drift after claim revision. *Test:* controlled version-update experiment.

**H4 — Interdisciplinary transfer:** Explicit interfaces increase the rate at which researchers from a second discipline can formulate valid follow-up tests. *Test:* matched interdisciplinary teams and rubric-based scoring.

**H5 — Governance effectiveness:** Independent evaluator declarations reduce unsupported RSI improvement claims. *Test:* compare audit findings with and without required evaluator separation.

**H6 — Overhead tradeoff:** RRP structure adds initial documentation cost; net benefit depends on task complexity and collaboration scale. *Test:* track preparation time, rework, and downstream validation quality.

All hypotheses require preregistered measures and suitably controlled evaluation before any efficacy claim.

## 23. Suggested validation roadmap

**Phase 0 — Schema review:** Check terminology, minimality, and compatibility with SPEC-001–003.

**Phase 1 — Manual pilots:** Encode RELAY-001 through RELAY-005 as RRPs and collect omissions and ambiguities.

**Phase 2 — Cross-team handoff:** Ask independent mathematics, AI, and biology reviewers to continue selected problems.

**Phase 3 — Adversarial review:** Introduce conflicting evidence, invalid assumptions, and version changes; measure detection and correction.

**Phase 4 — Machine-readable interoperability:** Develop JSON Schema, validators, and optional query interfaces as separate future deliverables.

**Phase 5 — Federated research relay:** Evaluate cross-repository lineage, governance, and attribution under real collaboration conditions.

No phase should be described as completed unless supporting artifacts are publicly available or their access restrictions are documented.

## 24. Research Relay Piece submission checklist

- [ ] Problem and exclusions are explicit.
- [ ] Key terms and assumptions are defined.
- [ ] Claims have correct epistemic labels.
- [ ] Supporting evidence and counter-evidence are separately traceable.
- [ ] Validation includes falsification or failure conditions.
- [ ] Perspectives, contexts, and comparison contracts are specified when applicable.
- [ ] Artifacts and dependencies are versioned.
- [ ] Privacy, safety, and evaluator governance are addressed.
- [ ] Contributor credit and licensing are clear.
- [ ] Unresolved questions are visible to the next researcher.

## 25. Research Relay examples in this repository

- `research-relay/RELAY-001-Perspective-Masking-Algebra.md`: algebraic properties and counterexamples.
- `research-relay/RELAY-002-Dynamic-Behavioral-Equivalence.md`: context-bounded equivalence and approximate bisimulation.
- `research-relay/RELAY-003-Relay-Composition-and-Contracts.md`: contract-preserving composition and substitution.
- `research-relay/RELAY-004-Biological-Dynamic-Intelligence.md`: biological hypotheses and empirical constraints.
- `research-relay/RELAY-005-Open-Structural-Evolution.md`: governed structural change and open-ended learning.
- **Proposed extension:** `research-relay/RELAY-006-RSI-UIERU-Convergence-and-Structural-Governance.md`: two-way RSI/UIERU interfaces; not assumed to exist until authored.
- `research-relay/RESEARCH-COLLABORATION.md`: collaboration procedures and contributor expectations.

## 26. Versioning and compatibility

The `schema_version` describes the interchange format; `version` describes the individual research piece. A backward-incompatible change to required field meaning SHOULD increment the schema's major version. New optional fields MAY be added in a minor revision. Every revision SHOULD include a changelog describing changed assumptions, evidence, and dependent claims.

An RRP receiving an unknown field SHOULD preserve it where possible but MUST NOT silently reinterpret a known field. Missing required fields MUST be reported as validation errors rather than filled with invented values.

## 27. Limitations

The contract cannot ensure that a hypothesis is important, an evaluator is independent, or a biological analogy is sound. It cannot resolve scientific disputes automatically. Formal metadata may also become performative bureaucracy; its costs should be measured against improvements in collaboration and rigor. Some research requires confidentiality or embargo, in which case a public RRP can share only permitted metadata and disclose the limits of inspection.

## 28. Conclusion

The Research Relay Piece Contract provides a proposed unit of exchange for open, dynamic structural-intelligence research. Its central contribution is not a new claim of intelligence or an asserted mathematical theorem. It is an explicit mechanism for carrying **questions, assumptions, hypotheses, evidence, counter-evidence, validation, interfaces, governance, and lineage** across research boundaries.

The long-term objective is a research ecosystem in which a useful problem can be inherited, challenged, refined, and extended without erasing its provenance or confusing conjecture with established knowledge. This is the research-level counterpart of the UIERU vision of structured, governed, and open-ended intelligence evolution.

---

**Suggested citation:** Tan, Sizhe, and GPT-Obot. *SPEC-004: Research Relay Piece Contract*. Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay, version 1.0.0, 2026. Cite a DOI only after it has actually been registered.

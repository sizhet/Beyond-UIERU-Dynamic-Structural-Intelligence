# RELAY-003 — Relay Composition and Contracts

**Project:** Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay (BUI-DSI)  
**Research Relay Piece:** RELAY-003  
**Version:** 1.0.0 — 2026-10-25  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Open research agenda; candidate definitions and falsifiable propositions, not established theorems

## Abstract

Dynamic intelligence systems rarely act as isolated units. They delegate tasks, transfer context, call tools, exchange evidence, revise policies, and adapt over time. The Universal Intelligence Evolution and Relay Unit (UIERU) perspective treats such exchanges as **Relay**: structured transfers of information, responsibility, control, and potentially learned capability. This research relay piece asks a central compositional question: *Under which assumptions can properties established for individual dynamic intelligence units be preserved when those units are connected, replaced, or evolved?* We propose a typed contract model, an explicit semantics for relay events, a candidate composition operator, and proof obligations for safety, liveness, provenance, and perspective-sensitive scoring. We identify counterexamples to naive compositionality, distinguish behavioral compatibility from contract refinement, and provide a staged empirical and formal validation program. No universal composition theorem is claimed.

**Keywords:** structural intelligence; UIERU; relay; assume–guarantee reasoning; interface contracts; compositional verification; dynamic equivalence; provenance; structural evolution; recursive self-improvement.

---

## 1. Why Relay Composition Is a Foundational Problem

A useful intelligence unit may have a reliable local evaluator, a clear task interface, and strong test performance. None of these properties alone guarantees reliable operation when it is embedded in a larger system. Upstream units may provide incomplete context; downstream units may interpret a score differently; two individually safe actions may interact unsafely; and an update to one unit may invalidate a contract previously satisfied by the network.

The central distinction is:

> **Local competence does not imply system-level contract preservation.**

The research goal is not to impose a single execution architecture. It is to discover conditions under which heterogeneous intelligence units—LLMs, rule systems, optimizers, retrieval components, humans, or hybrid assemblies—can relay work with explicit obligations and auditable evidence.

### 1.1 Scope

This piece studies:

- Typed exchange and delegation between dynamic units.
- Composition of interface, behavioral, and temporal contracts.
- Perspective-sensitive scoring and authority boundaries.
- State, history, provenance, and counter-evidence propagation.
- Contract-preserving replacement and evolution.
- Failures caused by cycles, concurrency, nondeterminism, and partial observation.

It does **not** assume that a unit's internal reasoning is transparent, that all units share one scoring scale, or that composition is associative in every operational setting.

## 2. Relation to the BUI-DSI Research Program

This piece extends the dynamic-unit foundations in **BUI-001**, observation and masking in **BUI-002**, differential localization in **BUI-003**, structural querying in **BUI-004**, equivalence and composition in **BUI-005**, formal questions in **BUI-006**, biological organizational analogies in **BUI-007**, and open research transfer in **BUI-008**.

Its immediate companion is **RELAY-002**, which asks when two units are dynamically equivalent. RELAY-003 asks a stronger question: **When does replacing one unit by an equivalent or contract-refining unit preserve the properties of the surrounding Relay system?**

The worked cases are **CASE-001** (perspective-masked model selection), **CASE-002** (dynamic equivalence and substitution), and **CASE-003** (context-dependent biological intelligence). Biological parallels are exploratory abstractions, not claims of neural implementation.

## 3. Minimal Dynamic UIERU Model

Let a unit be a labeled, possibly stochastic, evolving transition system:

\[
U=(X,I,O,P,\Theta,\mathcal{A},T,G,E),
\]

where:

- \(X\) is internal state, including relevant history;
- \(I,O\) are typed input and output spaces;
- \(P\) is the set of perspectives or evaluation contexts;
- \(\Theta\) is the policy/scoring configuration;
- \(\mathcal A\) is the action alphabet;
- \(T\) governs state, action, and output transitions;
- \(G\) is an admissible learning or structural-update relation;
- \(E\) represents evidence and provenance records.

A transition may be represented as

\[
(x_{t+1},o_t,e_t)\sim T_U(x_t,i_t,p_t,\theta_t),
\qquad
\theta_{t+1}\sim G_U(\theta_t,e_t).
\]

The notation intentionally permits deterministic or stochastic implementations. A real implementation must specify which state and event fields are observable, which are private, and which are required by contract.

## 4. A Typed Relay Event

Define a relay event as a structured record

\[
r=(id,s,d,k,v,c,p,a,h,\pi,\tau),
\]

with sender \(s\), destination \(d\), message kind \(k\), payload \(v\), context reference \(c\), perspective \(p\), authority or capability token \(a\), history reference \(h\), provenance \(\pi\), and logical time \(\tau\).

The record is a **candidate interface**, not a universal wire format. Implementations may add confidentiality labels, validity periods, idempotency keys, uncertainty intervals, resource budgets, and schema versions.

### 4.1 Relay kinds

| Kind | Typical content | Main contract concern |
|---|---|---|
| Context relay | Task constraints and relevant history | Completeness, freshness, privacy |
| Evidence relay | Measurements, tests, counterexamples | Provenance, uncertainty, integrity |
| Decision relay | Recommendation or chosen action | Authority, perspective, accountability |
| Execution relay | Tool call or delegated work | Side effects, budgets, permissions |
| Learning relay | Experience or proposed update | Validation, versioning, rollback |
| Structural relay | Portable unit or workflow revision | Interface compatibility, safety invariants |

**Repeated execution can itself be a relay of accumulated data**, but only if the resulting evidence is recorded with sufficient context to support legitimate reuse; repetition alone does not establish generalizable learning.

## 5. Contract Model

For unit \(U\), propose the contract

\[
C_U=(\Sigma_I,\Sigma_O,A,G,S,L,R,V,\Pi),
\]

where \(\Sigma_I,\Sigma_O\) are input/output schemas, \(A\) environmental assumptions, \(G\) guarantees, \(S\) safety invariants, \(L\) liveness or progress obligations, \(R\) resource and latency bounds, \(V\) validity conditions (context, perspective, version, time horizon), and \(\Pi\) provenance and audit obligations.

A contract should specify **what may be relied upon**, not simply describe how a unit is implemented.

### 5.1 Satisfaction

Let \(\operatorname{Traces}(U\mid A,V)\) denote the unit's observable traces under admissible assumptions and validity conditions. A simple trace-level contract satisfaction relation is:

\[
U\models C_U
\iff
\forall\rho\in\operatorname{Traces}(U\mid A,V):
\rho\models G\land S\land L\land R\land\Pi.
\]

This is a schematic definition. For probabilistic or unbounded systems, the quantifiers and interpretation of latency, liveness, and evidence must be refined. Statistical evidence cannot silently substitute for universal proof.

### 5.2 Perspective sovereignty

A receiving unit must not infer that an upstream score is comparable to its own score without a declared mapping. A score may be passed as evidence, but the receiving subject or governance plane retains its explicitly assigned authority to evaluate and act.

## 6. Relay Composition Operator

For compatible output and input types, write

\[
U_1\;\mathbin{\triangleright_R}\;U_2
\]

for a directed relay from \(U_1\) to \(U_2\) through relay adapter \(R\). The adapter may validate types, redact fields, map perspectives, enforce permissions, and record provenance.

A composed system is a graph

\[
\mathcal N=(\{U_i\}_{i\in N},\{R_{ij}\}_{(i,j)\in E},C_{\mathcal N}),
\]

with a system contract \(C_{\mathcal N}\) defined over **externally observable network traces**, not merely the conjunction of node contracts.

### 6.1 Compatibility is multidimensional

- **Type compatibility:** outputs can be parsed as inputs.
- **Semantic compatibility:** fields have compatible meanings and units.
- **Perspective compatibility:** score interpretation and optimization objectives are explicit.
- **Authority compatibility:** delegated actions remain within authorized scope.
- **Temporal compatibility:** freshness, ordering, and deadlines are respected.
- **Evolution compatibility:** versions and allowed updates remain interoperable.
- **Evidence compatibility:** downstream claims retain sufficient provenance.

Passing a JSON schema check establishes only a fraction of these obligations.

## 7. Candidate Assume–Guarantee Composition Rule

For a sequential pair \(U_1\triangleright_R U_2\), a sufficient-condition research template is:

1. \(U_1\models C_1\) and \(U_2\models C_2\) under their declared environments.
2. The adapter \(R\) preserves required types, semantics, authority, and evidence.
3. The guaranteed outputs of \(U_1\), after adaptation, satisfy the assumptions of \(U_2\).
4. Shared resources, interference, and temporal constraints are accounted for.
5. The desired network property is derivable from these obligations.

Then a **particular** system guarantee \(G_{12}\) may follow:

\[
\bigl(U_1\models C_1\bigr)\land
\bigl(U_2\models C_2\bigr)\land
\operatorname{Compat}(C_1,R,C_2)
\land\operatorname{SideConditions}
\Rightarrow
(U_1\triangleright_R U_2)\models G_{12}.
\]

**Research status:** This is a proof-obligation schema, not a theorem. The necessary side conditions depend on the operational semantics, concurrency model, fairness assumptions, and guarantee language.

## 8. Is Composition Associative?

A tempting claim is

\[
(U_1\triangleright U_2)\triangleright U_3
\equiv
U_1\triangleright(U_2\triangleright U_3).
\]

This may hold for a carefully defined abstract message-passing semantics with compatible adapters and no hidden side effects. It can fail operationally if grouping changes batching, retry logic, scheduling, privacy filtering, scoring normalization, or resource allocation.

**Open problem C1:** Identify the weakest useful assumptions under which Relay composition is associative up to a chosen observational equivalence.

**Counterexample target:** Three units share a rate-limited tool. Grouping changes the order of retries, causing a deadline miss in one grouping but not the other.

## 9. Contract Refinement and Substitution

Write \(C'\preceq C\) when a replacement contract is a valid refinement of the original under a defined refinement order. Informally, a replacement should not require stronger environmental assumptions or promise weaker externally relevant guarantees.

The familiar intuition is:

\[
A_C\Rightarrow A_{C'},\qquad
G_{C'}\Rightarrow G_C,
\]

with all implications interpreted over compatible trace domains and with temporal, authority, and provenance constraints included. These formulas are **not sufficient by themselves** for arbitrary evolving systems.

**Open problem C2:** Determine conditions for contextual substitutability:

\[
U'\preceq_{C,V}U
\Longrightarrow
\mathcal N[U']\models C_{\mathcal N}
\quad\text{whenever}\quad
\mathcal N[U]\models C_{\mathcal N}.
\]

Here \(\mathcal N[\cdot]\) is a network context with one designated replaceable position. This implication is a conjectured target requiring an explicit semantics and proof.

## 10. Dynamic Contracts Under Learning and RSI

A unit that learns can satisfy a contract at time \(t\) and violate it at \(t+1\). Therefore, static interface compatibility cannot certify unrestricted self-modification.

Propose a governed update transaction:

1. **Propose:** produce a candidate update and versioned artifact.
2. **Localize:** identify affected contracts, perspectives, and relay edges.
3. **Evaluate:** run tests, differential analysis, and counter-evidence checks.
4. **Sandbox:** exercise adversarial and distribution-shift scenarios.
5. **Approve:** apply an explicitly authorized release policy.
6. **Deploy:** use staged rollout and telemetry.
7. **Rollback or revise:** revoke the update if validity conditions fail.

A possible temporal invariant is:

\[
\Box\bigl(\operatorname{Active}(U,v)
\Rightarrow
\operatorname{Approved}(v,C,V)\bigr),
\]

where \(\Box\) means “always” in the selected temporal logic. Approval is an operational condition, not proof that every future trace is safe.

RSI and UIERU can meet here: RSI proposes and explores improvements; UIERU-like contracts and control planes evaluate and govern which changes may enter a live Relay network. Conversely, RSI methods may accelerate structural search within a governed UIERU ecosystem.

## 11. Perspective-Aware Contract Composition

Suppose \(U_A\) scores candidates by cost and \(U_B\) scores by safety. A naïve relay that forwards only a scalar score loses essential meaning. Define a score envelope:

```yaml
score:
  value: 0.87
  metric: task_success_estimate
  perspective: quality_first
  scale: [0.0, 1.0]
  calibration_dataset: synthetic_eval_v3
  uncertainty: {method: bootstrap, interval_95: [0.81, 0.92]}
  valid_context: {task_family: document_extraction}
  evidence_ref: evidence://run-042
  evaluator_version: eval-2.1
```

*All values above are illustrative, not empirical results.*

**Open problem C3:** Define when a perspective mapping \(f:P_A\to P_B\) preserves a decision or contract property, and when it merely transfers a nonbinding observation.

## 12. Provenance and Counter-Evidence Across Relays

Relay provenance should make it possible to answer:

- Which source produced a claim?
- Which transformation or masking operation changed it?
- Which evaluator and perspective were used?
- Which model, contract, and data versions were active?
- What contrary observations or failed tests were known?
- Who or what had authority to make the final decision?

A provenance chain should be tamper-evident where needed, but cryptographic integrity alone does not guarantee factual correctness. Counter-evidence must be first-class: a failed downstream result may trigger re-evaluation of upstream assumptions, not merely a local retry.

This is **Two-Way CCC** in a compositional setting: contracts and evidence flow forward, while discrepancies and counter-evidence flow backward to the relevant units and governance planes.

## 13. Failure Modes and Constructive Counterexamples

### F1 — Individually safe, jointly unsafe

Two agents each stay within a local resource budget but together exceed a shared global budget. Local resource guarantees do not compose without a shared allocation invariant.

### F2 — Schema-compatible, semantically incompatible

A sender reports latency in milliseconds; a receiver interprets the number as seconds. Structural type checks pass, but the decision is invalid.

### F3 — Score-scale confusion

A unit interprets a confidence-like score as a calibrated probability, causing unsafe thresholding.

### F4 — Hidden history dependency

Two units match on a finite replay dataset but diverge after repeated interactions because their internal learning states differ.

### F5 — Cyclic relay amplification

Two agents repeatedly reinforce each other's unsupported claims, increasing apparent confidence without independent evidence.

### F6 — Contract drift after update

A model upgrade improves average quality while violating a minority-language safety requirement that was part of the original contract.

### F7 — Non-idempotent retry

A timeout causes a delegated purchase action to be executed twice; each unit's local retry policy appears reasonable.

### F8 — Privacy-preserving mask breaks downstream proof

Redacting a sensitive field protects privacy but removes the evidence necessary to establish an authorization property. The system must either alter the proof method or decline the operation.

These counterexamples are **designed scenarios**, not reports of measured incidents.

## 14. Worked Synthetic Example: Three-Unit Research Relay

Consider a research workflow:

\[
U_{\text{retrieval}}
\triangleright
U_{\text{analysis}}
\triangleright
U_{\text{review}}.
\]

- Retrieval must attach source identifiers, timestamps, and access permissions.
- Analysis may synthesize hypotheses but must preserve attribution and uncertainty.
- Review checks factual support, counter-evidence, and release policy.

### 14.1 Initial contracts

| Unit | Assumption | Guarantee | Critical risk |
|---|---|---|---|
| Retrieval | Accessible corpus and query | Source-linked records | Stale or unauthorized evidence |
| Analysis | Valid source records | Claims with evidence pointers | Unsupported inference |
| Review | Traceable claims and policy | Approve, revise, or reject | Missing counter-evidence |

### 14.2 Substitution experiment

Replace the analysis unit with a faster candidate. It may be functionally equivalent on ordinary queries yet omit source pointers on long inputs. If the reviewer requires complete provenance, the replacement is **not** contract-refining, even if its answer quality is higher on a benchmark.

### 14.3 Example test matrix

| Test | Perspective | Expected property | Potential failure |
|---|---|---|---|
| T1 | Quality | Claim supported by source | Fabricated attribution |
| T2 | Speed | Deadline satisfied | Retry delay |
| T3 | Auditability | Complete provenance chain | Missing evidence pointer |
| T4 | Privacy | Unauthorized content excluded | Leakage through summary |
| T5 | Evolution | Approved version active | Silent model drift |
| T6 | Adversarial | Contradiction triggers review | Confidence amplification |

No numeric performance result is asserted by this example.

## 15. Perspective Differential Trees for Relay Diagnosis

A Perspective Differential Tree (PDT) can localize composition failures at several levels:

```text
Network Contract Difference
├── Interface Difference
│   ├── Schema / Type
│   └── Semantic Units
├── Perspective Difference
│   ├── Scoring Definition
│   └── Authority Mapping
├── Behavioral Difference
│   ├── Decision
│   └── Trajectory
├── Temporal Difference
│   ├── Ordering / Retry
│   └── Deadline / Freshness
├── Evolution Difference
│   ├── Model Version
│   └── Learning State
└── Evidence Difference
    ├── Provenance Gap
    └── Counter-Evidence Gap
```

PDT branches should be populated from observed or experimentally induced differences, with provenance and uncertainty. A branch name alone is not evidence of a causal mechanism.

## 16. Perspective-Aware Structural Queries

A minimal audit schema might include:

```sql
CREATE TABLE relay_event (
  event_id TEXT PRIMARY KEY,
  source_unit TEXT NOT NULL,
  target_unit TEXT NOT NULL,
  event_kind TEXT NOT NULL,
  perspective_id TEXT,
  contract_version TEXT NOT NULL,
  evidence_ref TEXT,
  event_time TIMESTAMP NOT NULL
);

CREATE TABLE contract_check (
  check_id TEXT PRIMARY KEY,
  event_id TEXT NOT NULL,
  obligation_id TEXT NOT NULL,
  status TEXT NOT NULL,
  observed_version TEXT NOT NULL,
  FOREIGN KEY (event_id) REFERENCES relay_event(event_id)
);
```

A query for recorded violations across relay edges:

```sql
SELECT e.source_unit, e.target_unit, e.perspective_id,
       c.obligation_id, COUNT(*) AS failed_checks
FROM relay_event AS e
JOIN contract_check AS c ON c.event_id = e.event_id
WHERE c.status = 'failed'
GROUP BY e.source_unit, e.target_unit,
         e.perspective_id, c.obligation_id
ORDER BY failed_checks DESC;
```

This detects recorded failures only; it does not prove that unobserved failures are absent. Future PASQ work should support time-bounded validity, causal lineage, counter-evidence links, and contract-version comparisons.

## 17. Open Formal Research Problems

**C1 — Associativity and observational congruence.** Determine a composition semantics and equivalence notion under which reassociation is sound.

**C2 — Contextual refinement.** Characterize sufficient and, where possible, necessary conditions for substituting a dynamic unit inside an arbitrary compatible network context.

**C3 — Perspective-preserving mappings.** Identify when cross-perspective score mappings preserve ordering, choice, or safety constraints.

**C4 — Cyclic composition.** Develop assume–guarantee rules for feedback loops without circular justification or unsupported evidence amplification.

**C5 — Probabilistic contracts.** Determine how local confidence bounds compose under correlated failures and shared data.

**C6 — Learning-stable guarantees.** Define update constraints under which contracts remain valid throughout bounded structural evolution.

**C7 — Provenance-preserving transformations.** Formalize the minimum evidence that must survive masking, aggregation, and relay to support downstream claims.

**C8 — Decentralized authority.** Model how subject-specific scoring sovereignty and global safety invariants coexist.

**C9 — Contract synthesis.** Infer candidate interface obligations from observed traces without confusing statistical fit with universal guarantees.

**C10 — Minimal counterexamples.** Automatically generate compact traces that explain failed network properties and identify responsible assumptions.

## 18. Testable Hypotheses

Each hypothesis requires explicit baselines, task distributions, confidence intervals, and preregistered outcome measures before empirical claims are made.

| ID | Hypothesis | Suggested test | Falsifying result |
|---|---|---|---|
| H1 | Typed semantic contracts reduce integration failures relative to schema-only checks | Paired integration tasks | No reproducible reduction |
| H2 | Provenance-preserving relay improves failure localization | Inject source/evaluator faults | No localization benefit |
| H3 | Contextual refinement predicts safe replacement better than output agreement alone | Controlled unit substitutions | No predictive improvement |
| H4 | Perspective metadata reduces score-misinterpretation errors | Cross-evaluator decision tasks | Error rate unchanged |
| H5 | Update gates reduce post-evolution contract violations | Simulated RSI update cycles | No reduction under matched cost |
| H6 | Counter-evidence backpropagation reduces repeated failures | Cyclic multi-agent workflow | Failures persist or worsen |

Measurement should include cost, latency, false rejection of valid updates, and governance overhead; a mechanism that prevents all change by rejecting everything is not successful intelligent evolution.

## 19. Validation Roadmap

### Phase 0 — Semantics and contract language

Specify message delivery, concurrency, failures, perspective mappings, observables, and admissible updates. Select a trace or temporal-logic semantics.

### Phase 1 — Finite-state reference models

Build small deterministic and stochastic units. Model-check safety, liveness, and substitution properties; deliberately generate counterexamples.

### Phase 2 — Composition and differential testing

Test chains, fan-out/fan-in graphs, and cycles. Compare schema-only, semantic-contract, and provenance-aware baselines.

### Phase 3 — Hybrid LLM/UIERU experiments

Connect LLM agents, retrieval, evaluators, and deterministic control components. Test hidden-history effects, evaluator disagreement, and RSI-generated updates under controlled conditions.

### Phase 4 — Adversarial sandbox

Inject malformed context, stale evidence, score-scale mismatches, correlated errors, unauthorized actions, and version drift. Evaluate Two-Way CCC diagnosis.

### Phase 5 — Governed pilot deployment

Use staged release, explicit authority, audit trails, rollback criteria, and documented validity limits. Publish negative results and revised contracts.

**Release criterion:** A claim should be labeled as *proved*, *model-checked under bounds*, *empirically supported*, *illustrated*, or *open*. These statuses are not interchangeable.

## 20. Research Relay Contract

The following machine-readable sketch is intended to help independent researchers pick up this problem without adopting the full SI vocabulary.

```yaml
research_relay_piece:
  id: RELAY-003
  title: Relay Composition and Contracts
  version: 1.0.0
  authors:
    - Sizhe Tan
    - GPT-Obot
  status: open-research
  core_question: >
    Under what conditions do local dynamic-unit contracts
    imply network-level guarantees after composition,
    substitution, and governed evolution?
  candidate_models:
    - labeled_transition_systems
    - assume_guarantee_contracts
    - probabilistic_temporal_models
    - provenance_annotated_event_graphs
  primary_obligations:
    - type_and_semantic_compatibility
    - perspective_and_authority_mapping
    - safety_liveness_resource_preservation
    - version_and_evolution_validity
    - evidence_and_counter_evidence_lineage
  counterexamples:
    - shared_resource_conflict
    - semantic_unit_mismatch
    - correlated_failure
    - cyclic_evidence_amplification
    - non_idempotent_retry
    - learning_induced_contract_drift
  validation:
    - formal_proof_or_countermodel
    - bounded_model_checking
    - differential_replay
    - adversarial_sandbox
    - controlled_hybrid_agent_experiment
  interfaces:
    depends_on:
      - RELAY-001-Perspective-Masking-Algebra
      - RELAY-002-Dynamic-Behavioral-Equivalence
    connects_to:
      - BUI-005-Dynamic-Equivalence-Relay-Composition-and-Emergent-Relations
      - CASE-002-Dynamic-Equivalence-and-Relay-Substitution
      - SPEC-004-Research-Relay-Piece-Contract
  contribution_policy:
    require_assumptions: true
    require_provenance: true
    welcome_counterexamples: true
    distinguish_proof_from_experiment: true
```

## 21. Collaboration and Contribution Pathways

- **Formal methods researchers:** define operational semantics, congruence, refinement, and compositional proof rules.
- **Distributed systems researchers:** analyze retries, partial failure, consistency, causal ordering, and shared-resource invariants.
- **Database and provenance researchers:** design queryable evidence lineage and integrity-preserving relay transformations.
- **Control and dynamical systems researchers:** study feedback stability and time-varying contracts.
- **LLM/RSI researchers:** test whether explicit contracts improve iterative agent modification without suppressing useful improvement.
- **SI engineers:** implement portable contracts, PDT localization, PASQ audits, and sandbox conformance tests.

Contributions should include assumptions, implementation or proof artifacts where available, evaluation conditions, known limitations, and counter-evidence. Distinct results and authorship should be attributed to their actual contributors; this relay piece does not assert priority over established contract or compositional-verification research.

## 22. Research Boundaries and Responsible Interpretation

The contract model is an **architectural proposal**. It does not prove that a particular LLM is interpretable, that all Relay networks are safe, or that an evolving system remains within contract forever. Structural transparency can expose routing, scoring interfaces, and governance decisions while leaving per-node model internals opaque.

The research program should avoid three common category errors:

1. Treating successful finite tests as universal correctness.
2. Treating syntactic interoperability as semantic or authority compatibility.
3. Treating a local equivalence claim as unrestricted network substitutability.

These boundaries are necessary for credible Open Research Relay.

## 23. Conclusion

Relay is more than message passing. In a dynamic structural intelligence ecosystem, Relay transfers work, evidence, context, authority, and sometimes the conditions for future learning. The central research challenge is to determine when such transfers preserve the contracts on which a larger system depends.

**RELAY-003 proposes a research interface, not a completed theory:** typed dynamic-unit contracts, perspective-aware relay events, explicit proof obligations, counterexample families, and a validation path from finite models to governed hybrid systems. Its success should be judged by whether other researchers can prove, falsify, refine, and reuse its claims—not by the elegance of its vocabulary alone.

The next adjacent research relay is **RELAY-004 — Biological Dynamic Intelligence**, which explores dynamic organization and context-dependent functional coordination while maintaining a strict distinction between computational analogy and biological evidence.

---

## References and Related Foundations

The following established research traditions offer useful points of comparison. They do not imply that the present UIERU proposal is already derived from or validated by those results.

1. Hoare, C. A. R. (1985). *Communicating Sequential Processes*. Prentice Hall.
2. Milner, R. (1989). *Communication and Concurrency*. Prentice Hall.
3. Lamport, L. (1978). Time, clocks, and the ordering of events in a distributed system. *Communications of the ACM*, 21(7), 558–565.
4. Abadi, M., & Lamport, L. (1995). Conjoining specifications. *ACM Transactions on Programming Languages and Systems*, 17(3), 507–535.
5. Alur, R., & Henzinger, T. A. (1999). Reactive modules. *Formal Methods in System Design*, 15, 7–48.
6. Benveniste, A., Caillaud, B., Nickovic, D., Passerone, R., Raclet, J.-B., Reinkemeier, P., Sangiovanni-Vincentelli, A., Damm, W., Henzinger, T. A., & Larsen, K. G. (2018). Contracts for system design. *Foundations and Trends in Electronic Design Automation*, 12(2–3), 124–400.
7. Clarke, E. M., Grumberg, O., & Peled, D. A. (1999). *Model Checking*. MIT Press.
8. W3C PROV Working Group (2013). *PROV-O: The PROV Ontology*. W3C Recommendation.

### Repository Placement

`research-relay/RELAY-003-Relay-Composition-and-Contracts.md`

### Citation

Sizhe Tan & GPT-Obot (2026). *RELAY-003: Relay Composition and Contracts*. In *Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay*, v1.0.0. Research agenda and proposed formalization.

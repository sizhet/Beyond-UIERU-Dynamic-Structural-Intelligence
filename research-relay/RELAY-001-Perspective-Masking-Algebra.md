# RELAY-001 — Perspective Masking Algebra

**Project:** Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay (BUI-DSI)  
**Version:** 1.0.0 — Open Research Problem  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Proposal; definitions, hypotheses, and illustrative counterexamples are not established properties of biological or deployed AI systems.

## Abstract

Perspective masking is proposed as a disciplined way to observe, compare, and sometimes intervene in dynamic intelligence units without claiming to expose their entire internal computation. This research relay piece asks whether families of masking operators admit useful algebraic laws, when those laws fail, and which observable properties survive masking. It distinguishes passive projection from intervention and counterfactual reconstruction; defines minimal mathematical objects and candidate propositions; supplies counterexamples, validation tasks, and interfaces to differential localization, SQL, relay composition, RSI, and computational neuroscience. The objective is to make a tractable, falsifiable mathematical problem available to independent researchers—not to announce a completed algebra.

## 1. Research motivation and lineage

BUI-DSI extends SI research from relatively stable structural descriptions (MDT, CCC, UTN, SIF localization) to evolving UIERU-like units with perspectives, scoring, action, history, and relay. The first engineering opportunity is to mask irrelevant variation and recover comparable views. But masking a recorded trace and disabling a scoring component during execution are mathematically different operations. An algebra that conflates them would give unreliable comparison and substitution claims.

This piece complements `docs/BUI-002-Perspective-Masking-and-Dynamic-Structural-Observation.md`, `docs/BUI-003-Perspective-Differential-Trees-and-Dynamic-Localization.md`, and `docs/BUI-006-Mathematical-Foundations-and-Open-Formal-Problems.md`.

## 2. Problem statement

**Primary question:** For which classes of dynamic intelligence systems and masking semantics do masking operators satisfy composition, commutativity, idempotence, refinement, and property-preservation laws?

**Secondary questions:**

1. Which laws hold for observation-only projections but fail for execution interventions?
2. How can provenance and omitted evidence be represented so that masking is auditable?
3. When does a masked observation support valid cross-perspective comparison?
4. Can masking operations be compiled into relational queries without changing their meaning?
5. Which guarantees survive relay composition or online structural evolution?

## 3. Minimal formal model

Let a dynamic intelligence unit be represented by a labeled, possibly stochastic transition system

\[
\mathcal U=(S,A,O,P,C,\Theta,K,G,s_0),
\]

where `S` is the state space, `A` actions, `O` observations, `P` perspectives, `C` contexts, `Θ` structural configurations, `K(s',o\mid s,a,p,c,\theta)` a transition/observation kernel, `G` an optional structure-update rule, and `s₀` an initial-state distribution or state. A finite execution trace is

\[
\tau=(s_0,p_0,c_0,a_0,o_1,s_1,\ldots,s_T).
\]

A **recorded evidence object** is `e=(τ, metadata, provenance, missingness)`; metadata may include time, version, evaluator, scoring scale, and relay dependencies. An **observation mask** `M_m : E → V_m` produces a typed view from recorded evidence. A **system intervention** `I_m : U → U_m` changes operational semantics; a **counterfactual reconstruction** `R_m(e, model)` estimates unobserved outcomes under explicit assumptions. These three maps must not share a single unqualified equality sign.

### 3.1 Typed masks

A mask specification may constrain `structure`, `perspective`, `scoring`, `context`, `time`, `evolution`, `interaction`, and `evidence`. Each field must state whether it filters fields, conditions a query, freezes a variable, or actively changes execution. The output includes an observation contract identifying which quantities remain visible and which are suppressed.

### 3.2 Comparison contract

A cross-mask comparison requires at minimum: task definition, context support, candidate-action set, scoring units and calibration, initial state or matching procedure, time horizon, intervention status, structural version, and provenance. Without these, numerical deltas are descriptive at best, not evidence of a causal perspective effect.

## 4. Candidate algebra for passive observation

Fix an immutable evidence universe `E` with a common schema. For a set of retained fields `F`, let `π_F(e)` be the projection retaining only fields in `F`. With compatible schemas and ordinary projection semantics:

\[
\pi_F(\pi_G(e))=\pi_{F\cap G}(e), \qquad
\pi_F\circ\pi_G=\pi_G\circ\pi_F, \qquad
\pi_F^2=\pi_F.
\]

These identities are valid **only under the stated projection interpretation** (including compatible handling of identifiers and metadata). They are not claims about arbitrary perspective masking.

### 4.1 Refinement order

Define `F ≼ G` if `F ⊆ G`, meaning `G` retains at least as much information. This forms a field-set lattice under union and intersection. A research task is to identify whether a useful analogous partial order exists for typed masks involving temporal aggregation, anonymization, missingness, or perspective conditioning.

### 4.2 Provenance-aware masking

A provenance-preserving view can be represented as `(π_F(e), m, source_id, omitted_fields, derivation)`. Projection of visible data may be idempotent, while provenance metadata grows as operations are chained. Consequently, equality may need to be defined up to normalized provenance, rather than literal byte-for-byte equality.

## 5. Why intervention algebra is harder

Let `I_p` suppress a scoring branch and renormalize remaining weights. Let `I_q` change the candidate-action set. The order may change the selected action:

\[
I_p(I_q(\mathcal U))\ne I_q(I_p(\mathcal U)).
\]

Likewise, freezing learning before a decision may differ from freezing it after feedback. Interventions alter the transition kernel, potentially creating histories that never occurred in the original system. A mask that is passive for a database query may be active for a live agent. Every algebraic claim must therefore specify its semantic domain.

## 6. Worked counterexamples

**CE-001 — Noncommuting intervention.** A decision system has candidates A and B. An intervention first removes A and recalibrates scores; a second intervention suppresses the recalibration branch. Reversing their order can select a different candidate. Record the complete scores and update order to make the example reproducible.

**CE-002 — Hidden confounding.** Two perspectives appear to cause different decisions, but their recorded contexts differ in threat level. Perspective-only filtering produces a misleading differential. Matched-context replay may eliminate it.

**CE-003 — Information-loss paradox.** Two units are identical under a mask that hides rare failures but are not substitutable under a safety contract that includes those failures.

**CE-004 — Temporal aggregation.** Averages over a long window erase a short-lived unstable transition; time aggregation and event filtering need not commute.

**CE-005 — Evolving schema.** A structural update introduces a new scoring branch. A mask compiled against the old schema silently drops that branch unless version constraints are enforced.

These are conceptual counterexample templates, not reported empirical findings.

## 7. Candidate research propositions

**P1 (projection subalgebra).** For immutable, schema-compatible evidence and pure field projections, masks form a commutative idempotent algebra isomorphic to intersection on retained-field sets. *Status:* follows from the definitions; formalize edge cases for typed evidence.

**P2 (query preservation).** A query `Q` can be evaluated after masking without semantic loss if all fields and provenance required by `Q` remain available and the query semantics commute with the chosen projection. *Status:* conditional claim requiring a precise query language and equivalence criterion.

**P3 (decision preservation).** An observation mask preserves a decision property when the property is measurable solely from retained evidence and does not depend on suppressed causal inputs. *Status:* research hypothesis; counterexamples expected for causal and temporal properties.

**P4 (relay compositionality).** Locally valid masking contracts suffice for global composition only with explicit assumptions about shared state, interface compatibility, interference, and observation boundaries. *Status:* open problem; a general unconditional theorem is not expected.

**P5 (evolution robustness).** Mask semantics remain comparable across unit versions if schema migrations and state transitions preserve a declared observation contract. *Status:* open; requires migration invariants and versioned validation.

## 8. Mathematical connections and prior-art search agenda

Relevant starting points include relational algebra and database provenance; abstract interpretation and Galois connections; program slicing and information-flow noninterference; labeled transition systems and bisimulation; causal interventions and structural causal models; temporal logic and model checking; and assume-guarantee reasoning. These are **research connections**, not novelty claims. A literature review should identify exact existing theorems before asserting any new algebra.

## 9. Research tasks for external contributors

- **MAT-01:** Define a typed mask calculus separating projection, conditioning, intervention, and counterfactual reconstruction.
- **MAT-02:** Prove or refute closure, commutativity, idempotence, and refinement laws for each mask class.
- **MAT-03:** Specify a provenance-preserving equivalence relation between masked views.
- **MAT-04:** Characterize which temporal and decision properties are invariant under each mask.
- **DB-01:** Give sound SQL/relational translations for a restricted passive-mask language.
- **MET-01:** Implement differential localization with explicit comparability contracts and negative tests.
- **RSI-01:** Test whether evolving LLM-agent evaluator configurations can be inspected using these masks without treating hidden model internals as transparent.
- **BIO-01:** Distinguish observational neural recordings from interventions in a task-switching model; avoid inferring neural architecture from functional analogy alone.

## 10. Validation protocol

**Stage A — Formal core.** Publish precise syntax, typing rules, denotational or operational semantics, and proofs for the restricted passive projection case.

**Stage B — Synthetic counterexamples.** Construct small deterministic and stochastic agents where proposed laws hold or fail. Include order-sensitive scoring, hidden context, schema updates, and rare-event safety cases.

**Stage C — Query equivalence.** Compare direct masked-trace evaluation with compiled SQL under identical datasets; report mismatches, missing fields, and provenance behavior.

**Stage D — Dynamic experiments.** Run matched-seed, matched-context comparisons of UIERU-like units across perspectives; separate observational association from intervention effects.

**Stage E — Relay stress test.** Compose units with shared state and conflicting constraints, then test whether local guarantees survive. Retain failures as first-class research results.

Suggested metrics: property-violation count, query-equivalence rate, provenance completeness, false-equivalence rate, decision preservation, and sensitivity to structural version changes. Metrics are proposed, not benchmark results.

## 11. Research relay contract

```yaml
relay_piece_id: BUI-DSI-RELAY-001
version: 1.0.0
status: open-research-problem
problem: Perspective Masking Algebra
model: typed dynamic transition system plus immutable evidence views
hypotheses:
  - passive projection algebra under explicit schema assumptions
  - conditional query and property preservation
counter_evidence:
  - order-sensitive interventions
  - hidden context
  - temporal aggregation
  - schema evolution
validation:
  - formal proofs and countermodels
  - reproducible synthetic traces
  - query equivalence tests
interfaces:
  - BUI-002
  - BUI-003
  - BUI-004
  - BUI-006
  - RELAY-002
  - RELAY-003
provenance_required: true
```

## 12. Contribution and governance rules

Contributors should label results as **proved**, **empirically supported**, **counterexample**, **conjecture**, or **open**. Submit minimal assumptions, definitions, reproducible examples, and versioned evidence. Negative results and stronger alternative formulations are welcome. A proposed law should not be promoted to a general UIERU guarantee without checking its semantics under execution, evolution, and relay composition.

## 13. Relationship to other BUI-DSI pieces

- `RELAY-002-Dynamic-Behavioral-Equivalence.md`: masking may hide behaviors needed for an equivalence or substitution claim.
- `RELAY-003-Relay-Composition-and-Contracts.md`: compositional masking requires interface and interference assumptions.
- `RELAY-004-Biological-Dynamic-Intelligence.md`: biological recording, perturbation, and counterfactual inference require distinct semantics.
- `RELAY-005-Open-Structural-Evolution.md`: masks must survive or explicitly fail across structural revisions.
- Proposed `RELAY-006-RSI-UIERU-Convergence.md`: evaluator and workflow masking for evolving LLM-agent systems.

## 14. Open questions

1. What is the smallest useful mask language that supports both structural and temporal observations?
2. Can a refinement order quantify information loss without assuming a fixed schema?
3. Which mask laws survive stochastic execution and policy updates?
4. How can a differential tree expose confounding rather than conceal it?
5. Can mask contracts become reusable components of SIF localization and PASQ query planning?
6. How should counter-evidence invalidate or narrow an earlier mask-based equivalence claim?

## 15. Scope and limitations

This document introduces a proposed research program, not an established mathematical theory or a validated implementation. Its projection identities apply to a deliberately restricted model. Real systems may have partially observed states, nonstationarity, evaluator drift, causal interference, and non-replayable actions. Claims about biological intelligence are functional research analogies, not anatomical identifications.

## 16. Suggested foundational reading

The following are conceptual starting points; the precise applicability of each result requires independent review.

- Codd, E. F. (1970). *A Relational Model of Data for Large Shared Data Banks*. Communications of the ACM.
- Cousot, P., & Cousot, R. (1977). *Abstract Interpretation: A Unified Lattice Model for Static Analysis of Programs by Construction or Approximation of Fixpoints*. POPL.
- Pearl, J. (2009). *Causality: Models, Reasoning, and Inference* (2nd ed.). Cambridge University Press.
- Milner, R. (1989). *Communication and Concurrency*. Prentice Hall.
- Clarke, E. M., Grumberg, O., & Peled, D. A. (1999). *Model Checking*. MIT Press.

## 17. Closing research invitation

The central opportunity is to turn perspective masking from an informal engineering convenience into a collection of **typed, auditable, falsifiable operators**. A useful contribution may be a theorem, a failed conjecture, a better counterexample, a faithful SQL translation, or an experimental protocol that exposes an invalid comparison. Such contributions are independently valuable and can be relayed into the broader dynamic structural intelligence research program.

---

**Citation context:** BUI-DSI, v1.0.0, Research Relay Piece RELAY-001.  
**Authors:** Sizhe Tan & GPT-Obot.  
**License:** See repository `LICENSE` and release metadata.

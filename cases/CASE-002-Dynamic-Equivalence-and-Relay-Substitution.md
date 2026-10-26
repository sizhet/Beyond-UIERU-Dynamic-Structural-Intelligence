# CASE-002 — Dynamic Equivalence and Relay Substitution

**Project:** Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay (BUI-DSI)  
**Version:** 1.0.0 (research proposal and synthetic case study)  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Open research case; no empirical validation claimed  
**Related:** BUI-002, BUI-003, BUI-004, BUI-005, BUI-006, BUI-008; CASE-001

## Abstract

Two dynamic intelligence units may differ radically in their internal architectures yet appear interchangeable for a bounded task. This case investigates when that apparent equivalence justifies substituting one unit for another inside a relay composition. It distinguishes output agreement, conditional behavioral similarity, trace equivalence, contract compatibility, and evolution compatibility. A synthetic two-unit service workflow demonstrates that matching observed answers is insufficient: a replacement may violate latency, evidence provenance, escalation, or long-horizon learning requirements. We propose a comparison contract, a perspective-conditioned differential analysis, a staged substitution protocol, and counter-evidence tests. The purpose is to supply an independently reusable research problem rather than assert a general substitution theorem.

## 1. Research question and scope

**Primary question:** Under what explicit conditions can a UIERU-like dynamic unit be replaced by another without invalidating the requirements of the surrounding relay system?

We consider a service workflow in which a coordinator delegates document-based technical questions to an answer unit. The surrounding workflow requires not only an answer but also evidence references, uncertainty signaling, and an escalation decision. Both candidate units are hypothetical. All numbers and traces below are **synthetic illustrations**, not measured results.

The study deliberately separates three claims:

1. **Observed similarity:** two units agree on a finite set of test inputs.
2. **Bounded substitutability:** under a stated context, environment, and contract, a replacement passes defined acceptance criteria.
3. **General equivalence:** units are interchangeable across all admissible contexts and future evolution states.

Only the second claim is an achievable engineering target in this case; the third remains an open formal problem.

## 2. The relay workflow

```text
User request
    |
    v
Coordinator UIERU (U_C)
    |-- task/context/perspective contract --> Answer UIERU (U_A or U_B)
    |<-- answer/evidence/confidence/escalation --|
    v
Contract gate -> deliver, revise, or escalate
    |
    v
Evidence log and feedback / possible evolution
```

The coordinator is held fixed during a controlled substitution. The candidate answer units are:

- **U_A:** explicit retrieval, rule-based evidence checking, and a small scoring tree.
- **U_B:** an LLM-centered retrieval agent with a learned evaluator and tool calls.

These descriptions are illustrative architecture choices, not statements about real products. The units expose the same nominal API but may behave differently under failure, ambiguity, or repeated feedback.

## 3. Comparison contract

A substitution experiment must pin or record the following dimensions.

| Dimension | Contract field | Example condition |
|---|---|---|
| Task | `task_family` | Document-grounded technical Q&A |
| Perspective | `perspective_profile` | Accuracy-first or latency-first |
| Context | `context_scope` | Fixed corpus version and question class |
| Environment | `environment_snapshot` | Same tools, permissions, and availability |
| History | `initial_state_id` | Frozen memory and evaluator versions |
| Interface | `api_contract_version` | Identical request/response schema |
| Evidence | `provenance_policy` | Citations must resolve to permitted sources |
| Safety | `escalation_policy` | Abstain or escalate when support is inadequate |
| Budget | `resource_limits` | Maximum latency and tool-use allowance |
| Evolution | `update_policy` | Frozen for initial tests; governed updates later |

A successful comparison must state whether the perspective is merely observed, replayed, or actively intervened upon. Masking an evaluator during execution may alter the unit and must not be mislabeled as passive observation.

## 4. Formalization

Represent a dynamic unit by

$$
U=(X,A,Y,P,C,H,T,O,L,K),
$$

where \(X\) is its internal state space, \(A\) the admissible actions, \(Y\) the observable outputs, \(P\) perspectives, \(C\) contexts, \(H\) history, \(T\) the state transition rule, \(O\) the observation rule, \(L\) the learning/update rule, and \(K\) its externally declared contract. This is a **proposed abstraction**, not a canonical definition of UIERU.

Let \(\tau(U,z)\) denote an observable execution trace for test condition \(z=(p,c,e,h)\). A trace may contain outputs, tool calls, latency, citations, escalation decisions, and externally visible state changes.

For a bounded test domain \(D\), define an empirical discrepancy:

$$
\widehat d_D(U_A,U_B)=\sum_{z\in D}w_z\,d_\tau\bigl(\tau(U_A,z),\tau(U_B,z)\bigr),
$$

with nonnegative weights \(w_z\) summing to one and a trace discrepancy function \(d_\tau\) declared in advance. A small empirical discrepancy **does not prove** equivalence outside \(D\). Further, if \(d_\tau\) is not a metric, \(\widehat d_D\) should not be called a mathematical distance.

A practical bounded substitution judgment is:

$$
operatorname{SubOK}(U_B\mid U_A,R,D,K,\epsilon)
$$

meaning that, when \(U_B\) replaces \(U_A\) in relay environment \(R\), the specified contract checks pass over \(D\) within declared tolerances \(\epsilon\). This is a **test predicate**, not a universal theorem.

## 5. Levels of equivalence

| Level | Question | Why it is insufficient alone |
|---|---|---|
| Interface compatibility | Can both units accept and return the same schema? | Semantics may differ |
| Output agreement | Do final answers match? | Provenance and escalation may diverge |
| Decision equivalence | Do they choose similar actions? | Timing and downstream effects may diverge |
| Trace equivalence | Do observable interaction sequences match? | Untested contexts and histories remain |
| Contractual substitutability | Does the enclosing relay meet its obligations after replacement? | Holds only under stated assumptions |
| Evolution compatibility | Do governed updates preserve required behavior? | Future learning may introduce drift |

Approximate bisimulation, trace refinement, and assume-guarantee reasoning offer established theoretical starting points. Whether a useful extension applies to evolving UIERU-like systems remains to be demonstrated.

## 6. Synthetic test matrix

The following values are **invented for illustration** and are not benchmarks.

| Scenario | Perspective | U_A result | U_B result | Preliminary finding |
|---|---|---|---|---|
| S1: well-supported question | Accuracy | Correct, cited | Correct, cited | Output and evidence agreement |
| S2: ambiguous evidence | Accuracy | Abstains | Confident unsupported answer | Escalation violation by U_B |
| S3: routine question | Latency | 900 ms | 550 ms | U_B meets tighter latency target |
| S4: source unavailable | Accuracy | Escalates | Retries unapproved tool | Permission/relay violation |
| S5: repeated corrections | Learning | Remains frozen | Updates evaluator | Evolution-policy divergence |

S1 alone would suggest equivalence. S2–S5 reveal that an apparently interchangeable unit can violate important relay obligations. The lesson is not that one architecture is categorically superior; the lesson is that equivalence is perspective-, context-, contract-, and time-dependent.

## 7. Perspective-conditioned differential tree

```text
Common task + fixed coordinator + shared interface
|
+-- Accuracy perspective
|   +-- Answer agreement (S1)
|   +-- Evidence provenance divergence (S2)
|   +-- Escalation divergence (S2, S4)
|
+-- Latency perspective
|   +-- Response-time differential (S3)
|   +-- Tool-budget differential (to measure)
|
+-- Evolution perspective
    +-- State-update divergence (S5)
    +-- Future behavior drift (open test)
```

Each differential node should retain its comparison contract, data provenance, measurement method, and counter-evidence. The tree is an index of observed or hypothesized differences, **not** a complete causal explanation.

## 8. Relay composition and contract preservation

Let \(R[U]\) denote the enclosing coordinator workflow with answer unit \(U\). A local interface match does not imply:

$$
K(R[U_A])\Rightarrow K(R[U_B]).
$$

A valid replacement argument must include assumptions about input admissibility, tool permissions, timing, escalation, and downstream handling. For example, the coordinator may assume that `confidence=high` is issued only with resolvable evidence. A replacement violating this assumption can cause an incorrect final delivery even if its response schema is valid.

A useful verification approach is **assume-guarantee reasoning**: the coordinator declares assumptions \(A_C\), the candidate declares guarantees \(G_B\), and the integration tests whether \(G_B\) entails the relevant assumptions under the shared environment. The implication must be justified rather than presumed.

## 9. Substitution protocol

**Phase 0 — Declare the contract.** Specify the intended context domain, perspectives, hard constraints, tolerated deviations, and disallowed updates.

**Phase 1 — Static checks.** Validate schemas, name/type contracts, tool permissions, and provenance formats.

**Phase 2 — Paired replay.** Run both units against the same frozen task set and initial conditions; log complete traces. When determinism is unavailable, use repeated trials and uncertainty estimates.

**Phase 3 — Differential localization.** Index output, scoring, decision, trajectory, and learning differences; record confounders.

**Phase 4 — Adversarial sandbox.** Inject missing evidence, contradictory sources, timeouts, malformed tool results, and perspective shifts.

**Phase 5 — Shadow relay.** Route the replacement through the full coordinator while withholding consequential external actions; compare contract compliance.

**Phase 6 — Governed deployment.** If criteria pass, enable bounded use with monitoring, rollback, and revalidation triggers.

**Phase 7 — Evolution requalification.** Re-run targeted checks after evaluator, memory, tool, scoring, or contract changes.

## 10. Perspective-aware structural queries

The following SQL is **illustrative pseudocode** against a hypothetical event schema; it is not a runnable query without the corresponding tables and normalization rules.

```sql
SELECT scenario_id, perspective_id,
       MAX(CASE WHEN unit_id = 'U_A' THEN escalation END) AS a_escalation,
       MAX(CASE WHEN unit_id = 'U_B' THEN escalation END) AS b_escalation
FROM paired_trace_observations
WHERE comparison_contract_id = 'C-002'
GROUP BY scenario_id, perspective_id
HAVING MAX(CASE WHEN unit_id = 'U_A' THEN escalation END)
    IS DISTINCT FROM
       MAX(CASE WHEN unit_id = 'U_B' THEN escalation END);
```

A production PASQ layer should reject or flag comparisons with incompatible context snapshots, missing provenance, noncomparable scoring scales, or mismatched evolution policies.

## 11. Counter-evidence and failure modes

1. **Finite-test illusion:** agreement on a benchmark hides failures on rare contexts.
2. **Perspective leakage:** different scoring priorities are compared as though identical.
3. **History contamination:** one unit has prior memory or feedback unavailable to the other.
4. **Hidden relay dependencies:** downstream components depend on undocumented timing or metadata.
5. **Mask intervention bias:** disabling a scoring component changes the behavior under study.
6. **Evaluator Goodharting:** a candidate learns to pass tests without meeting real-world obligations.
7. **Nonstationary drift:** successful substitution becomes invalid after updates.
8. **Provenance laundering:** plausible citations are treated as verified evidence without resolution.

Each failure mode should be associated with a falsification test and a recordable remediation, not merely listed as a warning.

## 12. Testable hypotheses

- **H1 — Conditional substitution:** Under a sufficiently explicit comparison contract, bounded substitutability can be evaluated more reliably than with output-only agreement.
- **H2 — Differential index utility:** Perspective differential trees reduce the effort required to locate contract-relevant divergences compared with unstructured logs.
- **H3 — Relay sensitivity:** Some unit pairs with high output agreement still produce materially different enclosing-system outcomes.
- **H4 — Evolution requalification:** Revalidation triggered by meaningful state or evaluator changes detects failures missed by one-time acceptance tests.
- **H5 — Structural governance:** Explicit contracts and provenance improve auditability of an LLM-centered RSI candidate without implying full interpretability of its internal model.

These are hypotheses, not established findings. Validation requires declared baselines, representative workloads, independent failure annotation, and uncertainty reporting.

## 13. Minimal experimental design

Use a frozen document corpus with independently annotated questions, including supported, ambiguous, contradictory, and unsupported cases. Implement two heterogeneous answer units with a common response contract. Randomize trial order and repeat stochastic runs. Pre-register hard constraints (such as citation validity and escalation behavior) separately from soft metrics (such as latency). Compare:

- output-only substitution screening;
- contract-aware paired replay;
- contract-aware replay plus adversarial sandbox and differential indexing.

Measure missed violations, false rejection rates, investigation time, resource cost, and post-update drift. Report confidence intervals where appropriate. Do not use synthetic values from Section 6 as experimental evidence.

## 14. RSI–UIERU two-way relay

An LLM-agent RSI implementation may generate new prompts, tools, evaluators, or workflow variants. A UIERU-inspired structural layer can expose their contracts, score changes, provenance, and governed substitution tests. Conversely, RSI search can propose new candidate units or relay structures for evaluation. This is a potential **two-way research interface**, not evidence that all RSI systems instantiate UIERU or that UIERU automatically makes their internal computations interpretable.

## 15. Research relay handoff

**Problem:** Define useful conditions for bounded substitution of evolving heterogeneous intelligence units.

**Minimal model:** Two candidate units, one enclosing relay, a declared comparison contract, and observable traces.

**Open formal questions:** Which trace relations are preserved under relay composition? Can approximate behavioral relations support meaningful error bounds? What restrictions on learning updates permit re-use of earlier proofs?

**Evidence needed:** Paired execution logs, source-validity checks, adversarial cases, update history, and full contract provenance.

**Accepted contributions:** Formal proofs, counterexamples, revised comparison contracts, empirical evaluations, alternate distance measures, and negative results.

**Interfaces:** BUI-002 Masking; BUI-003 Differential Tree; BUI-004 PASQ; BUI-005 Dynamic Equivalence; BUI-006 Formal Problems; BUI-008 Open Research Relay; proposed SPEC-002 and SPEC-004.

## 16. Limitations

This document is a conceptual, synthetic case study. It provides no real-world benchmark, validated numerical estimate, general substitution guarantee, or neuroscience claim. The choice of observable trace fields is incomplete for some applications; security, privacy, economic incentives, and long-run multi-agent adaptation may require additional contracts. Formal equivalence and empirical acceptance must remain clearly distinguished.

## 17. Conclusion

Dynamic equivalence is not an intrinsic label attached to a unit. It is a claim about observable behavior under a specified perspective, context, environment, history, contract, and time horizon. Relay substitution therefore requires more than matching outputs: it requires checking the assumptions and obligations of the enclosing system, preserving counter-evidence, and requalifying changes after evolution. This case offers a portable research problem for mathematics, formal methods, agent engineering, and open structural intelligence research.

## References and research connections

The following are established conceptual starting points, **not** citations proving the proposed UIERU claims:

1. Milner, R. *Communication and Concurrency*. Prentice Hall, 1989. (Behavioral equivalence and process calculi.)
2. Larsen, K. G., and Skou, A. “Bisimulation through Probabilistic Testing.” *Information and Computation* 94(1), 1991, 1–28. https://doi.org/10.1016/0890-5401(91)90030-6
3. Alur, R., Henzinger, T. A., Kupferman, O., and Vardi, M. Y. “Alternating Refinement Relations.” *CONCUR 1998*. https://doi.org/10.1007/BFb0055622
4. de Alfaro, L., and Henzinger, T. A. “Interface Automata.” *ESEC/FSE 2001*. https://doi.org/10.1145/503209.503226
5. SIF, UIERU, and BUI-DSI project documents: research lineage and proposed structural terminology; consult their respective repository releases for versioned citations.

---

**Research status:** Open hypothesis and synthetic case.  
**Citation guidance:** Cite the eventual BUI-DSI DOI release and this file's version; do not assign an unissued DOI.  
**Open relay principle:** Reusable results include valid proofs, bounded successes, reproducible failures, and counterexamples.

# RELAY-005 — Open Structural Evolution

**Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay (BUI-DSI)**  
**Research Relay Piece · v1.0.0 · 2026-10-25**  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Open research agenda; proposed models and hypotheses, not established results  
**Suggested repository path:** `research-relay/RELAY-005-Open-Structural-Evolution.md`

## Abstract

An intelligence system that can execute a fixed repertoire is not necessarily capable of open structural evolution. This Research Relay Piece asks how a population of dynamic intelligence units can discover, evaluate, compose, replace, and retire capabilities while preserving accountable control over safety, evidence, and decision authority. Building on Universal Intelligence Evolution and Relay Units (UIERUs), perspective-aware scoring, dynamic behavioral equivalence, and contract-governed relay, we propose a falsifiable research program for **open structural evolution**. We distinguish parameter adaptation, policy revision, structural modification, ecosystem expansion, and changes to the space of discoverable problems. Candidate formalizations describe versioned unit graphs, typed evolutionary operators, evidence-bearing selection, and governance gates. We identify conditions under which local improvement fails to produce global improvement, and formulate tests for novelty, transfer, robustness, reversibility, and sustained growth. Connections to recursive self-improvement (RSI) are treated as opportunities for bidirectional research rather than assertions of architectural identity. The intended output is a portable research interface for mathematicians, computer scientists, AI engineers, and empirical researchers.

**Keywords:** structural intelligence; UIERU; open-ended evolution; recursive self-improvement; structural growth; compositionality; contracts; evaluator governance; counter-evidence; research relay.

---

## 1. Research Position and Scope

The central question is not whether an intelligence system can change. Many systems already update parameters, retrieve new information, or revise plans. The question is whether it can **reliably extend its own effective organization**: its available intelligence units, interfaces, relationships, evaluation criteria, and problem-solving pathways.

We distinguish three claims:

1. **Established engineering observation:** software systems can dynamically select tools, modify workflows, accumulate memories, and deploy updated components.
2. **Research hypothesis:** explicit UIERU-like structural interfaces may make some of these changes easier to localize, compare, verify, and govern.
3. **Open scientific problem:** whether such mechanisms support sustained, nontrivial, generalizable, and safe open-ended intelligence growth.

No theorem of indefinite improvement is asserted. No claim is made that UIERU is a necessary or sufficient architecture for general intelligence.

## 2. From Adaptation to Open Structural Evolution

A useful taxonomy prevents the word *evolution* from hiding distinct mechanisms.

| Level | Object changed | Illustrative operation | Key validation question |
|---|---|---|---|
| L0 — Execution | Runtime state | Repeat an action or relay a result | Was the execution correct? |
| L1 — Adaptation | Parameters or local memory | Update weights, cache evidence | Does behavior improve in scope? |
| L2 — Policy revision | Scoring or dispatch policy | Reweight cost versus accuracy | Is the revised policy robust? |
| L3 — Structural change | Units and edges | Add, replace, split, merge a UIERU | Are interfaces and contracts preserved? |
| L4 — Ecosystem expansion | Capability repertoire and interoperability | Import a new specialized unit or protocol | Does the new capability transfer? |
| L5 — Open research growth | Questions, representations, evaluation methods | Discover a new problem class or measurement | Is the novelty independently defensible? |

These levels are neither a universal maturity ranking nor a guaranteed progression. A system can excel at one level and fail at another.

### 2.1 Repeated execution as data relay

Repeated execution can relay experience into evidence stores, precedent registries, or learning pipelines. It is not automatically learning: accumulated records must be selected, validated, attributed, and incorporated into an effective update. This distinction creates a measurable bridge between execution relay and structural evolution.

## 3. A Minimal Evolutionary State Model

Let the system state at step \(t\) be

$$
\mathcal{S}_t=(U_t,G_t,C_t,F_t,H_t,E_t,\Gamma_t),
$$

where:

- \(U_t\): a set of versioned intelligence units;
- \(G_t\): typed relay and dependency graph;
- \(C_t\): interface and behavioral contracts;
- \(F_t\): perspective-indexed scoring policies or forests;
- \(H_t\): histories, provenance, and precedent records;
- \(E_t\): supporting and counter-evidence;
- \(\Gamma_t\): governance rules, permissions, and evaluator authority.

An evolutionary proposal \(a_t\) induces a candidate transition

$$
\widehat{\mathcal{S}}_{t+1}=T(\mathcal{S}_t,a_t,\xi_t),
$$

with \(\xi_t\) representing environmental uncertainty and stochastic effects. A separate governance procedure decides whether to deploy, sandbox, revise, or reject that candidate:

$$
\mathcal{S}_{t+1}=operatorname{Gate}(\mathcal{S}_t,\widehat{\mathcal{S}}_{t+1},\mathcal{V}_t).
$$

Here \(\mathcal{V}_t\) is a validation dossier, not a single scalar score. This separation between **proposal** and **authorization** is fundamental.

### 3.1 State identity and lineage

Each unit should have a stable logical identifier, a version, a declared interface, a provenance chain, and a supersession relationship. A change in identity or behavior must not silently inherit the trust assigned to an earlier version.

### 3.2 A note on state sufficiency

The tuple is a proposed abstraction. Its adequacy depends on the task and observation granularity. If latent model state, human judgment, or external services affect outcomes, those dependencies must be represented explicitly or acknowledged as unobserved.

## 4. Candidate Structural Evolution Operators

We propose typed operators, each with preconditions, expected effects, and rollback semantics.

| Operator | Candidate transformation | Principal risk |
|---|---|---|
| `ADD` | Introduce a new unit | Hidden dependencies or unbounded authority |
| `REPLACE` | Substitute a unit under a scoped contract | Distribution-shift failure |
| `COMPOSE` | Form a relay chain or graph | Error amplification and latency growth |
| `SPLIT` | Divide a broad unit into specialists | Loss of shared context |
| `MERGE` | Consolidate overlapping units | Loss of diversity and interpretability |
| `REWIRE` | Change routing or feedback topology | Emergent loops and instability |
| `REWEIGHT` | Modify perspective scoring | Reward hacking and Goodhart effects |
| `LOCALIZE` | Add differential routing or retrieval indices | Misclassification and stale localization |
| `IMPORT` | Integrate external intelligence pieces | Provenance and trust boundary violations |
| `RETIRE` | Remove obsolete or unsafe components | Unrecognized downstream reliance |
| `FORK` | Preserve alternative lineages | Fragmentation and evaluation overhead |

These operators are research primitives, not an exhaustive or universally safe instruction set.

## 5. Perspective-Dependent Fitness and Selection

There is no generally valid single fitness function for all UIERUs, subjects, and environments. Let \(p\) denote a perspective, \(c\) a context, and \(h\) an observed history. Define a conditional evaluation vector:

$$
\mathbf{q}(a\mid p,c,h)=
(q_{\mathrm{quality}},q_{\mathrm{cost}},q_{\mathrm{latency}},
q_{\mathrm{safety}},q_{\mathrm{robustness}},q_{\mathrm{novelty}}).
$$

A perspective-dependent preference relation \(\succeq_{p,c}\) may rank candidates, but the preference relation itself must be documented and subject to governance. Hard constraints cannot safely be collapsed into compensatory scalar weights without explicit authorization.

### 5.1 Evaluation sovereignty

Who is permitted to change a scoring forest, approve a deployment, or redefine success? A structurally intelligent system must distinguish candidate-generating authority from evaluator and deployment authority. Different stakeholders may legitimately use different perspectives.

### 5.2 Anti-Goodhart safeguards

A proposed improvement should be evaluated against:

- held-out tasks and adversarial cases;
- independent or partially independent evaluators;
- safety constraints and negative externalities;
- calibration and uncertainty estimates;
- counter-evidence retained with the same provenance discipline as supporting evidence.

A higher reported score alone is insufficient evidence of growth.

## 6. The Growth Loop and Its Failure Modes

A candidate loop is:

1. Observe a performance gap or an emerging opportunity.
2. Localize the relevant context, units, and constraints.
3. Generate alternative structural modifications.
4. Evaluate candidates in a bounded sandbox.
5. Compare across perspectives and counter-evidence.
6. Authorize a reversible deployment, or reject the change.
7. Record outcomes, lineage, and failures.
8. Update precedents and generate new research questions.

This is a **governed hypothesis-to-evidence loop**, not a claim that all cycles produce improvement.

### 6.1 Failure classes

- **Local-to-global inversion:** a faster unit slows the overall workflow through extra coordination.
- **Evaluator capture:** a candidate learns to exploit the measurement process.
- **Dependency fragility:** a replacement violates implicit assumptions downstream.
- **Exploration collapse:** short-term optimization removes diverse alternatives.
- **Historical lock-in:** accumulated precedents prevent novel paths from being considered.
- **Structural bloat:** more units increase cost without effective capability growth.
- **Governance drift:** repeated exceptions silently broaden permissions.
- **Irreversibility:** state changes make rollback or meaningful comparison impossible.

## 7. Measuring Growth Without Assuming It

Candidate measures should be reported separately rather than reduced prematurely to a single index.

### 7.1 Capability gain

Estimate the difference in task performance under a matched evaluation distribution, with confidence intervals and resource accounting.

### 7.2 Structural novelty

Distinguish a renamed component from a functionally new capability. Novelty may be measured relative to a versioned baseline, a task repertoire, and an explicit equivalence criterion.

### 7.3 Transfer and compositional gain

Test whether an added unit helps on unseen tasks or composes successfully with independently developed units. A successful isolated demonstration does not establish ecosystem-level growth.

### 7.4 Sustainability

Track regressions, maintenance costs, audit burden, safety violations, and the rate of invalidated prior guarantees. Growth that cannot be sustained or governed is not unambiguously beneficial.

### 7.5 Openness

A finite experimental horizon cannot prove infinite open-ended evolution. At most it can provide evidence for sustained novelty and transfer over the measured horizon, under declared constraints.

## 8. Dynamic Equivalence During Evolution

RELAY-002 frames behavioral equivalence as conditional and potentially revocable. Let

$$
U_i \approx_{p,c,h,\epsilon,T} U_j
$$

mean that two units satisfy a declared comparison relation under perspective \(p\), context \(c\), history \(h\), tolerance \(\epsilon\), and horizon \(T\). Evolution introduces a new question: how long does that relation remain valid after either unit changes?

A replacement decision should therefore include:

- a comparison contract and evidence window;
- a drift-monitoring policy;
- a revalidation trigger;
- a fallback or rollback route;
- a record of any assumptions that cannot be tested.

**Open problem:** identify sufficient conditions under which a local replacement preserves bounded system-level properties in an evolving relay graph.

## 9. Contracts and Compositional Growth

RELAY-003 treats composition as a contract problem. Structural evolution adds a temporal dimension: contracts may remain syntactically compatible while their empirical guarantees decay.

A proposed evolution contract may contain:

```yaml
change_id: EV-EXAMPLE-001
operation: REPLACE
candidate_unit: model-router-v3
replaces: model-router-v2
perspectives: [quality, latency, cost]
assumptions:
  task_family: bounded-text-analysis
  deployment_context: sandbox-first
required_guarantees:
  - no_privilege_expansion
  - interface_schema_compatible
  - rollback_available
validation:
  paired_replay: required
  adversarial_tests: required
  independent_evaluator: required
  drift_recheck: required
status: proposed
```

This is an illustrative research schema, not an implemented standard.

## 10. Perspective Masking and Evolutionary Observation

RELAY-001 motivates algebraic treatment of perspective masking. In evolutionary settings, the observed value of a change may differ depending on what is visible, what is held constant, and what is intervened upon.

Three distinct operations must not be conflated:

1. **Observational masking:** select a view of recorded states and outcomes.
2. **Replay comparison:** rerun candidates against matched recorded inputs, when feasible.
3. **Causal intervention:** actively change a unit or routing policy and observe the result.

A perspective differential tree can index changes in scores, choices, trajectories, and learning outcomes. The index is an aid to localization; it does not itself establish causality.

## 11. RSI–UIERU Convergence: A Two-Way Research Interface

Recursive self-improvement (RSI) studies systems that iteratively modify aspects of their own capabilities or improvement processes. UIERU research asks how evolving intelligence can be organized into explicit, composable, inspectable units and governed relay structures. These are related but not identical research programs.

### 11.1 RSI to UIERU

RSI techniques may supply candidate generation, search over structural modifications, automated testing, and iterative optimization. Candidate discoveries could become versioned UIERU components after independent evaluation.

### 11.2 UIERU to RSI

UIERU-like contracts, perspective scoring, provenance, differential localization, and counter-evidence channels may improve the auditability and control of RSI workflows.

### 11.3 Interpretability boundary

Explicit relay structures may improve **structural transparency**—which component was selected, under what contract, and with what evidence—without explaining the internal mechanisms of a neural model. Claims of improved interpretability must specify the level being measured.

### 11.4 Testable comparison

Compare an LLM-agent RSI workflow with and without an explicit structural governance layer, holding model access, task budget, and evaluation sets as comparable as possible. Measure improvement, cost, regressions, incident detection, and audit effort. Avoid treating a positive result on one benchmark as proof of general superiority.

## 12. Open-Endedness Versus Bounded Optimization

A system may optimize a fixed benchmark indefinitely without generating a new useful capability. Conversely, it may create many novel artifacts without increasing task competence.

We propose three separable axes:

- **Exploration breadth:** diversity of candidate structures and problem classes.
- **Verified capability growth:** improvements surviving independent evaluation.
- **Evolution of evaluators and questions:** creation of defensible new measurements or research problems.

The third axis creates a difficult meta-evaluation challenge: when a system changes the criteria of success, how can researchers distinguish legitimate discovery from self-serving metric revision?

## 13. Candidate Formal Problems

The following are open problems, not proven propositions.

### OP-01 — Structural reachability

Given a typed operator set and contract constraints, characterize which target architectures are reachable from a starting system.

### OP-02 — Safe local replacement

Find sufficient, empirically checkable conditions for a local unit substitution to preserve specified global properties.

### OP-03 — Growth under bounded resources

Determine when an evolutionary policy yields persistent improvement subject to finite compute, energy, data, and validation budgets.

### OP-04 — Evaluator robustness

Characterize conditions under which independent evaluators and counter-evidence reduce the probability of selecting reward-hacking candidates.

### OP-05 — Diversity preservation

Identify selection mechanisms that preserve useful alternatives without unbounded ecosystem growth.

### OP-06 — Nonstationary equivalence

Define revalidation schedules or error bounds for behavioral equivalence under learning and environmental drift.

### OP-07 — Compositional error accumulation

Bound how local uncertainty and failure probabilities propagate through branching or cyclic relay graphs.

### OP-08 — Novelty and functional contribution

Construct operational tests distinguishing superficial structural variation from genuine new task capability.

### OP-09 — Evolutionary provenance

Specify a minimal lineage and evidence representation sufficient to reproduce or audit a structural change.

### OP-10 — Governance invariants

Formalize invariants that prevent evolutionary operators from silently expanding their own authorization.

### OP-11 — Evaluator evolution

Study how evaluation criteria can be updated without erasing historical comparability or enabling arbitrary success redefinition.

### OP-12 — Research relay interoperability

Determine the minimal shared semantics required to transfer an evolutionary hypothesis and its counter-evidence between independent research groups.

## 14. Candidate Hypotheses and Falsification Tests

| ID | Hypothesis | Primary measure | Counter-evidence condition |
|---|---|---|---|
| H1 | Contract-governed replacement reduces severe regressions | Regression rate under matched changes | Equal or higher regression rate at matched budget |
| H2 | Perspective-aware selection improves multi-objective trade-offs | Pareto frontier or constrained utility | No robust improvement after held-out evaluation |
| H3 | Provenance-rich evolution improves diagnosis | Time and accuracy of root-cause identification | No gain or prohibitive audit overhead |
| H4 | Differential localization reduces candidate search cost | Compute and experiments per validated gain | Search cost rises without validated gain |
| H5 | Explicit counter-evidence reduces evaluator gaming | Undetected exploitation frequency | Gaming remains unchanged or worsens |
| H6 | Relay-compatible imports improve transfer | Held-out task success with resource controls | Gains vanish on transfer or violate contracts |
| H7 | RSI + structural governance yields better audited improvement | Quality, safety, and auditability jointly | Improvement is absent or dominated by overhead |
| H8 | Diversity-preserving selection supports longer-run adaptation | Recovery and transfer under distribution shifts | Diversity incurs cost without resilience benefit |

These hypotheses require preregistered metrics, matched baselines, and confidence reporting before strong empirical claims can be made.

## 15. An Illustrative Experimental Program

### Experiment A — Evolution operator benchmark

Create a sandbox of small, versioned task-solving units. Allow `ADD`, `REPLACE`, `COMPOSE`, and `REWEIGHT` under fixed resource limits. Compare fixed architecture, unconstrained search, and contract-governed evolution.

### Experiment B — Hidden dependency challenge

Introduce downstream consumers with partially implicit expectations. Measure whether contract tests, differential trees, and adversarial evaluation detect unsafe replacements.

### Experiment C — Perspective conflict

Use multiple legitimate objectives—quality, cost, latency, safety—with hard constraints and changing contexts. Test whether perspective-aware methods preserve constraints while adapting choices.

### Experiment D — Longitudinal drift

Run repeated learning cycles. Recheck previously approved equivalence and contract claims, recording the rate and causes of invalidation.

### Experiment E — RSI governance interface

Wrap an iterative LLM-agent improvement workflow in versioned unit contracts and evidence capture. Compare against a similarly resourced workflow without the wrapper. Include negative results and overhead.

### Experiment F — Open research relay

Exchange a research hypothesis package between independent teams. Measure whether the receiving team can reproduce assumptions, run a falsification test, and return a machine-readable counter-evidence report.

## 16. Evidence and Counter-Evidence Protocol

Every accepted change should carry an evidence dossier:

```yaml
proposal_id: EV-EXAMPLE-001
baseline_version: system-v1
candidate_version: system-v2
claim: "lower latency without loss of task quality"
perspective: latency-constrained-quality
context_scope: bounded-text-analysis
supporting_evidence:
  - paired_replay_results
  - held_out_evaluation
counter_evidence:
  - adversarial_regression_cases
  - unresolved_failure_modes
uncertainty:
  confidence_method: bootstrap-interval
  untested_contexts: [multilingual-long-context]
governance:
  approver_role: independent-reviewer
  deployment_stage: sandbox
  rollback_reference: system-v1
status: awaiting-validation
```

A negative result is a valid research contribution when the assumptions, test conditions, and failure mechanism are clearly recorded.

## 17. Research Governance and Safety Boundaries

Open structural evolution is not equivalent to unrestricted self-modification. Research systems should enforce:

- bounded experimental authority and sandbox isolation;
- separation of proposal, evaluation, and deployment permissions;
- immutable or independently controlled audit records;
- explicit resource ceilings and termination criteria;
- revalidation when environments, dependencies, or evaluators change;
- reversible deployment wherever technically possible;
- independent review for changes affecting safety or governance mechanisms.

Governance itself is a research subject: controls can fail, and their effectiveness must be tested rather than assumed.

## 18. Research Relay Package: Suggested Interface

```yaml
research_relay_piece:
  id: RELAY-005
  title: Open Structural Evolution
  version: 1.0.0
  authors:
    - Sizhe Tan
    - GPT-Obot
  status: open-research
  problem:
    statement: >-
      Under what conditions can versioned intelligence units and
      relay graphs undergo verified, composable, and governable
      structural growth?
    scope:
      - dynamic-intelligence-units
      - typed-relay-graphs
      - evidence-bearing-evolution
  proposed_model:
    state: [units, graph, contracts, perspectives, history, evidence, governance]
    operators: [ADD, REPLACE, COMPOSE, SPLIT, MERGE, REWIRE, REWEIGHT, IMPORT, RETIRE]
  hypotheses: [H1, H2, H3, H4, H5, H6, H7, H8]
  open_problems: [OP-01, OP-02, OP-03, OP-04, OP-05, OP-06, OP-07, OP-08, OP-09, OP-10, OP-11, OP-12]
  validation:
    minimum: [matched-baseline, held-out-tests, counter-evidence, provenance]
    outputs: [results, failures, confidence, resource-cost, reproducibility-notes]
  interfaces:
    upstream: [RELAY-001, RELAY-002, RELAY-003, RELAY-004]
    related: [BUI-008, CASE-001, CASE-002, CASE-003]
  contribution_policy:
    accept: [formalization, proof, counterexample, implementation, experiment, replication]
    require: [assumptions, methods, provenance, limitations, attribution]
```

The schema is intentionally provisional. A later `SPEC-004-Research-Relay-Piece-Contract.md` may define a stricter, machine-checkable version.

## 19. Collaboration Opportunities by Discipline

**Mathematics and formal methods:** reachability, compositional verification, stochastic guarantees, bisimulation under drift, governance invariants.

**AI/ML and RSI researchers:** candidate-generation efficiency, evaluator design, automated testing, search under resource constraints, model-based and model-free improvement loops.

**Distributed systems and software engineering:** interface versioning, lineage, rollback, dependency analysis, reliable relay protocols.

**Control and dynamical systems:** stability of adaptive feedback networks, bounded uncertainty, disturbance response, multi-timescale evolution.

**Cognitive and biological sciences:** empirically testable analogies concerning adaptation, functional reorganization, and context-dependent coordination, without assuming biological identity with UIERU.

**Research infrastructure:** portable evidence dossiers, counterexample registries, reproducibility packages, and attribution-preserving relay.

## 20. Staged Validation Roadmap

**Stage 0 — Semantics.** Specify units, contracts, operators, perspectives, and observation boundaries.

**Stage 1 — Toy formal systems.** Establish limited theorems or counterexamples for constrained compositions and replacements.

**Stage 2 — Controlled software experiments.** Test operators with explicit baselines and reproducible synthetic tasks.

**Stage 3 — Realistic agent workflows.** Evaluate tool-using and self-improving agents under comparable budgets.

**Stage 4 — Longitudinal governance.** Measure drift, accumulated dependencies, rollback reliability, and evaluator failures over repeated cycles.

**Stage 5 — Independent research relay.** Transfer hypotheses, evidence, and counter-evidence to external teams for replication or rejection.

Each stage can invalidate assumptions of the next. Progress is contingent on evidence, not a predetermined schedule.

## 21. Relations to the BUI-DSI Research Series

- **BUI-001:** the move from relatively static structural descriptions to dynamic intelligence units.
- **BUI-002 / RELAY-001:** perspective masking and observational semantics.
- **BUI-003:** perspective differential trees for localizing change.
- **BUI-004:** perspective-aware structural queries over evolving evidence.
- **BUI-005 / RELAY-002:** conditional dynamic equivalence and substitution.
- **BUI-006:** mathematical foundations and open formal questions.
- **BUI-007 / RELAY-004:** bounded biological analogies and empirical falsification.
- **BUI-008:** open research relay as a method of transferring unfinished scientific work.
- **RELAY-003:** contracts and composition as constraints on system-level evolution.
- **CASE-001–003:** concrete scenarios for perspective selection, substitution, and context-dependent biological intelligence.

## 22. Research Risks and Unresolved Tensions

1. **Expressiveness versus verifiability:** rich evolving structures may defeat practical formal checking.
2. **Novelty versus reproducibility:** genuinely new capabilities may require new evaluations that break comparability.
3. **Autonomy versus accountability:** self-generated improvements require independent authorization boundaries.
4. **Composability versus emergence:** local contracts may fail to capture global interactions.
5. **Speed versus evidence quality:** rapid iteration can outrun robust evaluation.
6. **Open interfaces versus attack surface:** interoperability may introduce unsafe dependencies.
7. **Efficiency versus diversity:** aggressive selection can erase useful alternatives.
8. **Structural transparency versus model opacity:** inspectable architecture does not imply interpretable internal models.

These tensions should be maintained as explicit research questions rather than resolved by rhetoric.

## 23. Conclusion: Growth as an Auditable Research Process

The promise of open structural evolution is not an infinitely expanding graph of intelligence units. It is the possibility that a system can **discover useful new structures, test them against alternatives, integrate them through contracts, preserve counter-evidence, and revise itself without surrendering accountability**.

UIERU provides one proposed vocabulary for this research: versioned intelligence units, perspective-aware valuation, structural relay, dynamic equivalence, and governed evolution. RSI contributes complementary questions and techniques for generating and iterating improvements. Whether the combination yields durable gains remains to be demonstrated.

The next scientific step is therefore not to declare an open-ended intelligence architecture complete, but to publish precise problems, falsifiable hypotheses, experimental interfaces, and negative results that other researchers can inherit. That is the purpose of **Open Research Relay**.

---

## Suggested Background Reading

The following works provide established neighboring concepts; they are not presented as validations of UIERU:

- Holland, J. H. (1992). *Adaptation in Natural and Artificial Systems* (2nd ed.). MIT Press.
- Lehman, J., & Stanley, K. O. (2011). Abandoning objectives: Evolution through the search for novelty alone. *Evolutionary Computation*, 19(2), 189–223.
- Stanley, K. O., Lehman, J., & Soros, L. (2017). Open-endedness: The last grand challenge you've never heard of. *O'Reilly AI Newsletter* (essay).
- Sutton, R. S., & Barto, A. G. (2018). *Reinforcement Learning: An Introduction* (2nd ed.). MIT Press.
- Alur, R. (2015). *Principles of Cyber-Physical Systems*. MIT Press.
- Clarke, E. M., Grumberg, O., & Peled, D. A. (1999). *Model Checking*. MIT Press.

**Citation note:** Cite this Research Relay Piece as a proposed research agenda. Formal definitions, operator semantics, and hypotheses remain open to correction and refinement.

**Authors:** Sizhe Tan & GPT-Obot  
**Repository:** Beyond-UIERU-Dynamic-Structural-Intelligence  
**Version:** 1.0.0

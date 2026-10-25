# BUI-008 — Open Research Relay and the Next Horizon of Structural Intelligence

**Project:** Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay (BUI-DSI)  
**Version:** 1.0.0 — Research agenda and conceptual proposal  
**Authors:** Sizhe Tan & GPT-Obot  
**Date:** 2026-10-25  
**Status:** Open research proposal; definitions and hypotheses are provisional

## Abstract

The Universal Intelligence Evolution and Relay Unit (UIERU) motivates a change in the working granularity of Structural Intelligence (SI): from relatively static representations, routing structures, and contracts toward units whose decisions, evaluations, interactions, and internal configurations evolve with perspective, context, environment, and history. This change also exposes a second-order challenge: how can researchers observe, locate, compare, query, substitute, compose, and validate such evolving units without presuming complete knowledge of their internal mechanisms? This paper closes the eight-part BUI-DSI research sequence by proposing **Open Research Relay** as a reproducible way to publish the *research problems themselves* as portable, inspectable, contestable pieces. It defines a minimal Research Relay Piece contract, distinguishes established evidence from proposed models and untested hypotheses, identifies mathematical, neuroscientific, and engineering collaboration interfaces, and outlines a phased validation roadmap. The purpose is not to claim that dynamic structural intelligence has been solved, but to make its emerging problems visible, structured, testable, and openly relayable.

**Keywords:** Structural Intelligence; UIERU; dynamic intelligence; research relay; perspective masking; differential localization; behavioral equivalence; formal methods; computational neuroscience; collective structural learning; counter-evidence.

---

![Fig-008-Open-Research-Relay-Ecosystem.png](../figures/Fig-008-Open-Research-Relay-Ecosystem.png)

---

## 1. Purpose and Scope

This paper is both the conclusion of the BUI-DSI core sequence and a handoff to future researchers. It advances three limited claims:

1. Dynamic intelligence units introduce research questions that cannot be settled by static descriptors alone.
2. Those questions can be decomposed into independently examinable mathematical, biological, and engineering research pieces.
3. Publishing those pieces with explicit assumptions, evidence, failure cases, and interfaces can improve the quality and continuity of collective research.

It **does not** claim a universal mathematical theory of intelligence, a demonstrated neural implementation of UIERU, or validated superiority of any proposed algorithm. Its primary contribution is a structured, falsifiable research agenda and a reusable relay contract.

## 2. The Research Lineage: Why This Horizon Became Visible

BUI-DSI emerges from a path-dependent sequence of SI investigations. This lineage is a motivation and provenance record, not a claim of priority over related external research.

| Research emphasis | Representative SI concepts | New capability or question |
|---|---|---|
| Structural representation and branching | MDT, CCC, Calling Graph | How to describe and dispatch structured differences and actions |
| Localized intelligence | UTN, per-node intelligence | Where relevant capability resides and how to invoke it |
| Portable intelligence and interoperability | PIRP/PIRU, contracts, relay | How intelligence components travel and cooperate |
| Evaluation and governance | UCPSF, scoring forests, control planes | Whose perspective governs selection and optimization |
| Open structural systems | SIF, dual maps, counter-evidence | How to locate and grow capability across changing structures |
| Dynamic unit integration | UIERU | How evaluation, execution, feedback, relay, and evolution form an operating unit |
| Research of dynamic units | BUI-DSI | How to observe, compare, query, and verify evolving units |

The move to UIERU is best understood as a **change of analytical granularity**, not proof that UIERU is the final or fundamental unit of intelligence. Subsequent research may require dynamically formed unit boundaries, relationships among units, and collective evolution as first-class objects.

## 3. From First-Order Evolution to Second-Order Research

A first-order problem asks how a unit learns or changes:

\[
U_{t+1} = \mathcal{E}(U_t, a_t, o_t, h_t).
\]

Here \(\mathcal{E}\) is an abstract update operation; its meaning depends on the implementation. A second-order problem asks how a research or engineering system can establish warranted claims *about* the evolving unit:

\[
K_{t+1} = \mathcal{R}(K_t, D_t, A_t, X_t),
\]

where \(K_t\) is the current body of qualified knowledge, \(D_t\) new observations, \(A_t\) assumptions and model revisions, and \(X_t\) counter-evidence. The expression is a conceptual schema, not a validated law of scientific progress.

This second-order layer should itself support provenance, versioning, dispute resolution, and revision. It must not silently promote an empirical regularity into a universal theorem.

## 4. The BUI-DSI Core Research Interfaces

The preceding seven papers establish a connected research program:

| Paper | Research interface | Main unresolved issue |
|---|---|---|
| BUI-001 | Static-to-dynamic granularity transition | What counts as a dynamic intelligence unit? |
| BUI-002 | Perspective masking and observation | When does a mask preserve meaning rather than alter behavior? |
| BUI-003 | Perspective differential trees and localization | How can dynamic differences be indexed without conflating contexts? |
| BUI-004 | Perspective-aware structural query and SQL | Which claims are supported by stored evidence versus simulation? |
| BUI-005 | Dynamic equivalence, relay composition, relations | Under what contracts is substitution safe? |
| BUI-006 | Mathematical foundations | Which formal properties can be proved, disproved, or bounded? |
| BUI-007 | Biological organizational biomimicry | Which functional parallels have experimental support? |
| BUI-008 | Open research relay | How can others inherit and challenge the agenda? |

These interfaces are mutually informative, but no paper depends on accepting every hypothesis in the others.

## 5. A Minimal Research Relay Piece (RRP)

A **Research Relay Piece** is a portable, versioned research object that enables another investigator to understand, reproduce where applicable, challenge, or extend a specific claim or problem without reconstructing the entire originating research program.

We propose the provisional contract:

\[
\mathrm{RRP}=(P,M,H,E,V,I),
\]

where:

- **P — Problem:** scope, motivation, research question, exclusions.
- **M — Model:** terms, assumptions, mathematical or computational representation, boundary conditions.
- **H — Hypotheses:** testable propositions, conjectures, or explicitly labeled design expectations.
- **E — Evidence:** observations, sources, counter-evidence, negative results, uncertainty, provenance.
- **V — Validation:** tests, proof obligations, controls, baselines, failure criteria, reproducibility requirements.
- **I — Interfaces:** inputs, outputs, dependencies, compatibility contracts, authorship, licensing, versioning, citations.

This tuple is an organizational proposal rather than a new mathematical discovery. Its adequacy must be evaluated by whether it improves reuse, scrutiny, and research progress.

### 5.1 Recommended RRP metadata

```yaml
rrp_id: BUI-RELAY-001
version: 0.1.0
status: open-problem
question: "Under what assumptions do perspective masks compose?"
model_ref: "specs/SPEC-002-Perspective-Masking-Contract.md"
assumptions:
  - "Observation masks do not mutate the source system"
hypotheses:
  - id: H1
    statement: "Selected masks are idempotent under a fixed observation schema"
evidence:
  positive: []
  counterexamples: []
validation:
  proof_obligations: []
  experiments: []
interfaces:
  related_papers: ["BUI-002", "BUI-006"]
provenance:
  authors: ["Sizhe Tan", "GPT-Obot"]
  date: "2026-10-25"
```

The example illustrates a proposed interchange shape; it is not a completed, tested specification.

## 6. The Five Initial Relay Tracks

### RELAY-001 — Perspective Masking Algebra

**Question:** Under what precise assumptions are observation masks idempotent, commutative, composable, or semantics-preserving?

**Research entry:** Specify pure projections separately from interventions that alter scoring or state. Construct minimal counterexamples to unjustified algebraic identities. Compare with projection operators, database views, and program semantics.

**Useful deliverables:** definitions; a theorem with assumptions; a counterexample library; executable property tests.

### RELAY-002 — Dynamic Behavioral Equivalence

**Question:** What kind of equivalence or approximate distance is sufficient for a particular substitution decision?

**Research entry:** Compare output agreement, trace similarity, probabilistic behavior, contextual equivalence, and bisimulation-inspired criteria. Explicitly scope task distributions, perspectives, and observation horizons.

**Useful deliverables:** metrics with limits; contextual substitution contracts; adversarial tests.

### RELAY-003 — Relay Composition and Contracts

**Question:** Which properties survive composition of heterogeneous, stateful intelligence units?

**Research entry:** Study assume-guarantee reasoning, interface compatibility, feedback loops, resource contention, and interference between evolving components.

**Useful deliverables:** compositional proof rules, counterexamples, relay protocol tests.

### RELAY-004 — Biological Dynamic Intelligence

**Question:** Are UIERU-like functions better modeled as fixed modules, dynamic assemblies, or multiple interacting organizational levels?

**Research entry:** Use computational neuroscience literature and data to distinguish observed neural phenomena from SI-inspired interpretations. Compare task-dependent functional organization, context inference, valuation, and learning.

**Useful deliverables:** preregisterable predictions, model comparisons, explicit null hypotheses.

### RELAY-005 — Open Structural Evolution

**Question:** How can identity, provenance, and guarantees be maintained when unit boundaries, contracts, and internal mechanisms change?

**Research entry:** Explore versioned transition systems, dynamic graphs, invariant monitoring, and evolutionary histories. Investigate when old evidence expires after structural change.

**Useful deliverables:** identity policies, evidence-validity rules, update-safe contracts.

## 7. Perspective Masking as a Shared Experimental Handle

Masking is a promising bridge between established SIF localization mechanisms and UIERU dynamics because it can expose constrained views of a complex unit. But it must not be treated as one undifferentiated operation.

We distinguish:

1. **Observational projection:** selects what is displayed or measured without modifying the underlying process.
2. **Execution intervention:** changes available inputs, scoring components, actions, or connections and can change the process.
3. **Counterfactual reconstruction:** estimates what would have occurred under an unobserved configuration and therefore requires assumptions or a causal model.

A useful comparison contract should record the unit version, task, candidate set, perspective semantics, context, environmental conditions, history window, mask semantics, scoring normalization, and provenance. Without this alignment, a differential tree can faithfully index an *invalid comparison*.

## 8. Differential Trees and Structural Query as Relay Infrastructure

Perspective Differential Trees (PDT) and Perspective-Aware Structural Query (PASQ) provide candidate engineering interfaces for organizing dynamic evidence.

A PDT may index differences at scoring, decision, trajectory, and learning/evolution levels. PASQ may retrieve those records using relational, graph, and temporal query mechanisms. Their roles differ:

- **PDT:** structured comparison and navigation among qualified differences.
- **PASQ:** declarative retrieval and aggregation over recorded evidence.
- **Simulation/experimentation:** generation of new observations under controlled interventions.
- **Governance:** labeling, provenance, validation, and counter-evidence handling.

An SQL query over observations cannot by itself establish a causal effect or an unobserved counterfactual. Query correctness, evidence sufficiency, and causal validity are separate obligations.

## 9. Mathematical Research: Make the Questions Independently Interesting

A mathematical collaborator should be able to engage a precise problem without first accepting the entire SI vocabulary. The following translations may help:

| SI problem | Established research connections |
|---|---|
| Perspective masking | Algebraic projections, abstract interpretation, program semantics |
| Dynamic equivalence | Labeled transition systems, bisimulation, probabilistic metrics |
| Relay composition | Assume-guarantee reasoning, process algebra, control theory |
| Dynamic query | Relational algebra, temporal databases, provenance semirings |
| Open evolution | Dynamic graphs, nonstationary systems, runtime verification |

These connections are starting points for literature review, not claims that the corresponding fields lack prior solutions. New contributions must be distinguished from restatements of known results.

An exemplary formal problem is: *Given a stateful transition system and two observation masks, characterize sufficient and necessary conditions for mask composition to preserve a chosen trace property.* Both positive theorems and minimal counterexamples count as useful results.

## 10. Biological Intelligence: Hypothesis, Not Identification

Biological brains exhibit context-dependent behavior, distributed computation, value-related learning, and plasticity. Such phenomena motivate dynamic organizational abstractions. They do not establish that a brain contains explicit UIERU units, scoring forests, SQL-like queries, or software-style relay contracts.

The strongest research strategy is comparative:

- Define an SI-inspired computational model and competing models.
- Specify measurable predictions that differ between models.
- Use appropriate behavioral or neural evidence, including null results.
- Record confounds and limits of interpretation.
- Revise or abandon the analogy when it fails.

A particularly important open question is whether functional unit boundaries are fixed, context-dependent, or distributed across scales. This could force revisions to the UIERU abstraction itself.

## 11. Beyond the Unit: Dynamic Intelligence Relationships

The next useful research object may be a **relationship**, not merely a larger unit. Let

\[
R_{ij}(t,p,c,h)
\]

be a provisional description of how units \(i\) and \(j\) relate under time, perspective, context, and history. Candidate relations include relay, dependency, competition, substitution, cooperation, shared learning, and governance.

Such relations may be directed, weighted, typed, and time-varying. A multi-unit system may therefore require joint analysis of:

\[
\text{Unit Dynamics} + \text{Relationship Dynamics} + \text{Collective Evolution}.
\]

The sum is conceptual, not a literal additive decomposition. Interactions may create emergent behavior that cannot be inferred from isolated unit evaluations.

## 12. Two-Way Research Relay and Counter-Evidence

An open research relay should support both **forward extension** and **backward correction**:

- Forward: a published problem is inherited, formalized, tested, or generalized.
- Backward: a new theorem, counterexample, replication failure, or conflicting dataset changes the status of earlier claims.

Each RRP should therefore track:

| Evidence status | Meaning |
|---|---|
| Established within stated scope | Supported by a specified proof or reproducible evidence |
| Proposed | Coherent model or mechanism, not yet validated |
| Open hypothesis | Testable claim without decisive evidence |
| Contested | Credible conflicting evidence or unresolved assumptions |
| Refuted within stated scope | Counterexample or valid negative result defeats the claim |
| Superseded | Replaced by a newer version, with traceable history |

This is consistent with two-way CCC, counter-evidence governance, and anti-Goodhart principles: the goal is not to maximize positive confirmations, but to improve the reliability of the shared research map.

## 13. A Phased Validation Roadmap

### Phase 0 — Literature and novelty audit

Map the agenda against prior work in formal verification, dynamical systems, databases, multi-agent systems, and neuroscience. Identify what is inherited, adapted, or genuinely open.

**Exit condition:** a claim-to-literature matrix with no unsupported novelty assertions.

### Phase 1 — Minimal formal and data models

Specify a stateful UIERU abstraction, observational masks, comparison contracts, and evidence schema. Build deliberately small counterexamples.

**Exit condition:** precise definitions and at least one reproducible failing case for an overbroad claim.

### Phase 2 — MET prototypes

Test PDT and PASQ on versioned decision traces with controlled perspective changes. Compare against simpler baselines such as flat event tables and conventional indexed queries.

**Exit condition:** measured utility and failure modes, not merely a working demonstration.

### Phase 3 — Compositional validation

Test contextual substitution and relay contracts under state changes, resource constraints, and feedback interference.

**Exit condition:** explicit conditions under which a property is preserved or fails.

### Phase 4 — Cross-disciplinary relay

Invite independent mathematical proofs, computational neuroscience model comparisons, and third-party replications.

**Exit condition:** externally inspectable contributions with provenance, negative results, and versioned revisions.

## 14. Research Collaboration and Attribution

The repository should welcome contributions from mathematics, theoretical computer science, databases, formal methods, control theory, computational neuroscience, and engineering. Contributions may include corrected definitions, literature connections, counterexamples, experimental designs, data, implementations, or independent critique.

A contributor should be able to cite an individual RRP or paper and explain exactly which assumptions and claims were extended. Authorship, acknowledgments, license permissions, and provenance should be preserved. A DOI provides a persistent reference to a release; it does not certify correctness, novelty, or peer review.

The repository should avoid presenting a single project vocabulary as a prerequisite for participation. Where possible, provide a translation from SI terminology into established disciplinary language.

## 15. Research Risks and Safeguards

**Over-generalization:** behavior under a few perspectives may not generalize to unseen contexts. *Safeguard:* state domain and distribution bounds.

**Mask-induced distortion:** interventions can change the very behavior under study. *Safeguard:* distinguish observation, intervention, and counterfactual inference.

**False equivalence:** similar outputs do not imply safe substitution. *Safeguard:* specify contextual and compositional obligations.

**Elegant but irrelevant mathematics:** convenient assumptions can erase open evolution. *Safeguard:* keep executable counterexamples and stress tests alongside formal work.

**Biological overclaim:** functional analogy may be mistaken for anatomical correspondence. *Safeguard:* require independent empirical tests and alternative models.

**Research fragmentation:** portable pieces may lose the assumptions that made them valid. *Safeguard:* versioned contracts, dependency links, and provenance.

**Priority inflation:** path-dependent discovery may be mistaken for exclusive originality. *Safeguard:* conduct systematic literature reviews and cite relevant antecedents.

## 16. Proposed Repository Interfaces

The following companion materials are planned as independently maintainable artifacts:

```text
research-relay/
  RELAY-001-Perspective-Masking-Algebra.md
  RELAY-002-Dynamic-Behavioral-Equivalence.md
  RELAY-003-Relay-Composition-and-Contracts.md
  RELAY-004-Biological-Dynamic-Intelligence.md
  RELAY-005-Open-Structural-Evolution.md
  RESEARCH-COLLABORATION.md
specs/
  SPEC-001-Dynamic-UIERU-Observation-Model.md
  SPEC-002-Perspective-Masking-Contract.md
  SPEC-003-Dynamic-Differential-and-Query-Schema.md
  SPEC-004-Research-Relay-Piece-Contract.md
OPEN-QUESTIONS.md
TESTABLE-HYPOTHESES.md
VALIDATION-ROADMAP.md
```

These paths denote planned interfaces; their inclusion here does not imply the files or their implementations already exist.

## 17. Proposed Testable Hypotheses

**H1 — Mask qualification:** Explicitly distinguishing observational and intervention masks reduces invalid dynamic comparisons relative to an unqualified masking baseline.

**H2 — Differential localization:** A PDT-based index improves retrieval of relevant perspective-dependent differences on selected benchmark workloads compared with a flat trace index, after accounting for construction and maintenance costs.

**H3 — Query reproducibility:** PASQ with explicit comparison contracts yields more reproducible analytic results than queries omitting context and version alignment.

**H4 — Contextual substitution:** A contract-aware dynamic-equivalence test detects more unsafe substitutions than output-only similarity on adversarial relay tasks.

**H5 — Relay quality:** Research Relay Pieces with assumptions, counter-evidence, and validation protocols enable more accurate independent reproduction or critique than narrative-only problem statements.

**H6 — Biological model comparison:** A context-sensitive, dynamically organized model predicts specified task-switching observations better than an appropriately matched fixed-module baseline on a defined dataset.

These are hypotheses, not empirical findings. Each requires benchmark design, baselines, metrics, and preregistered or otherwise explicit failure criteria before strong conclusions are drawn.

## 18. What Would Count as Progress?

Progress need not mean proving that UIERU is a universal intelligence primitive. More defensible outcomes include:

1. A counterexample showing that a proposed masking law fails under stateful intervention.
2. A precise equivalence notion useful for one class of relay substitutions.
3. A PASQ schema that makes provenance and temporal comparability explicit.
4. A failed biological analogy that narrows the range of plausible models.
5. A proof obligation that exposes hidden assumptions in a composition contract.
6. A research relay contribution that can be independently reproduced and extended.

A negative result can be as important as a successful prototype when it improves the map of what is and is not possible.

## 19. Future Research Horizon

Several horizons deserve continued scanning:

- **Endogenous perspectives:** units that infer or learn the perspective under which they evaluate actions.
- **Dynamic unit boundaries:** units assembled or dissolved according to task and context.
- **Collective intelligence relations:** network-level behavior not reducible to isolated units.
- **Evidence expiration:** formal criteria for when prior observations cease to support claims after structural updates.
- **Research-tool evolution:** systems that revise their own localization, comparison, and validation methods under governance.
- **Human–AI research sovereignty:** transparent allocation of decision authority, attribution, and accountability across collaborative research.

None should be treated as an inevitable next stage. The appropriate research granularity should follow evidence and explanatory utility.

## 20. Conclusion: Publish the Research Lens

The most durable contribution of BUI-DSI may be neither a new algorithm nor a definitive theory, but a *research lens*: a structured way to recognize that dynamic intelligence units demand new methods of observation, comparison, formalization, and validation.

The SI research lineage made this horizon visible. That path dependence creates an opportunity to document it, not an entitlement to exclusive ownership of the questions. Open Research Relay turns that opportunity into a practical obligation: define problems clearly, expose assumptions, preserve counter-evidence, and make continuation possible for people who do not share the original research history.

**The purpose of this work is not to claim that dynamic structural intelligence has been solved, but to make its emerging problems visible, structured, testable, and openly relayable.**

## 21. Selected Research Connections (for Subsequent Literature Review)

The following are established bodies of work to investigate, not claims of direct derivation or exhaustive citations:

- Milner, R. *Communication and Concurrency* (1989) — process interaction and behavioral equivalence.
- Clarke, E. M., Grumberg, O., and Peled, D. A. *Model Checking* (1999) — formal verification of transition systems.
- Cousot, P., and Cousot, R. “Abstract Interpretation: A Unified Lattice Model for Static Analysis of Programs by Construction or Approximation of Fixpoints” (1977) — abstraction and soundness.
- Abadi, M., and Lamport, L. “Composing Specifications” (1993) — compositional specification reasoning.
- Pearl, J. *Causality: Models, Reasoning, and Inference*, 2nd ed. (2009) — observation versus intervention.
- Kandel, E. R., et al. *Principles of Neural Science*, 6th ed. (2021) — biological neural systems and learning.

Future releases should add complete, verified bibliographic records and domain-specific reviews before asserting novelty or priority.

---

## Citation and Research Status

**Suggested citation (before DOI registration):**  
Tan, Sizhe, and GPT-Obot. (2026). *BUI-008: Open Research Relay and the Next Horizon of Structural Intelligence*. In *Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay*, version 1.0.0. GitHub research repository.

**Research status:** Conceptual framework, proposed interfaces, and open hypotheses. Not peer-reviewed; no mathematical or biological claims in this paper should be interpreted as experimentally validated without separate evidence.

**License:** Refer to the repository's `LICENSE.txt` file. No license is asserted by this document independently.

---

## 📚 DBM-SI Series Navigation

See:\
[./docs/DBM-SI-Series-of-gitHub-Repositories/DBM-SI-Series-of-gitHub-Repositories.md](../docs/DBM-SI-Series-of-gitHub-Repositories/DBM-SI-Series-of-gitHub-Repositories.md)

---
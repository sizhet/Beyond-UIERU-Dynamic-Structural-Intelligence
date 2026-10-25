# GLOSSARY — Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay

**Project:** BUI-DSI  
**Version:** 1.0.0  
**Authors:** Sizhe Tan & GPT-Obot  
**Date:** 2026-10-25  
**Status:** Working research vocabulary; proposed terms and hypotheses are not established scientific standards.

## 1. Purpose and reading conventions

This glossary establishes consistent terminology across [the core papers](CONTENTS.md), [research cases](CONTENTS.md#3-research-cases--cases), [Research Relay Pieces](CONTENTS.md#4-open-research-relay--research-relay), and [specifications](CONTENTS.md#5-specifications--specs). It distinguishes established disciplinary terminology from **project-defined** abstractions and **candidate** mathematical relations. The same word may have a narrower meaning inside a comparison contract than in ordinary language.

**Terminology status:**
- **Established:** widely used concept in mathematics, computer science, machine learning, or neuroscience; local use is described here without asserting a new discovery.
- **Project-defined:** an architectural or methodological term defined for this research program.
- **Proposed:** a research construct whose mathematical properties or empirical utility remain to be demonstrated.

## 2. Foundational structural intelligence terms

### Structural Intelligence (SI) — project-defined research program

An approach to intelligence emphasizing explicit structures for representation, localization, evaluation, selection, action, composition, evidence, and evolution. SI does not imply that all intelligence can be represented structurally or that structural visibility fully explains opaque components.

### Dynamic Structural Intelligence (DSI) — project-defined

The study of intelligence systems whose behavior and organization vary with context, perspective, history, feedback, learning, and structural modification. Its objects of study include changing relations among intelligence units, not only their static descriptions.

### Universal Intelligence Evolution and Relay Unit (UIERU) — project-defined

A proposed composable intelligence-unit abstraction that can be observed through context, perspective, valuation, selection, action, feedback, history, and evolution interfaces. A UIERU may encapsulate opaque models, symbolic components, tools, humans, or hybrids; it is not claimed to be a natural biological unit or a proven universal substrate.

### Dynamic UIERU

A UIERU treated as a stateful, time-evolving process rather than a fixed function. An illustrative observation-level representation is

\[
U_t = (I_t, C_t, P_t, V_t, A_t, F_t, H_t, E_t, G_t),
\]

where identity/boundary, context, perspective, valuation, action, feedback, history, evolution state, and governance are **modeling coordinates**, not a universally required physical decomposition. The symbols are local to this illustration and do not override schemas in SPEC-001.

### Intelligence Unit / Per-Node Intelligence

A localized capability or decision-bearing component within a larger architecture. **Per-node** emphasizes that different nodes may use different representations, models, policies, or computational resources.

### Localization

The process of identifying which unit, structural region, precedent, or capability is relevant to a task under stated constraints. **Dynamic localization** also accounts for time, context, history, and evolving unit boundaries.

### Scoring Forest — project-defined

A collection of potentially heterogeneous scoring trees or evaluation structures representing multiple application directions, objectives, or viewpoints. Scores from different trees are not automatically commensurable; aggregation requires explicit assumptions or policy.

### Control Plane

The layer specifying policies, constraints, routing, authorization, and governance of intelligence operations. In this project, control-plane decisions should be distinguishable from a unit's opaque internal inference.

### Perspective

An explicitly specified evaluative or observational viewpoint, such as quality, latency, cost, safety, or biological function. A perspective may select evidence fields, assign weights, impose constraints, or determine a comparison target. **Perspective is not equivalent to a hidden subjective experience.**

### Perspective Sovereignty / Evaluation Sovereignty — project-defined

The question of which subject or authorized authority may define, prioritize, revise, or override evaluation criteria. A shared scoring interface does not imply shared authority to choose objectives.

### Context

Task, environment, constraints, external state, and other conditions that may change the meaning of an observation or the behavior of a unit. A context identifier without a description of relevant conditions is often insufficient for scientific comparison.

### History / Structural Precedent

Time-ordered observations, actions, feedback, modifications, and prior decisions that may influence present behavior. A **structural precedent** is a recorded prior pattern or solution that can be retrieved and compared; it is not automatically valid in a new context.

### Structural Growth

A validated or at least explicitly tracked change in the organization of an intelligence system—such as adding, splitting, replacing, rewiring, or composing units. Performance improvement alone does not establish structural growth.

## 3. Observation, masking, and causal boundaries

### Dynamic Observation — project-defined

A timestamped, provenance-bearing record of a unit's relevant context, perspective, state, action, output, feedback, and evolution metadata. Observation is **not** an explanation of underlying mechanisms.

### Observation Model

A schema for what can be recorded and compared, with explicit missingness, uncertainty, versioning, and evidence provenance. See [SPEC-001](specs/SPEC-001-Dynamic-UIERU-Observation-Model.md).

### Perspective Masking — proposed methodological framework

A family of operations that expose, filter, reweight, aggregate, or otherwise transform an observation or comparison according to a declared perspective. Different operator kinds have different semantics and cannot be conflated.

### Observational Projection / Field Mask

Selection or suppression of fields from already available data. It changes what is visible to the analyst, **not** the original system's behavior.

### Perspective Rescoring

Recomputation of a valuation using an alternative declared scoring perspective on available evidence. It is not evidence that a deployed system would have chosen differently.

### Replay

Re-execution or deterministic reconstruction under specified inputs, snapshots, and environment assumptions. Reproducibility is conditional on how much state and nondeterminism are controlled.

### Simulation

Evaluation using an explicit surrogate or generative model of system behavior. Simulation outcomes are model-dependent and are not direct measurements of the target system.

### Intervention — established causal concept

A deliberate modification of a variable or operating condition in the target system, subject to experimental design and governance. Interventional claims require stronger evidence than observational differences.

### Counterfactual Estimate — established causal concept, local application proposed

An estimate of what would have happened under an alternative condition that was not observed. It requires identification assumptions or a validated model and must not be labeled as observed fact.

### Masking Algebra — proposed formalization

A study of operators on views, observations, and interventions and their conditional properties (e.g., idempotence, commutativity, information refinement, and query preservation). **No general algebraic laws are assumed without specifying operator types and domains.** See [RELAY-001](research-relay/RELAY-001-Perspective-Masking-Algebra.md).

### Provenance

Traceable origin and transformation history of data, claims, comparisons, or artifacts, including relevant timestamps, versions, methods, and authority boundaries.

### Evidence Boundary

The set of conditions, observations, assumptions, and uncertainties within which a claim is supported. Evidence outside that boundary may require a new validation effort.

## 4. Dynamic differentials, trees, and queries

### Dynamic Differential — project-defined

A structured comparison of two or more states, units, runs, or perspectives under an **explicit comparison contract**. Differences without comparable conditions can be descriptive but not necessarily interpretable.

### Scoring Differential

Difference in valuation or scoring under specified inputs and perspective semantics. It does not by itself imply a changed decision.

### Decision Differential

Difference in selected action, route, or option under specified constraints. Identical decisions may arise from different scores; different decisions need not produce different realized outcomes.

### Trajectory Differential

Difference in observed or modeled sequences of states, actions, and outcomes across a time horizon. Trajectory differences can reflect environment changes as well as policy changes.

### Learning Differential

Difference attributable, under a stated identification method, to learning or update processes. A change across time is not sufficient evidence of learning; context drift and measurement artifacts are alternatives.

### Perspective Differential Tree (PDT) — proposed structure

A hierarchical index of conditional differences across perspectives, contexts, time scales, behaviors, and structures. Its branches may store evidence, uncertainty, provenance, and invalidation conditions. It is a proposed organization and retrieval structure, not an established optimal index.

### Perspective-Aware Structural Query (PASQ) — proposed interface

A query approach that makes perspective, comparison conditions, evidence, provenance, and differential type first-class parts of structural retrieval. PASQ can be implemented with SQL or other query systems; **PASQ is not an existing SQL standard**.

### Query Preservation

The property that a specified query yields equivalent relevant results before and after an allowed transformation. Whether it holds depends on the query language, masking operator, and chosen equivalence notion.

### Comparison Contract

An explicit declaration of units, task distribution, perspective, context, history, observation window, metrics, tolerances, evidence sources, and validity conditions governing a comparison. See [SPEC-003](specs/SPEC-003-Dynamic-Differential-and-Query-Schema.md).

## 5. Equivalence, substitution, and composition

### Behavioral Equivalence — established family of ideas, project-specific application

A relation asserting that two systems are indistinguishable with respect to specified observable behavior and conditions. It does **not** imply identical internal implementation.

### Dynamic Behavioral Equivalence — proposed conditional relation

Behavioral equivalence assessed over state transitions, trajectories, histories, and possibly updates under declared perspectives and contexts. The strength of the relation must be specified: finite-sample agreement, distributional similarity, bisimulation, or contract-level substitutability are different claims.

### Approximate Bisimulation — established formal-methods concept

A relation between state-transition systems requiring sufficiently similar observations and matching transitions within a defined tolerance or metric. Its application to UIERUs is a **research proposal**, and suitable state abstractions and error bounds remain open.

### Conditional Equivalence

An equivalence or similarity claim limited to a task family, context set, perspective, horizon, tolerance, and evidence base. It may be revoked if those conditions cease to hold.

### Substitutability / Relay Substitution

The ability to replace one unit with another while preserving specified external contracts and system-level properties. Similar benchmark scores alone do not establish substitutability.

### Interface Compatibility

Agreement on input/output structure, types, protocol, or capability signatures. It is weaker than behavioral equivalence or safe substitution.

### Contract Preservation

Continued satisfaction of a declared set of obligations after composition, replacement, or evolution. This may require runtime monitoring, testing, or formal proof depending on the claim.

### Assume–Guarantee Reasoning — established formal method

A compositional technique in which component guarantees are established under explicit environmental assumptions. Its use for dynamic intelligence units requires attention to feedback loops, state changes, and evolving assumptions.

### Relay — project-defined broad abstraction

Transfer, invocation, composition, or transformation of intelligence capabilities, tasks, evidence, control, or research state across boundaries. **Relay is not merely a network message**; it can include structured handoff and integration.

### Relay Composition

Organization of multiple units into a larger workflow or system under interface, perspective, contract, resource, and governance constraints. Local competence does not guarantee global correctness.

### Relay Graph

A directed or otherwise structured representation of units and their invocation, information, evidence, or control relations. A graph edge may have semantics beyond simple data flow.

### Two-Way CCC — project-defined

A bidirectional consistency/constraint and counter-evidence exchange mechanism in which requirements and evidence may propagate forward, while failures, contradictions, and corrective signals propagate backward. **CCC** belongs to the project's prior structural-intelligence vocabulary; its exact expansion and schema should follow the referenced upstream work rather than be guessed from the acronym.

### Emergent System-Level Behavior

A property arising from interaction among units that is not trivially inferred from individual unit performance. The term does not imply inexplicability; the goal is to identify composition mechanisms and testable conditions.

## 6. Evolution, learning, and governance

### Open Structural Evolution — proposed research program

Continual discovery, evaluation, composition, revision, and retirement of intelligence structures without presuming a fixed, exhaustive catalogue of possible units. **Open** does not mean unrestricted self-modification.

### Evolution Operator

A declared structural transformation such as ADD, REPLACE, COMPOSE, SPLIT, MERGE, REWIRE, REWEIGHT, LOCALIZE, IMPORT, RETIRE, or FORK. Operators require preconditions, postconditions, and evidence of contract effects.

### Evolution History / Lineage

A versioned record connecting predecessor and successor structures, proposed changes, tests, approvals, regressions, and reasons for adoption or rollback.

### Recursive Self-Improvement (RSI) — established research direction

A system's iterative improvement of its own components, methods, or capabilities, potentially including mechanisms that improve future improvement. Not all learning is RSI, and RSI does not inherently require LLMs.

### RSI–UIERU Convergence — proposed research hypothesis

The possibility that LLM-agent or other RSI systems can be observed, compared, composed, or governed through UIERU-like structural interfaces, while RSI methods generate candidate structural changes for UIERU systems. Functional resemblance does not establish architectural identity.

### Evaluator Governance

Controls over who defines evaluation objectives, what evidence is admitted, how evaluators are updated, and how disagreements or regressions are handled.

### Anti-Goodhart — established concern, local governance usage

Measures intended to prevent optimization of a proxy score from displacing the underlying objective. Examples include independent validation metrics, counter-evidence, distribution-shift testing, and explicit authority to reject a candidate change.

### Counter-Evidence

An observation, proof, counterexample, negative result, or competing explanation that weakens or refutes a claim within its asserted scope. Counter-evidence is a first-class research artifact, not merely a review comment.

### Adversarial Sandbox

A controlled test environment for challenging proposed changes, including conflicting objectives, distribution shifts, malicious inputs, and failure injection. Sandbox success does not automatically imply deployment safety.

### Structural Interpretability

The ability to inspect system-level routing, perspective choice, contracts, evidence, and structural updates. It differs from **model interpretability**, which seeks to explain the internal computation of an opaque model. UIERU aspires to improve the former but does not automatically solve the latter.

### Governance Invariant

A condition intended to remain true through execution, composition, and evolution—for example, a permission boundary or evidence-retention obligation. Whether it can be proved or only monitored depends on system design.

## 7. Biological intelligence and cross-disciplinary research

### Dynamic Organizational Biomimicry — proposed research approach

Learning from context-sensitive, adaptive, distributed biological organization rather than asserting direct one-to-one correspondence between artificial modules and anatomical brain structures.

### Dynamic Functional Boundary

A context- or task-dependent boundary around a coordinated functional process. It is a modeling hypothesis that may or may not correspond to stable anatomical partitions.

### Dynamic Functional Coalition — proposed biological model class

A temporarily coordinated collection of neural or functional components whose participation changes with context and task. It competes with fixed-module and reweighted-network explanations and requires empirical discrimination.

### Context-Dependent Valuation

A process in which action values or preferences vary with internal state, environmental conditions, goals, or history. Similar outward behavior does not prove identical valuation mechanisms.

### Identifiability — established statistical concept

Whether a model parameter or causal mechanism can be distinguished from alternatives using available observations and assumptions. Behavioral data alone may not identify the neural implementation of a proposed UIERU-like process.

### Causal Intervention

An experiment designed to alter a target mechanism or condition and observe resulting effects. In neuroscience, intervention feasibility and specificity limit the strength of causal inference.

### Cross-Disciplinary Analogy

A proposed mapping between concepts from different fields that can suggest hypotheses but does not establish mechanistic equivalence. The mapping should record where it fails.

## 8. Open Research Relay vocabulary

### Open Research Relay — project-defined

A framework for transferring unresolved problems, formal models, assumptions, evidence, counter-evidence, validation obligations, and collaboration interfaces so independent researchers can extend or challenge the work.

### Research Relay Piece (RRP) — project-defined

A portable, versioned research object with six core fields: **Problem (P), Model (M), Hypotheses (H), Evidence (E), Validation (V), Interfaces (I)**, plus optional or extended **Governance (G)** and **Lineage (L)**. A compact representation is

\[
R = (P,M,H,E,V,I;G,L).
\]

The notation describes a contract shape, not a theorem about research processes. See [SPEC-004](specs/SPEC-004-Research-Relay-Piece-Contract.md).

### Research Handoff

A documented transfer of a research question and sufficient context for an independent contributor to evaluate or continue it, including assumptions and outstanding failure conditions.

### Epistemic Status

The classification of a statement as definition, assumption, conjecture, proved result, empirical hypothesis, observation, simulation, analogy, or unresolved question. Different statuses require different evidence standards.

### Proof Obligation

A mathematical claim whose premises, conclusion, and permitted inference rules must be established. A candidate proposition is not a proved theorem.

### Falsifiable Hypothesis

An empirical claim with observable outcomes that could count against it, under a specified protocol and scope. An illustrative benchmark result is not a validation result unless independently measured.

### Negative Result

A reproducible failure, non-improvement, impossibility result, or unsupported hypothesis. Negative results can advance Research Relay when their conditions and provenance are preserved.

### Conformance

Satisfaction of the explicitly enumerated requirements of a proposed specification at a named level. Conformance to a record format does not certify the truth of the claims recorded.

### Reproducibility / Replicability

**Reproducibility** generally concerns obtaining consistent results with specified data, methods, and computational conditions; **replicability** concerns independent evidence from a distinct study. Terminology varies by field and should be defined in each protocol.

### Research Lineage

Versioned relationships among research questions, models, evidence, revisions, refutations, and derived works, preserving attribution and the conditions under which claims changed.

### Research Collaboration Contract

An explicit agreement about scope, methods, artifacts, provenance, permissions, review, credit, and update pathways. See [RESEARCH-COLLABORATION](research-relay/RESEARCH-COLLABORATION.md).

## 9. Distinctions that must not be collapsed

| Distinction | Why it matters |
|---|---|
| Observation vs. explanation | A visible trace does not identify its generating mechanism. |
| Projection vs. intervention | Hiding fields does not alter the deployed system. |
| Simulation vs. measured outcome | Simulated results inherit assumptions from the model. |
| Scoring vs. decision | Different scores may lead to the same action. |
| Decision vs. trajectory | Environment and execution can change realized outcomes. |
| Trajectory change vs. learning | Drift can arise without adaptation. |
| Interface compatibility vs. behavioral equivalence | Matching schemas do not guarantee matching behavior. |
| Behavioral equivalence vs. contract substitutability | Local similarity does not guarantee system safety. |
| Local guarantee vs. global guarantee | Composition can introduce new failure modes. |
| Structural interpretability vs. model interpretability | Auditable routing does not explain all internal neural computation. |
| Biological analogy vs. neural mechanism | Similar functional organization is not proof of anatomical correspondence. |
| Candidate theorem vs. proved theorem | A formal proposal requires proof or a counterexample. |
| Synthetic example vs. empirical evidence | Illustrations cannot establish performance claims. |
| Repeated execution vs. structural evolution | Accumulated traces are not automatically validated improvements. |
| Open evolution vs. unrestricted modification | Growth must respect contracts, safety, and governance. |
| Research artifact transfer vs. Research Relay | The latter includes assumptions, contestability, and validation paths. |

## 10. Abbreviations and cross-references

| Abbreviation | Expansion / meaning | Status |
|---|---|---|
| BUI-DSI | Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay | Project name |
| SI | Structural Intelligence | Project research family |
| DSI | Dynamic Structural Intelligence | Project-defined |
| UIERU | Universal Intelligence Evolution and Relay Unit | Project-defined |
| MDT | Metric Differential Tree | Prior SI work |
| UTN | Universal Type/Name or related prior-project UTN terminology; consult source repository for its exact canonical expansion | Prior SI work; expansion to verify |
| CCC | Prior SI consistency/counter-evidence coordination terminology; consult source documents for exact expansion | Prior SI work |
| PDT | Perspective Differential Tree | Proposed |
| PASQ | Perspective-Aware Structural Query | Proposed |
| RRP | Research Relay Piece | Proposed |
| RSI | Recursive Self-Improvement | Established research direction |
| LLM | Large Language Model | Established |
| MET | Minimum experimental test / minimal experimental testing (local shorthand; define explicitly in each protocol) | Working shorthand |
| SQL | Structured Query Language | Established |
| API | Application Programming Interface | Established |

**Terminology caution:** Acronyms inherited from upstream SI repositories should be checked against their original definitions before release. This glossary avoids asserting uncertain expansions as authoritative.

## 11. Primary document map

- **Conceptual foundations:** [BUI-001](docs/BUI-001-From-Static-Structural-Intelligence-to-Dynamic-Intelligence-Units.md) through [BUI-008](docs/BUI-008-Open-Research-Relay-and-the-Next-Horizon-of-Structural-Intelligence.md).
- **Operational examples:** [CASE-001](cases/CASE-001-Perspective-Masked-Model-Selection.md), [CASE-002](cases/CASE-002-Dynamic-Equivalence-and-Relay-Substitution.md), [CASE-003](cases/CASE-003-Context-Dependent-Biological-Intelligence.md).
- **Formal open problems:** [RELAY-001](research-relay/RELAY-001-Perspective-Masking-Algebra.md), [RELAY-002](research-relay/RELAY-002-Dynamic-Behavioral-Equivalence.md), [RELAY-003](research-relay/RELAY-003-Relay-Composition-and-Contracts.md).
- **Biological and evolution questions:** [RELAY-004](research-relay/RELAY-004-Biological-Dynamic-Intelligence.md), [RELAY-005](research-relay/RELAY-005-Open-Structural-Evolution.md).
- **Collaboration:** [RESEARCH-COLLABORATION](research-relay/RESEARCH-COLLABORATION.md).
- **Interoperability:** [SPEC-001](specs/SPEC-001-Dynamic-UIERU-Observation-Model.md), [SPEC-002](specs/SPEC-002-Perspective-Masking-Contract.md), [SPEC-003](specs/SPEC-003-Dynamic-Differential-and-Query-Schema.md), [SPEC-004](specs/SPEC-004-Research-Relay-Piece-Contract.md).

## 12. Maintenance and contribution rules

1. Define a new term at first use in a paper and add it here if reused across documents.
2. Label project-defined terms and proposed mathematical constructs; do not present them as established community standards.
3. State scope and evidence conditions for equivalence, causality, learning, and evolution claims.
4. Preserve original meanings when citing established disciplines; explicitly identify any local specialization.
5. Track renamed terms and schema migrations in [CHANGELOG](CHANGELOG.md) when available.
6. Accept corrections, counterexamples, and alternative definitions through the procedures in [RESEARCH-COLLABORATION](research-relay/RESEARCH-COLLABORATION.md).

---

**Citation / attribution:** Sizhe Tan & GPT-Obot, *Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay*, working glossary, v1.0.0 (2026). This document provides research terminology and does not certify experimental or formal claims.

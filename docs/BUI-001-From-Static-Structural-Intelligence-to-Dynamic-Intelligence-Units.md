# BUI-001 — From Static Structural Intelligence to Dynamic Intelligence Units

**Project:** Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay (BUI-DSI)  
**Authors:** Sizhe Tan & GPT-Obot  
**Version:** 1.0.0 — Research proposal  
**Date:** 2026-10-21  
**Status:** Open research agenda; conceptual framework, not a validated universal theory

## Abstract

Structural Intelligence (SI) research has progressively shifted its engineering focus from relatively static representations—such as differential trees, context-sensitive triggers, localization indexes, and calling graphs—toward portable, composable, evaluative, and evolving intelligence systems. The Universal Intelligence Evolution and Relay Unit (UIERU) marks a further conceptual transition: an intelligence unit is treated not merely as a stored capability or callable component but as a potentially stateful process integrating perspective-sensitive valuation, selection, action, feedback, relay, and structural adaptation. This paper defines the transition, distinguishes structural identity from dynamic behavior, identifies the limits of transferring static localization tools to dynamic units, and proposes a research agenda based on perspective masking, differential observation, queryable traces, behavioral equivalence, and compositional verification. It also situates UIERU-like models relative to biological intelligence without claiming neural identity. The goal is to publish a precise, falsifiable, reusable research entry point—not to claim that the mathematics or biology of dynamic structural intelligence has already been solved.

**Keywords:** Structural Intelligence; UIERU; dynamic intelligence units; perspective masking; scoring forest; localization; structural relay; behavioral equivalence; open research relay; mathematical foundations; biological intelligence

---

![Fig-001-BUI-DSI-Grand-Research-Map.png](../figures/Fig-001-BUI-DSI-Grand-Research-Map.png)

---

![Fig-002-From-Static-SI-to-Dynamic-UIERU.png](../figures/Fig-002-From-Static-SI-to-Dynamic-UIERU.png)

---

## 1. Introduction: A Change in the Research Object

Early SI work could often isolate a structure and ask how to represent, search, score, compose, or refine it. A metric differential tree, a context-bound trigger, a universal tree node, or a calling graph can be studied as a relatively stable artifact, even if it participates in a changing runtime. This decomposition is productive: explicit interfaces and local experiments make engineering questions tractable.

Yet the intelligence of an operating system cannot always be reduced to the inventory of its parts. A capable unit may evaluate competing actions differently as objectives change, alter its decisions after feedback, transfer work to other units, and reorganize its own internal mechanisms. Its relevant behavior is then inseparable from perspective, context, environment, and history.

UIERU is proposed as a useful organizational abstraction for this dynamic regime. The claim is **not** that every intelligence system contains a natural, unique UIERU, or that UIERU is the final granularity of intelligence. Rather, UIERU gives researchers a candidate unit at which structural components and adaptive processes can be examined together.

The next challenge is methodological: how can such units be observed, localized, compared, queried, substituted, composed, and improved without requiring complete access to every internal mechanism?

## 2. Research Lineage: From Structural Components to Open Systems

The following lineage records a research motivation, not a claim of exclusive priority over adjacent work in computer science or neuroscience.

| Research layer | Representative SI concepts | Principal question |
|---|---|---|
| Structural representation | Metric Differential Tree (MDT), Calling Graph, Context-Bound Trigger (CBT), CCC | What differences, dependencies, and conditions can be represented explicitly? |
| Localization and per-node capability | Universal Tree Node (UTN), per-node intelligence | Where is the relevant capability, and how can it be invoked? |
| Portability and relay | PIRP/PIRU, contracts, naming and type interfaces | How can intelligence pieces be moved, reused, and combined? |
| Evaluation and control | UCPSF, scoring trees and forests, control planes | How are alternatives evaluated and selected from a perspective? |
| Open structural organization | Structural Intelligence Framework (SIF), dual maps, precedent registries, counter-evidence | How can an ecosystem discover, govern, and grow capabilities? |
| Dynamic unit organization | UIERU | How can evaluation, action, feedback, relay, and evolution operate as a coherent unit? |
| Post-UIERU research | BUI-DSI | How can changing units themselves become tractable research objects? |

These layers overlap; they are not mutually exclusive historical eras. Static representations remain essential inside dynamic systems. The transition concerns the **dominant object of analysis**, not the disappearance of prior methods.

## 3. A Minimal Dynamic UIERU Model

A useful first model separates a unit's relatively persistent specification from its changing state and behavior.

Let

\[
U = (K, X, \mathcal{P}, \mathcal{A}, \mathcal{R}, F, G, \Gamma),
\]

where:

- \(K\) is a structural core: capabilities, interfaces, contracts, and internal organization;
- \(X\) is the state space, including memory and other historical variables;
- \(\mathcal{P}\) is a set of possible perspectives or valuation configurations;
- \(\mathcal{A}\) is the action and delegation space;
- \(\mathcal{R}\) is the space of relay relationships and messages;
- \(F\) is a state-transition mechanism;
- \(G\) is an observation and decision mechanism, potentially using scoring forests;
- \(\Gamma\) is a family of permitted adaptation or structural-update operations.

At step \(t\), a simplified operational view is

\[
(a_t, y_t) = G(K_t, x_t, p_t, c_t, e_t),
\]

\[
(x_{t+1}, K_{t+1}) = F_{\Gamma}(K_t, x_t, a_t, y_t, r_t, e_t),
\]

where \(p_t\) denotes perspective, \(c_t\) context, \(e_t\) environment, \(r_t\) relay input/output, and \(y_t\) an observable outcome or trace. The equations are schematic; they do not imply that all implementations expose these variables or evolve on discrete time steps.

### 3.1 What makes the unit dynamic?

A UIERU-like unit is dynamic when at least one of the following changes materially with operation: internal state, valuation or policy, selected action, relay relationships, or the structural core itself. **Dynamic behavior** and **structural evolution** must not be conflated: a fixed architecture can produce complex state-dependent behavior, while structural evolution changes the architecture or its explicit components.

### 3.2 Why scoring forests matter—but are not the whole story

Scoring trees or forests provide a candidate mechanism for multi-criteria evaluation and selection. However, dynamic intelligence also depends on state transitions, feedback, environmental coupling, and relay. Masking a scoring forest may simplify observation, but it does not necessarily eliminate all dynamics. Nor is a scoring forest presumed to be the only possible valuation implementation.

## 4. From Static Localization to Dynamic Localization

SIF-style localization can often index stable capabilities, names, types, contracts, and structural precedents. These remain useful for UIERU structural cores. Yet a dynamic search question may be different:

- Which unit is capable of a task **now**, under a specified perspective and context?
- Which unit remains reliable across a family of contexts?
- Which units are behaviorally similar despite dissimilar internal scoring mechanisms?
- Which unit can substitute for another without violating a relay contract?
- Which unit has changed in a way that invalidates an earlier localization result?

Thus a dynamic localization result should be associated with a **scope**—at minimum the tested perspective, context, environment, state or time window, and relevant evidence. An unqualified statement that two evolving units are equivalent is generally too strong.

## 5. Perspective Masking as an Observation Operator

A **perspective mask** is proposed as a controlled restriction or projection of the features, objectives, observations, or conditions considered in an analysis. The term does not by itself specify whether a system is merely observed through a filtered view or actually executed under a modified policy.

We distinguish:

1. **Observational masking:** project an existing record or model without changing the underlying run.
2. **Interventional masking:** modify available perspectives, scoring components, or information during execution.
3. **Counterfactual masking:** estimate what might have happened under conditions not actually executed.

These three cases have different evidentiary requirements and must not be mixed.

Other useful restrictions include structural masks, scoring masks, temporal masks, evolution masks, and interaction masks. A mask should record its scope, transformation, provenance, and known losses of information.

### 5.1 A mathematical question, not an assumed law

For masks \(M_P\) and \(M_Q\), one may ask whether

\[
M_P(M_Q(U)) = M_{P\cap Q}(U).
\]

This equality can hold for suitable pure projections. It need not hold for interventions that alter actions or state. Idempotence, commutativity, associativity, and behavior preservation are **candidate properties to investigate**, not established UIERU theorems.

## 6. Differential Trees for Dynamic Behavior

Traditional structural differences can be extended into three distinguishable families:

**Scoring differential.** Given comparable runs under perspectives \(p_i\) and \(p_j\), compare normalized or calibrated valuation outputs. Raw score subtraction is not meaningful when scoring scales differ.

**Decision differential.** Compare selected actions, delegation choices, or policies. Different scores can yield the same action; similar scores can yield different actions near a decision boundary.

**Trajectory differential.** Compare sequences of states, actions, relay messages, feedback, and updates. Trajectory differences may compound over time and are sensitive to environmental variation.

A **Perspective Differential Tree** could organize shared conditions at its trunk and explainable divergences at its branches. Such a tree is a proposed representation, not a proof that differences have unique causal explanations. Controlled experiments and counter-evidence are needed to distinguish causal effects from correlations.

## 7. Perspective-Aware Structural Query

A practical route to dynamic localization is to retain mature database and query technologies while adding explicit perspective, state, time, provenance, and trace semantics.

A conceptual query can be written as

\[
Q(U,p,c,e,h,m),
\]

where \(m\) identifies the mask and \(h\) identifies relevant history or a bounded history representation.

A minimal record schema might contain:

```text
unit_id | unit_version | task_id | context_id | perspective_id
state_ref | environment_ref | mask_id | timestamp | action_id
score_schema | selected_capability | outcome_ref | trace_ref
contract_ref | evidence_provenance
```

This schema supports reproducible questions such as: Which units changed action under a perspective switch? Which versions violated a contract after adaptation? Which traces exhibit similar decision patterns?

Ordinary SQL can query **recorded** behavior; counterfactual behavior requires additional models, simulation, or intervention. This distinction is fundamental.

## 8. Dynamic Equivalence and Relay Composition

For a bounded family of contexts \(\mathcal C\), perspectives \(\mathcal P\), and a specified observation metric \(d\), one may propose

\[
U_i \approx_{\mathcal P,\mathcal C,\varepsilon} U_j
\]

when their relevant observed behaviors differ by no more than \(\varepsilon\) under a stated protocol. The definition is incomplete until the behavior space, sampling regime, metric, time horizon, and confidence criteria are fixed.

Possible levels of equivalence include output, decision, trace, probabilistic, and contextual or compositional equivalence. Formal methods such as bisimulation and approximate simulation offer important prior art to investigate; UIERU does not automatically require inventing a new equivalence theory.

Relay introduces a further challenge. Even if two units are locally similar, substituting one inside a larger system can change feedback loops, resource usage, timing, or safety properties. Contract compatibility and compositional verification therefore belong alongside behavioral similarity.

## 9. Beyond Fixed Unit Boundaries

A further open question concerns whether UIERU boundaries should be fixed. Some systems may dynamically form functional groups based on tasks, available capabilities, contexts, and relay relationships. This motivates research on **Dynamic Intelligence Relationships** and emerging functional units.

Candidate relationship types include cooperation, competition, dependency, substitution, delegation, shared evaluation, and collective learning. A system-level intelligence property may depend on the topology and evolution of these relations rather than solely on individual unit capability.

This suggests that the next useful research granularity after UIERU may be a **dynamic relation or interaction process**, not necessarily a larger static container.

## 10. Biological Intelligence: Functional Analogy, Not Neural Identification

Animal nervous systems demonstrate context-dependent behavior, value-sensitive action selection, distributed processing, plasticity, and learning from feedback. These phenomena motivate UIERU-like computational abstractions. They do **not** establish that the brain contains literal scoring forests, UIERU contracts, or fixed UIERU anatomical modules.

Two complementary hypotheses merit study:

- **Organizational analogy:** some biological intelligence functions can be usefully modeled as interacting, stateful evaluation–action–learning processes.
- **Emergent boundaries:** functionally coherent intelligence units may form dynamically rather than correspond to fixed anatomical compartments.

Both require engagement with computational neuroscience and carefully designed empirical comparisons. A good engineering analogy is not itself biological evidence.

## 11. Mathematical Foundations and External Research Interfaces

The move from static structure to dynamic units creates research questions well suited to collaboration with mathematics, theoretical computer science, control, formal verification, database theory, and computational neuroscience.

| Research interface | Initial formal question | Candidate prior-art families |
|---|---|---|
| Masking algebra | Under which assumptions do masks commute, compose, or preserve properties? | Algebra of projections; program semantics |
| Behavioral equivalence | What observable equivalence survives state changes and adaptation? | Bisimulation; probabilistic transition systems |
| Relay composition | When do local contracts imply system-level guarantees? | Assume–guarantee reasoning; compositional verification |
| Dynamic localization | How can a query index stateful, context-dependent behavior? | Temporal databases; provenance; event sourcing |
| Open evolution | Which invariants survive structural updates? | Dynamic systems; runtime verification; adaptive control |
| Biological organization | Which functional abstractions predict measurable behavior? | Computational neuroscience; learning and control |

A research relay should expose **small, independently tractable problems**, not demand that a collaborator adopt the entire SI vocabulary. The value of external participation includes counterexamples, impossibility results, alternative models, and rediscovery of relevant established theories.

## 12. Open Research Relay: Why Publish Before the Problem Is Solved?

The purpose of BUI-DSI is to preserve and share an emerging research horizon. A useful open research piece should contain:

- a precisely bounded problem and motivation;
- minimal assumptions and formal objects;
- explicit separation of observations, proposals, and hypotheses;
- links to related theories and prior work;
- test cases, possible counterexamples, and validation criteria;
- interfaces for independent extension, critique, and reuse.

This turns research itself into a relayable structural activity. It does not assert scientific priority simply because a particular SI development path revealed a question. Novelty and overlap must be assessed against the wider literature.

## 13. Testable Hypotheses and Failure Modes

**H1 — Scoped localization:** Adding perspective, state, and provenance to structural indexes improves the reproducibility of dynamic-unit retrieval relative to capability-only indexes on specified benchmark tasks.

**H2 — Differential compression:** Under controlled tasks, a perspective differential tree can represent important behavior divergences more compactly than unstructured trace comparison while preserving specified diagnostic information.

**H3 — Query utility:** A perspective-aware query schema supports useful cross-run analyses without requiring a new general-purpose query language.

**H4 — Conditional substitutability:** A behaviorally similar unit can replace another within a bounded relay contract under identifiable conditions; counterexamples reveal when similarity is insufficient.

**H5 — Biological explanatory value:** A carefully specified UIERU-like model predicts some context-dependent biological behaviors better than an appropriate simpler baseline; failure would narrow or reject the analogy.

Potential failure modes include confounded perspective comparisons, incompatible score scales, incomplete history, mask-induced changes in the system, hidden relay dependencies, unstable unit identity, and models so simplified that they omit open-ended evolution.

## 14. Validation Roadmap

**Stage A — Define.** Specify minimal dynamic-unit semantics, masking types, trace schema, and comparison contracts.

**Stage B — Reproduce.** Build a small controlled model-selection case with multiple perspectives and repeated trials; record full provenance.

**Stage C — Differentiate.** Compare scoring, decisions, and trajectories under observational and interventional masks; explicitly test whether purported algebraic properties fail.

**Stage D — Query.** Implement relational queries over recorded traces; measure retrieval utility and reproducibility against static indexing baselines.

**Stage E — Compose.** Test substitution and relay contracts; deliberately search for counterexamples where local equivalence fails to preserve system properties.

**Stage F — Generalize.** Evaluate more heterogeneous units, adaptation mechanisms, and biological analogies with external domain expertise.

The roadmap is an invitation to future validation; no experimental outcomes are claimed here.

## 15. Conclusions

UIERU motivates a consequential change in the granularity of Structural Intelligence research: from examining relatively stable structures and capabilities to examining units whose behavior depends on valuation, context, history, feedback, relay, and adaptation. Static SI tools remain useful, but dynamic behavior introduces new requirements for observation, localization, comparison, query, equivalence, and composition.

The immediate research opportunity is a tractable sequence:

**Perspective Masking → Dynamic Differentials → Perspective-Aware Query → Scoped Equivalence → Verified Relay Composition → Open Evolution.**

The long-term opportunity is broader: to connect structural intelligence engineering with mathematical foundations and biological intelligence while keeping assumptions, evidence, and counter-evidence explicit.

**This work does not claim that dynamic structural intelligence has been solved. It aims to make its emerging problems visible, structured, testable, and openly relayable.**

## 16. Research Status and Citation Guidance

This document is a conceptual research proposal within the BUI-DSI series. Equations define candidate abstractions rather than experimentally established universal laws. Proposed mechanisms such as Perspective Differential Trees and Perspective-Aware Structural Query require independent implementation and validation. Biological comparisons are hypotheses at the functional level, not claims of neural identity.

For scholarly reuse, cite the versioned BUI-DSI repository release and its DOI once assigned. Do not invent a DOI before registration. Preserve attribution to **Sizhe Tan & GPT-Obot**, while independently checking applicable publisher and repository policies on AI-assisted authorship and disclosure.

## Related SI Research Lineage

- Structural Intelligence Framework (SIF): https://github.com/sizhet/Structural-Intelligence-Framework
- Universal Intelligence Evolution and Relay Unit (UIERU): https://github.com/sizhet/Universal-Intelligence-Evolution-and-Relay-Unit
- Universal Control Planes and Scoring Folding (UCPSF): https://github.com/sizhet/Universal-Control-Planes-and-Scoring-Folding
- Subjective Structural Intelligence (SSI): https://github.com/sizhet/Subjective-Structural-Intelligence

These links provide project context, not independent empirical validation.

## Selected Foundational Literature to Investigate

- Milner, R. (1989). *Communication and Concurrency*. Prentice Hall. [Process semantics and behavioral equivalence.]
- Baier, C., & Katoen, J.-P. (2008). *Principles of Model Checking*. MIT Press. [Transition systems and verification.]
- Alur, R., & Henzinger, T. A. (1992). Logics and models of real time: A survey. In *Real-Time: Theory in Practice*. [Temporal and state-based reasoning.]
- Sutton, R. S., & Barto, A. G. (2018). *Reinforcement Learning: An Introduction*, 2nd ed. MIT Press. [Sequential decision-making and learning.]
- Vyas, S., Golub, M. D., Sussillo, D., & Shenoy, K. V. (2020). Computation through neural population dynamics. *Annual Review of Neuroscience*, 43, 249–275. https://doi.org/10.1146/annurev-neuro-092619-094115

The literature above identifies adjacent foundations; it is not a systematic novelty review. A later release should add focused surveys for masking, provenance, context-dependent neural computation, and compositional contracts.

---

*BUI-001 · BUI-DSI v1.0.0 · Sizhe Tan & GPT-Obot · 2026-10-21*

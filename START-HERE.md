# START HERE — Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay

**BUI-DSI · v1.0.0 · Reader's guide and research entry points**  
**Authors:** Sizhe Tan & GPT-Obot  
**Date:** 2026-10-25  
**Status:** Open research agenda; candidate models and proposed interfaces, not an established general theory.

> **Begin with the research question, choose a perspective, and follow the evidence.**

## 1. What is this repository?

**Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay (BUI-DSI)** investigates how intelligence units can be **observed, compared, queried, substituted, composed, and studied as they change** with context, perspective, feedback, and history. It extends the Structural Intelligence (SI) research trajectory and the **Universal Intelligence Evolution and Relay Unit (UIERU)** proposal.

The repository also develops **Open Research Relay**: a method of handing off *researchable problems*—including assumptions, candidate definitions, hypotheses, evidence, counter-evidence, validation procedures, and provenance—to other researchers.

This is primarily a **research and specification repository**, not a packaged software implementation. Examples and schemas are proposals and illustrative artifacts; a diagram is not proof, and a synthetic case is not empirical validation.

## 2. The five-minute route

If you have limited time, read these in order:

1. **[README.md](README.md)** — research thesis, architecture, and complete document map.
2. **[BUI-001 — From Static Structural Intelligence to Dynamic Intelligence Units](docs/BUI-001-From-Static-Structural-Intelligence-to-Dynamic-Intelligence-Units.md)** — why dynamic units change the research problem.
3. **[BUI-002 — Perspective Masking and Dynamic Structural Observation](docs/BUI-002-Perspective-Masking-and-Dynamic-Structural-Observation.md)** — what a perspective-dependent observation means.
4. **[BUI-008 — Open Research Relay and the Next Horizon of Structural Intelligence](docs/BUI-008-Open-Research-Relay-and-the-Next-Horizon-of-Structural-Intelligence.md)** — why unresolved problems should be relayable research artifacts.
5. **[RESEARCH-COLLABORATION.md](research-relay/RESEARCH-COLLABORATION.md)** — how to test, challenge, and extend the proposals.

**One-sentence thesis:** Dynamic intelligence needs explicit *observation conditions*, *comparison contracts*, *composition boundaries*, and *evidence-governed evolution*.

## 3. The central conceptual chain

```text
Context + Perspective + History
              |
              v
   Dynamic UIERU Observation         [SPEC-001]
              |
              v
      Perspective Masking            [BUI-002, SPEC-002]
              |
              v
  Differential Analysis / PDT        [BUI-003]
              |
              v
   Structural Query / PASQ           [BUI-004, SPEC-003]
              |
              v
 Dynamic Equivalence + Substitution  [BUI-005, RELAY-002]
              |
              v
 Relay Composition + Contracts       [RELAY-003]
              |
              v
   Open Structural Evolution         [RELAY-005]
              |
              v
   Open Research Relay / RRP         [BUI-008, SPEC-004]
              ^
              |
    Counter-evidence and revision
```

This is a **reading map**, not a claim that every research system must implement the same pipeline or that all arrows have been formally verified.

## 4. Choose your research background

### 4.1 Mathematics, theoretical computer science, and formal methods

**Question:** Which proposed relations can be defined precisely, proved, refuted, or bounded?

Recommended sequence:

1. [BUI-006 — Mathematical Foundations and Open Formal Problems](docs/BUI-006-Mathematical-Foundations-and-Open-Formal-Problems.md)
2. [RELAY-001 — Perspective Masking Algebra](research-relay/RELAY-001-Perspective-Masking-Algebra.md)
3. [RELAY-002 — Dynamic Behavioral Equivalence](research-relay/RELAY-002-Dynamic-Behavioral-Equivalence.md)
4. [RELAY-003 — Relay Composition and Contracts](research-relay/RELAY-003-Relay-Composition-and-Contracts.md)
5. [SPEC-004 — Research Relay Piece Contract](specs/SPEC-004-Research-Relay-Piece-Contract.md)

Useful targets: conditional masking laws, approximate bisimulation, assume–guarantee composition, probabilistic contracts, evolution-aware invariants, and counterexample construction. **Do not assume candidate algebraic laws hold without stated preconditions.**

### 4.2 AI engineering, LLM agents, and RSI

**Question:** Can a changing agent system be observed, compared, and governed through explicit structural interfaces?

Recommended sequence:

1. [BUI-001 — Dynamic Intelligence Units](docs/BUI-001-From-Static-Structural-Intelligence-to-Dynamic-Intelligence-Units.md)
2. [CASE-001 — Perspective-Masked Model Selection](cases/CASE-001-Perspective-Masked-Model-Selection.md)
3. [CASE-002 — Dynamic Equivalence and Relay Substitution](cases/CASE-002-Dynamic-Equivalence-and-Relay-Substitution.md)
4. [SPEC-001 — Dynamic UIERU Observation Model](specs/SPEC-001-Dynamic-UIERU-Observation-Model.md)
5. [SPEC-002 — Perspective Masking Contract](specs/SPEC-002-Perspective-Masking-Contract.md)
6. [RELAY-005 — Open Structural Evolution](research-relay/RELAY-005-Open-Structural-Evolution.md)

A promising *proposed* interface is **RSI candidate generation → UIERU-like structural evaluation → governed selection and evolution**. RSI and UIERU are not asserted to be identical. Structural transparency of a wrapper does not establish interpretability of a model's internal computation.

### 4.3 Neuroscience, biology, and cognitive science

**Question:** Which dynamic-organizational analogies yield falsifiable hypotheses, and which are unsupported?

Recommended sequence:

1. [BUI-007 — Biological Intelligence and Dynamic Organizational Biomimicry](docs/BUI-007-Biological-Intelligence-and-Dynamic-Organizational-Biomimicry.md)
2. [CASE-003 — Context-Dependent Biological Intelligence](cases/CASE-003-Context-Dependent-Biological-Intelligence.md)
3. [RELAY-004 — Biological Dynamic Intelligence](research-relay/RELAY-004-Biological-Dynamic-Intelligence.md)
4. [BUI-002 — Perspective Masking](docs/BUI-002-Perspective-Masking-and-Dynamic-Structural-Observation.md)
5. [VALIDATION-ROADMAP.md](VALIDATION-ROADMAP.md) — planned repository navigation document.

**Boundary:** The repository does **not** claim that biological brains literally implement UIERUs, scoring forests, or its proposed contracts. Similar observable behavior does not imply identical mechanisms. Biological evidence must be able to reject a structural analogy.

### 4.4 Data systems, structural search, and database research

**Question:** How can dynamic observations and differentials be indexed and queried without losing their conditions?

Recommended sequence:

1. [BUI-003 — Perspective Differential Trees](docs/BUI-003-Perspective-Differential-Trees-and-Dynamic-Localization.md)
2. [BUI-004 — Perspective-Aware Structural Query and SQL](docs/BUI-004-Perspective-Aware-Structural-Query-and-SQL.md)
3. [SPEC-003 — Dynamic Differential and Query Schema](specs/SPEC-003-Dynamic-Differential-and-Query-Schema.md)
4. [CASE-001 — Perspective-Masked Model Selection](cases/CASE-001-Perspective-Masked-Model-Selection.md)

Key distinction: a scoring differential is not necessarily a decision differential; neither establishes a trajectory or learning differential. Comparisons require aligned contexts, histories, windows, and evidence.

### 4.5 Research collaboration, governance, and philosophy of intelligence

**Question:** How can claims, counterclaims, evidence, and research credit survive transfer across teams?

Recommended sequence:

1. [BUI-008 — Open Research Relay](docs/BUI-008-Open-Research-Relay-and-the-Next-Horizon-of-Structural-Intelligence.md)
2. [SPEC-004 — Research Relay Piece Contract](specs/SPEC-004-Research-Relay-Piece-Contract.md)
3. [RESEARCH-COLLABORATION.md](research-relay/RESEARCH-COLLABORATION.md)
4. [RELAY-005 — Open Structural Evolution](research-relay/RELAY-005-Open-Structural-Evolution.md)

## 5. The eight core papers: suggested progression

| Paper | Core question | Next useful document |
|---|---|---|
| [BUI-001](docs/BUI-001-From-Static-Structural-Intelligence-to-Dynamic-Intelligence-Units.md) | What makes an intelligence unit dynamic? | SPEC-001 |
| [BUI-002](docs/BUI-002-Perspective-Masking-and-Dynamic-Structural-Observation.md) | What changes under a perspective? | RELAY-001 |
| [BUI-003](docs/BUI-003-Perspective-Differential-Trees-and-Dynamic-Localization.md) | How are differences localized? | SPEC-003 |
| [BUI-004](docs/BUI-004-Perspective-Aware-Structural-Query-and-SQL.md) | How are those differences queried? | CASE-001 |
| [BUI-005](docs/BUI-005-Dynamic-Equivalence-Relay-Composition-and-Emergent-Relations.md) | When can units substitute or compose? | CASE-002 |
| [BUI-006](docs/BUI-006-Mathematical-Foundations-and-Open-Formal-Problems.md) | What needs formal proof? | RELAY-002/003 |
| [BUI-007](docs/BUI-007-Biological-Intelligence-and-Dynamic-Organizational-Biomimicry.md) | What can biological studies test? | CASE-003 |
| [BUI-008](docs/BUI-008-Open-Research-Relay-and-the-Next-Horizon-of-Structural-Intelligence.md) | How can research questions themselves be relayed? | SPEC-004 |

## 6. Three cases: learn by comparison

- **[CASE-001 — Perspective-Masked Model Selection](cases/CASE-001-Perspective-Masked-Model-Selection.md):** A synthetic LLM-selection example that separates score, decision, execution, and learning observations.
- **[CASE-002 — Dynamic Equivalence and Relay Substitution](cases/CASE-002-Dynamic-Equivalence-and-Relay-Substitution.md):** A contract-scoped replacement problem in which local similarity need not imply system-level equivalence.
- **[CASE-003 — Context-Dependent Biological Intelligence](cases/CASE-003-Context-Dependent-Biological-Intelligence.md):** Competing explanatory models for context-dependent behavior, without claiming anatomical or mechanistic identity.

**Evidence warning:** Synthetic examples clarify an interface; they are not empirical measurements or proof of feasibility.

## 7. Open Research Relay: select a problem track

| Track | Main research question | Entry document |
|---|---|---|
| 001 — Masking Algebra | Under what conditions do masking operations compose and preserve information? | [RELAY-001](research-relay/RELAY-001-Perspective-Masking-Algebra.md) |
| 002 — Dynamic Behavioral Equivalence | What counts as conditionally equivalent behavior over time? | [RELAY-002](research-relay/RELAY-002-Dynamic-Behavioral-Equivalence.md) |
| 003 — Composition and Contracts | When do local guarantees survive relay composition? | [RELAY-003](research-relay/RELAY-003-Relay-Composition-and-Contracts.md) |
| 004 — Biological Dynamic Intelligence | Which biological analogies are testable and identifiable? | [RELAY-004](research-relay/RELAY-004-Biological-Dynamic-Intelligence.md) |
| 005 — Open Structural Evolution | How can new structures be selected without losing governance? | [RELAY-005](research-relay/RELAY-005-Open-Structural-Evolution.md) |

**Proposed additional track:** **RSI–UIERU Convergence and Structural Governance**—an extension discussed for a future `RELAY-006`; it is **not** counted among the five initial completed tracks. Its focus is bidirectional: RSI can generate candidate structures; UIERU-style contracts and evidence can help evaluate and govern them.

For contribution expectations and attribution, see [RESEARCH-COLLABORATION.md](research-relay/RESEARCH-COLLABORATION.md).

## 8. The four proposed specifications

| Specification | What it makes explicit |
|---|---|
| [SPEC-001 — Dynamic UIERU Observation Model](specs/SPEC-001-Dynamic-UIERU-Observation-Model.md) | Identity, context, perspective, time, provenance, behavior, evolution |
| [SPEC-002 — Perspective Masking Contract](specs/SPEC-002-Perspective-Masking-Contract.md) | Operation semantics, preconditions, uncertainty, governance |
| [SPEC-003 — Dynamic Differential and Query Schema](specs/SPEC-003-Dynamic-Differential-and-Query-Schema.md) | Comparison contracts, PDT, PASQ, query results and evidence |
| [SPEC-004 — Research Relay Piece Contract](specs/SPEC-004-Research-Relay-Piece-Contract.md) | Problem, model, hypotheses, evidence, validation, interfaces, lineage |

These are **proposed research specifications**, not ratified interoperability standards. A conforming example should not be mistaken for an independently tested implementation.

## 9. Seven distinctions worth keeping visible

1. **Observation ≠ intervention.** A filtered view does not establish a causal effect.
2. **Score ≠ decision.** A changed valuation need not change an action.
3. **Decision ≠ trajectory.** Execution can diverge from intent.
4. **Repeated execution ≠ structural learning.** Experience becomes learning only through an evidenced update process.
5. **Behavioral similarity ≠ mechanism identity.** This matters especially in biological analogies.
6. **Local equivalence ≠ compositional substitutability.** The environment and contract matter.
7. **Structural explainability ≠ full model interpretability.** A transparent relay path can still contain opaque LLM components.

## 10. How to evaluate a claim in this repository

Before treating a statement as a result, ask:

- Is it a **definition**, a **candidate theorem**, an **empirical hypothesis**, an **illustrative example**, or a **validated finding**?
- What are its perspective, context, history, temporal window, assumptions, and comparison contract?
- Which evidence supports it? What would falsify it?
- Does the evidence concern a local unit, a relay system, or an evolving population of units?
- Are there counterexamples, confounders, unobserved internal states, or distribution shifts?
- Can another researcher reproduce or independently challenge the claim?

A strong contribution can be a proof, an implementation, a reproducible dataset, a negative result, or a decisive counterexample. **A rejected hypothesis is useful research progress when its failure conditions are recorded.**

## 11. A practical first research contribution

A modest but meaningful entry project could be:

1. Choose two agent or workflow configurations and one bounded task distribution.
2. Record observations using the fields proposed in [SPEC-001](specs/SPEC-001-Dynamic-UIERU-Observation-Model.md).
3. Declare a single perspective and an explicit comparison contract using [SPEC-002](specs/SPEC-002-Perspective-Masking-Contract.md).
4. Compare scoring, decisions, and observed trajectories separately using [SPEC-003](specs/SPEC-003-Dynamic-Differential-and-Query-Schema.md).
5. Test a specific substitution claim; seek a counterexample under changed context or history.
6. Publish the assumptions, artifacts, uncertainty, negative cases, and replication instructions using [SPEC-004](specs/SPEC-004-Research-Relay-Piece-Contract.md).

This is a **suggested experiment**, not a report of one already performed.

## 12. Figures and navigation

The intended figure sequence is:

1. `figures/Fig-001-BUI-DSI-Grand-Research-Map.png`
2. `figures/Fig-002-From-Static-SI-to-Dynamic-UIERU.png`
3. `figures/Fig-003-Perspective-Masking-Architecture.png`
4. `figures/Fig-004-Perspective-Differential-Tree.png`
5. `figures/Fig-005-Perspective-Aware-Structural-Query.png`
6. `figures/Fig-006-Dynamic-Equivalence-and-Relay-Composition.png`
7. `figures/Fig-007-Mathematics-Neuroscience-and-SI.png`
8. `figures/Fig-008-Open-Research-Relay-Ecosystem.png`

**Release check:** Verify that the eight named image files exist as separate assets before relying on individual links; a composite eight-panel image alone does not satisfy these paths.

Additional navigation files planned for the repository root: `CONTENTS.md`, `GLOSSARY.md`, `FIGURE-INDEX.md`, `OPEN-QUESTIONS.md`, `TESTABLE-HYPOTHESES.md`, `VALIDATION-ROADMAP.md`, and `FUTURE-DIRECTIONS.md`.

## 13. Research integrity and collaboration

BUI-DSI is deliberately open to refutation. In particular:

- Proposed mathematical laws require proofs or carefully delimited counterexamples.
- Neuroscientific analogies require empirical support and competing explanations.
- RSI–UIERU convergence is a research hypothesis and design opportunity, not a demonstrated identity.
- Interface proposals require implementations and conformance testing before interoperability can be claimed.
- Governance mechanisms should be tested against evaluator gaming, Goodhart effects, distribution shift, and relay failure.

Read [RESEARCH-COLLABORATION.md](research-relay/RESEARCH-COLLABORATION.md) before proposing a new research relay piece or submitting evidence. Preserve original attribution and the provenance of all additions and corrections.

## 14. Next steps

**New to the topic?** Start with [BUI-001](docs/BUI-001-From-Static-Structural-Intelligence-to-Dynamic-Intelligence-Units.md).  
**Want a concrete case?** Start with [CASE-001](cases/CASE-001-Perspective-Masked-Model-Selection.md).  
**Want a proof problem?** Start with [RELAY-001](research-relay/RELAY-001-Perspective-Masking-Algebra.md).  
**Want a data interface?** Start with [SPEC-001](specs/SPEC-001-Dynamic-UIERU-Observation-Model.md).  
**Want to contribute?** Start with [RESEARCH-COLLABORATION.md](research-relay/RESEARCH-COLLABORATION.md).

---

**Citation and attribution:** Sizhe Tan & GPT-Obot, *Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay*, v1.0.0 (2026). Consult `CITATION.cff` and the repository's DOI metadata when available; do not invent a DOI before registration.

**Research invitation:** Prove a conditional result, construct a counterexample, test a competing explanation, or improve a research contract—and relay the evidence in both directions.

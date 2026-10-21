# Changelog

All notable changes to **Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay (BUI-DSI)** are documented here.

This repository is a research framework and open research agenda. A release documents the state of its proposals and research interfaces; it does **not** imply that the proposed mathematical properties, biological analogies, or engineering hypotheses have been proved or empirically validated.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and version labels follow [Semantic Versioning](https://semver.org/) as a documentation convention.

## [Unreleased]

### Planned
- Investigate a dedicated `RELAY-006-RSI-UIERU-Convergence-and-Structural-Governance.md` research piece, subject to inclusion in a later release.
- Conduct formal proofs, counterexample construction, independent replication, and empirical validation of candidate claims.
- Develop machine-checkable examples and conformance tests for the four proposed specifications.
- Export and review eight individual figure files, ensuring captions and links match the figure index.
- Incorporate external research contributions, including negative results and revisions to assumptions.

## [1.0.0] - 2026-10-21

### Added — Research foundation
- Eight core papers in `docs/`:
  - `BUI-001-From-Static-Structural-Intelligence-to-Dynamic-Intelligence-Units.md`
  - `BUI-002-Perspective-Masking-and-Dynamic-Structural-Observation.md`
  - `BUI-003-Perspective-Differential-Trees-and-Dynamic-Localization.md`
  - `BUI-004-Perspective-Aware-Structural-Query-and-SQL.md`
  - `BUI-005-Dynamic-Equivalence-Relay-Composition-and-Emergent-Relations.md`
  - `BUI-006-Mathematical-Foundations-and-Open-Formal-Problems.md`
  - `BUI-007-Biological-Intelligence-and-Dynamic-Organizational-Biomimicry.md`
  - `BUI-008-Open-Research-Relay-and-the-Next-Horizon-of-Structural-Intelligence.md`
- Three illustrative cases in `cases/`:
  - `CASE-001-Perspective-Masked-Model-Selection.md`
  - `CASE-002-Dynamic-Equivalence-and-Relay-Substitution.md`
  - `CASE-003-Context-Dependent-Biological-Intelligence.md`
- Five open research relay pieces in `research-relay/`:
  - `RELAY-001-Perspective-Masking-Algebra.md`
  - `RELAY-002-Dynamic-Behavioral-Equivalence.md`
  - `RELAY-003-Relay-Composition-and-Contracts.md`
  - `RELAY-004-Biological-Dynamic-Intelligence.md`
  - `RELAY-005-Open-Structural-Evolution.md`
- `research-relay/RESEARCH-COLLABORATION.md` for contribution pathways, research provenance, counter-evidence, and cross-disciplinary collaboration.
- Four proposed research interface specifications in `specs/`:
  - `SPEC-001-Dynamic-UIERU-Observation-Model.md`
  - `SPEC-002-Perspective-Masking-Contract.md`
  - `SPEC-003-Dynamic-Differential-and-Query-Schema.md`
  - `SPEC-004-Research-Relay-Piece-Contract.md`

### Added — Repository navigation and research planning
- `README.md`, `START-HERE.md`, and `CONTENTS.md` for overview and reading paths.
- `GLOSSARY.md` to distinguish observation from explanation, scores from decisions, trajectories from learning, and behavioral equivalence from substitutability.
- `FIGURE-INDEX.md` to document eight planned figure topics and placements.
- `FUTURE-DIRECTIONS.md` describing the long-term research agenda.
- `OPEN-QUESTIONS.md` organizing 29 open research questions.
- `TESTABLE-HYPOTHESES.md` organizing 15 empirical hypotheses and separate candidate formal propositions.
- `VALIDATION-ROADMAP.md` organizing proposed validation stages P0–P6.

### Introduced — Research concepts
- Dynamic UIERU observation with explicit context, perspective, history, evidence, and provenance.
- Perspective Masking with distinctions among projection, replay, simulation, intervention, and counterfactual estimation.
- Perspective Differential Trees (PDT) and Perspective-Aware Structural Query (PASQ).
- Four differential categories: scoring, decision, trajectory, and learning.
- Conditional dynamic behavioral equivalence, relay substitution, contract preservation, and evolution-aware comparison.
- Open Structural Evolution with evaluator governance, counter-evidence, and anti-Goodhart safeguards.
- Research Relay Pieces as portable descriptions of problems, models, hypotheses, evidence, validation, and interfaces.
- An exploratory RSI–UIERU convergence direction, without asserting equivalence between RSI, LLMs, and UIERU architectures.
- Biological dynamic organizational analogies framed as testable hypotheses, not established neural mechanisms.

### Research integrity and limitations
- Mathematical laws and equivalence properties are **candidate propositions** unless accompanied by proofs.
- Synthetic case data and proposed experiments are **illustrative**, not empirical results.
- Structural interpretability is distinguished from interpretation of opaque per-node models.
- Counterexamples, negative findings, and revisions are first-class research outcomes.
- The presence of a specification does not establish implementation conformance or deployment safety.

### Figure publication note
- Eight figure subjects and intended filenames are catalogued in `FIGURE-INDEX.md`. The initial artwork was produced as a composite overview; individual `figures/Fig-001-...png` through `Fig-008-...png` files must be checked or exported before the release is considered visually complete. Do not treat the figure index as proof that those eight separate assets are present.

### Release administration
- Initial research-documentation release candidate prepared for GitHub and a prospective Zenodo DOI deposit.
- A DOI must not be cited as assigned until Zenodo has issued it.
- Authorship: **Sizhe Tan & GPT-Obot**.

---

## Versioning and correction policy

- **Patch (`1.0.x`)**: editorial fixes, corrected links, metadata corrections, and non-substantive clarifications.
- **Minor (`1.x.0`)**: additional research pieces, hypotheses, cases, figures, and compatible specification extensions.
- **Major (`x.0.0`)**: material changes to central research definitions, comparison semantics, or specification contracts that require downstream review.
- Substantive counter-evidence may require a revision even when the earlier statement was central to a published release. Preserve a traceable record rather than silently overwriting research history.

## Citation

Use `CITATION.cff` and the corresponding release record when available. Cite a version-specific DOI only after one has been assigned. For the latest working material, refer to the repository and identify the accessed version or commit.

# Figure Index — Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay

**Version:** 1.0.0 (draft)  
**Authors:** Sizhe Tan & GPT-Obot  
**Repository:** `Beyond-UIERU-Dynamic-Structural-Intelligence`  
**Status:** Figure plan and insertion guide; verify individual image assets before release.

## 1. Purpose and asset status

This index defines the eight intended figures, their conceptual roles, captions, and recommended placements throughout the BUI-DSI repository. It distinguishes **planned standalone assets** from assets actually available for publication.

At the time of drafting this index, an **eight-panel composite overview image** has been generated as `a_wide_composite_infographic_image_with_8_labeled.png`. That composite is **not equivalent to eight separately exported, verified PNG files**. The eight filenames below are canonical *targets*, not a claim that eight individual files already exist. Before release, export or recreate each panel as a legible, standalone image; check terminology, numbering, and readability at normal GitHub display sizes.

**Canonical image directory:** `figures/`.

## 2. Master figure catalog

| No. | Canonical filename | Title / focus | Primary document | Additional relevant documents |
|---|---|---|---|---|
| 001 | `Fig-001-BUI-DSI-Grand-Research-Map.png` | Grand research map: observation to open research relay | `README.md`; `docs/BUI-001-From-Static-Structural-Intelligence-to-Dynamic-Intelligence-Units.md` | `START-HERE.md`, `docs/BUI-008-Open-Research-Relay-and-the-Next-Horizon-of-Structural-Intelligence.md` |
| 002 | `Fig-002-From-Static-SI-to-Dynamic-UIERU.png` | Transition from static structures to stateful, evolving units | `docs/BUI-001-From-Static-Structural-Intelligence-to-Dynamic-Intelligence-Units.md` | `docs/BUI-007-Biological-Intelligence-and-Dynamic-Organizational-Biomimicry.md` |
| 003 | `Fig-003-Perspective-Masking-Architecture.png` | Observation projection, replay, intervention, and counterfactual separation | `docs/BUI-002-Perspective-Masking-and-Dynamic-Structural-Observation.md` | `research-relay/RELAY-001-Perspective-Masking-Algebra.md`, `specs/SPEC-002-Perspective-Masking-Contract.md` |
| 004 | `Fig-004-Perspective-Differential-Tree.png` | Scoring, decision, trajectory, and learning differentials | `docs/BUI-003-Perspective-Differential-Trees-and-Dynamic-Localization.md` | `cases/CASE-001-Perspective-Masked-Model-Selection.md`, `specs/SPEC-003-Dynamic-Differential-and-Query-Schema.md` |
| 005 | `Fig-005-Perspective-Aware-Structural-Query.png` | PASQ query flow over perspective-aware evidence and differential indexes | `docs/BUI-004-Perspective-Aware-Structural-Query-and-SQL.md` | `specs/SPEC-003-Dynamic-Differential-and-Query-Schema.md` |
| 006 | `Fig-006-Dynamic-Equivalence-and-Relay-Composition.png` | Conditional equivalence, substitution, and contract-preserving relay | `docs/BUI-005-Dynamic-Equivalence-Relay-Composition-and-Emergent-Relations.md` | `cases/CASE-002-Dynamic-Equivalence-and-Relay-Substitution.md`, `research-relay/RELAY-002-Dynamic-Behavioral-Equivalence.md`, `research-relay/RELAY-003-Relay-Composition-and-Contracts.md` |
| 007 | `Fig-007-Mathematics-Neuroscience-and-SI.png` | Cross-disciplinary hypothesis, experiment, and counter-evidence interface | `docs/BUI-007-Biological-Intelligence-and-Dynamic-Organizational-Biomimicry.md` | `docs/BUI-006-Mathematical-Foundations-and-Open-Formal-Problems.md`, `cases/CASE-003-Context-Dependent-Biological-Intelligence.md`, `research-relay/RELAY-004-Biological-Dynamic-Intelligence.md` |
| 008 | `Fig-008-Open-Research-Relay-Ecosystem.png` | Research Relay Pieces, provenance, validation, critique, and versioned growth | `docs/BUI-008-Open-Research-Relay-and-the-Next-Horizon-of-Structural-Intelligence.md` | `research-relay/RESEARCH-COLLABORATION.md`, `specs/SPEC-004-Research-Relay-Piece-Contract.md` |

## 3. Figure descriptions, captions, and placement guidance

### Fig-001 — BUI-DSI Grand Research Map

**Intended content:** A high-level flow linking dynamic UIERU observation, perspective masking, differential localization, structural query, conditional equivalence, relay composition, open evolution, and open research relay. Show evidence and counter-evidence as feedback rather than a one-way pipeline.

**Suggested caption:** *Figure 1. BUI-DSI research map. Dynamic intelligence is studied through explicit observations, perspectives, differential structures, queries, conditional equivalence, compositional contracts, and open research relay. Feedback and counter-evidence can revise earlier claims.*

**Insert:** Near the beginning of `README.md`, after the project overview and before the document map. Optionally repeat in BUI-001 immediately after its framing of the research agenda. Use one canonical file rather than duplicating assets.

### Fig-002 — From Static SI to Dynamic UIERU

**Intended content:** Contrast a relatively static structural inventory with a dynamic intelligence unit having context, perspective, scoring, action, feedback, history, and evolution. Avoid suggesting that every SI structure or every LLM automatically implements a UIERU.

**Suggested caption:** *Figure 2. From structural components to dynamically situated intelligence units. The UIERU research model makes behavior, context, feedback, and evolution explicit without presupposing a particular internal implementation.*

**Insert:** In BUI-001, after the static-versus-dynamic conceptual comparison and before the proposed dynamic unit model.

### Fig-003 — Perspective Masking Architecture

**Intended content:** A common observation record branching into distinct perspective-specific views; separate paths for descriptive projection, deterministic replay, simulation, actual intervention, and counterfactual estimation. Label evidence provenance and uncertainty.

**Suggested caption:** *Figure 3. Perspective masking architecture. Descriptive views, replay, simulation, intervention, and counterfactual estimates have different epistemic meanings and must not be conflated.*

**Insert:** In BUI-002, immediately after the masking operator taxonomy; cross-reference from RELAY-001 and SPEC-002.

### Fig-004 — Perspective Differential Tree

**Intended content:** A comparison root with perspective/context validity conditions and four differential branches: scoring, decision, trajectory, learning. Include leaf evidence, uncertainty, and invalidation on structural evolution.

**Suggested caption:** *Figure 4. Perspective Differential Tree (PDT). Differential claims are indexed by explicit comparison conditions and evidence, enabling targeted localization without treating every observed difference as learning.*

**Insert:** In BUI-003, after the PDT node/branch model; reference in CASE-001 and SPEC-003.

### Fig-005 — Perspective-Aware Structural Query

**Intended content:** PASQ query specification → observation/evidence store → perspective-aware filtering → PDT or differential index → query result with provenance and validity flags. SQL is an implementation option, not the definition of PASQ.

**Suggested caption:** *Figure 5. Perspective-Aware Structural Query (PASQ). Queries retrieve dynamic structural comparisons under declared perspective, context, history, and evidence constraints.*

**Insert:** In BUI-004, after the query architecture and before SQL examples; reference in SPEC-003.

### Fig-006 — Dynamic Equivalence and Relay Composition

**Intended content:** Two internally different units compared under a shared contract, with conditional behavioral equivalence; show substitution into a larger relay graph and a system-level contract check. Include a failure/rollback path.

**Suggested caption:** *Figure 6. Conditional dynamic equivalence and relay substitution. Local behavioral similarity does not by itself guarantee system-level contract preservation, especially under learning and environmental change.*

**Insert:** In BUI-005, between the equivalence framework and relay composition discussion; cross-reference in CASE-002 and RELAY-003.

### Fig-007 — Mathematics, Neuroscience, and SI

**Intended content:** Three research communities exchanging candidate models, formal definitions, experiments, counterexamples, and revised hypotheses. Show a two-way relationship rather than claiming neural mechanisms instantiate UIERU components.

**Suggested caption:** *Figure 7. A bidirectional research interface among mathematics, neuroscience, and structural intelligence. Biological observations constrain computational analogies; formal models help generate falsifiable hypotheses.*

**Insert:** In BUI-007, after the discussion of dynamic organizational biomimicry and before experimental validation; reference in BUI-006 and CASE-003.

### Fig-008 — Open Research Relay Ecosystem

**Intended content:** Research Relay Pieces with problem, model, hypotheses, evidence/counter-evidence, validation, interfaces, provenance, and version history. Depict contributions from multiple disciplines and revision of prior claims.

**Suggested caption:** *Figure 8. Open Research Relay ecosystem. Research problems and their evidentiary boundaries are portable, contestable, versioned, and reusable across disciplines.*

**Insert:** In BUI-008, after the Research Relay Piece model and before collaboration or governance; cross-reference in `research-relay/RESEARCH-COLLABORATION.md` and SPEC-004.

## 4. Canonical Markdown embedding

From a document under `docs/`, `cases/`, `research-relay/`, or `specs/`, use a relative path such as:

```markdown
![Figure 4. Perspective Differential Tree](figures/Fig-004-Perspective-Differential-Tree.png)

*Figure 4. Perspective Differential Tree (PDT). Differential claims are indexed by explicit comparison conditions and evidence.*
```

From root-level `README.md`, use:

```markdown
![Figure 1. BUI-DSI Grand Research Map](figures/Fig-001-BUI-DSI-Grand-Research-Map.png)
```

**Do not insert these links until the corresponding standalone files exist**, or GitHub will display broken images. The composite overview may instead be referenced explicitly by its real filename if committed to the repository.

## 5. Publication and quality-control checklist

- [ ] Eight independent PNG assets exist with the exact canonical names above.
- [ ] Figure numbers and filenames match the displayed diagrams and captions.
- [ ] Text and arrows remain legible when images are scaled to GitHub content width.
- [ ] Every caption distinguishes proposed models from established or experimentally supported results.
- [ ] Figure 3 clearly separates observation, replay, intervention, and counterfactual inference.
- [ ] Figure 4 distinguishes scoring, decision, trajectory, and learning differentials.
- [ ] Figure 6 does not equate local equivalence with guaranteed global substitutability.
- [ ] Figure 7 avoids unsupported claims about brain mechanisms.
- [ ] All Markdown links resolve from the document's actual directory.
- [ ] Each figure has descriptive alt text and consistent credit.
- [ ] `README.md`, `CONTENTS.md`, and `START-HERE.md` reflect the final asset status.

## 6. Credits and research status

**Conceptual research and figure direction:** Sizhe Tan & GPT-Obot.  
**Figure status:** Conceptual illustrations of an open research agenda; not empirical results, proofs, or evidence of biological implementation.

The index is a living navigation artifact. Future figure revisions should preserve traceability to the relevant paper, specification, and version.


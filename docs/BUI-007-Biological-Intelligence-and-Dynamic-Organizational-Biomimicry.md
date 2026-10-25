# BUI-007 — Biological Intelligence and Dynamic Organizational Biomimicry

**Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay**  
**Version:** 1.0.0 (research proposal)  
**Date:** 2026-10-25  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Open research agenda; hypotheses and analogies are not established neuroscientific findings.

## Abstract

Biological intelligence operates through context-sensitive perception, valuation, action, feedback, memory, and adaptation. This paper investigates whether the Universal Intelligence Evolution and Relay Unit (UIERU) offers a useful *functional abstraction* for studying such processes, without claiming that brains literally implement UIERU, explicit Scoring Forests, or software-like Relay contracts. We propose **dynamic organizational biomimicry**: transfer principles of changing functional organization rather than copying neural anatomy. We distinguish observed biological phenomena, computational interpretations, and speculative structural-intelligence hypotheses; formulate a minimal state-dependent model; examine shifting functional boundaries, perspective-dependent selection, distributed coordination, and learning; and identify falsifiable experiments and collaboration interfaces for neuroscience, mathematics, and structural intelligence (SI) engineering. The intended contribution is a portable, testable research agenda, not a completed biological theory.

**Keywords:** structural intelligence; UIERU; dynamic organizational biomimicry; neural population dynamics; context-dependent computation; action selection; reinforcement learning; functional networks; perspective masking; research relay.

## 1. Scope and epistemic discipline

This article asks: **Can UIERU-like abstractions help explain, predict, or engineer selected properties of biological dynamic intelligence?** Three levels of claims must remain separate:

1. **Empirical observation:** behavioral and neural findings reported in experimental neuroscience.
2. **Computational interpretation:** models proposed to explain those findings, often with multiple plausible alternatives.
3. **SI hypothesis:** proposed correspondences between those models and UIERU/SIF/UCPSF concepts.

Functional analogy is neither neural homology nor proof of shared implementation. A successful analogy should yield predictions or engineering benefits beyond retrospective vocabulary matching. This article does not assert that any animal has a discrete UIERU, a literal Perspective Mask, a Scoring Forest data structure, or a named Relay API.

## 2. From static structural biomimicry to dynamic organizational biomimicry

Earlier SI work developed mechanisms such as metric-differential structures, triggers, localization, per-node intelligence, portable units, scoring, contracts, and relay. These can be *compared* with biological phenomena such as discrimination, context-sensitive responses, memory retrieval, specialized circuits, valuation, and inter-area coordination. Such comparisons remain provisional.

UIERU changes the focal object: instead of treating a capability as a static component, it considers an intelligence unit whose observable behavior depends on its state, environment, task, evaluative configuration, interactions, and learning history. **Dynamic organizational biomimicry** therefore studies how functions are recruited, coordinated, stabilized, and reorganized over time. It seeks reusable principles, not faithful replicas of brains.

## 3. A minimal comparative model

For a candidate functional unit, define:

\[
U_t=(S_t,\Theta_t,\mathcal{I}_t,\mathcal{O}_t,\mathcal{R}_t),
\]

where \(S_t\) is latent or measured state, \(\Theta_t\) is an adaptable policy or evaluative configuration, \(\mathcal{I}_t\) and \(\mathcal{O}_t\) describe input/output relations, and \(\mathcal{R}_t\) describes interactions with other units or resources. This is a modeling choice, not an anatomical decomposition.

A state-dependent behavioral model is:

\[
a_t\sim\pi_{\Theta_t}(\cdot\mid o_t,c_t,g_t,h_t),
\]

\[
S_{t+1}\sim T(\cdot\mid S_t,a_t,o_t,c_t),\qquad
\Theta_{t+1}=L(\Theta_t,S_t,a_t,r_t,h_t),
\]

where \(o_t\) is observation, \(c_t\) context, \(g_t\) goals or motivational constraints, \(h_t\) relevant history, and \(r_t\) feedback. These equations do not imply that biological brains implement explicit policy tables or reward scalars.

A *Perspective* in SI can be operationalized as a declared evaluative condition or family of conditions; biological motivation, task rules, attention, and bodily state may influence this condition but are not automatically identical to it.

## 4. Biological phenomena motivating the comparison

### 4.1 Context-dependent computation

Behavior can vary with task instructions, motivational state, environmental uncertainty, and recent experience. Context-dependent neural computations have been studied in distributed cortical and subcortical systems. A UIERU-like model may represent this through conditional policy selection or state-dependent valuation. **Open question:** Does an explicit Perspective variable improve prediction compared with a conventional recurrent or latent-state model of matched complexity?

### 4.2 Neural population dynamics

Neural populations exhibit temporally evolving activity patterns that participate in computation. Their collective dynamics are not reducible to a static catalog of neuron roles. UIERU's dynamic view is a potentially useful abstraction, but neural population dynamics alone do not establish modular intelligence units.

### 4.3 Valuation and action selection

Basal ganglia-associated circuits, frontal networks, and neuromodulatory processes participate in learning and action selection. Multiple goals and constraints can influence behavior. Scoring Forests provide an *engineering analogy* for plural valuation; they should not be presented as an identified neural data structure. Biological valuation may be distributed, nonlinear, implicit, and partially non-comparable across tasks.

### 4.4 Learning and historical dependence

Plasticity, memory consolidation, and changes in network dynamics shape future behavior. UIERU's evolving state captures the broad idea of history dependence. However, biological adaptation includes synaptic, cellular, circuit, physiological, and behavioral timescales, and does not always require explicit structural additions.

### 4.5 Coordination across functional systems

Brains support recurrent and distributed communication across circuits. SI Relay can model transfer, coordination, and state-dependent influence, but neural communication does not necessarily resemble message passing between software components with clean boundaries or typed contracts.

## 5. The central boundary question: fixed units or emergent functional organizations?

Anatomical structures can be comparatively stable while task-relevant functional coalitions change. Consequently, a biological counterpart of a UIERU, if useful at all, might be a **temporarily assembled functional organization**, not a persistent, localized anatomical object.

Let \(N\) denote available neural resources and let \(B_t\subseteq N\) be a candidate functional boundary inferred under a specified task and measurement regime:

\[
B_t=\Phi(N,c_t,g_t,h_t,\mathcal{D}_{\le t}),
\]

where \(\mathcal{D}_{\le t}\) denotes evidence available through time \(t\). This equation is an inference framework, not a known biological law. The boundary may be overlapping, graded, and uncertain rather than a crisp set.

**Research problem:** Under what observational or intervention criteria can a functional unit be identified reproducibly? Proposed criteria include predictive sufficiency, causal contribution, relative autonomy, stability over a task window, and usefulness for transfer across tasks. These criteria may conflict.

## 6. Perspective masking as a neuroscientific method: analogy and limits

SI distinguishes at least three operations:

- **Observational mask:** restricts which variables or records an analyst inspects without changing the organism.
- **Interventional mask:** changes neural, sensory, motivational, or environmental conditions; this can alter the system being studied.
- **Counterfactual mask:** estimates what would have occurred under a different condition; this requires a justified causal or statistical model.

These operations must never be conflated. An apparent invariance under observational filtering does not demonstrate invariance under intervention. In neuroscience, perturbation effects may propagate across recurrent circuits and compensatory mechanisms.

For matched trials, define a conditional behavioral contrast:

\[
\Delta_{p,q}(x)=\mathbb{E}[Y\mid do(P=p),X=x]-\mathbb{E}[Y\mid do(P=q),X=x],
\]

only where \(P\) is a well-defined manipulable experimental condition and the causal estimand is identifiable. For non-manipulable constructs, use descriptive conditional contrasts instead of \(do(\cdot)\). Outcome \(Y\) can be a decision, reaction time, trajectory feature, or neural summary, with explicit measurement units.

## 7. Differential trees and the search for invariant mechanisms

A Perspective Differential Tree (PDT) may index experimentally observed contrasts at four levels:

1. **Valuation differential:** change in a measurable preference or model-derived value estimate.
2. **Decision differential:** change in action selection probability.
3. **Trajectory differential:** change in behavior or neural activity over time.
4. **Learning differential:** change in later responses after feedback or training.

Each comparison node should carry a **comparison contract**: organism/species, task, conditions, measurement, time window, matching assumptions, uncertainty, provenance, and potential confounders. A PDT is an evidence index, not automatically a causal explanation. Shared patterns across conditions are candidates for invariants; counterexamples should be actively sought.

## 8. Dynamic equivalence without anatomical identity

Two candidate functional organizations may be similar for one task yet differ under stress, new contexts, or prolonged learning. Define a task-scoped behavioral distance:

\[
d_{\mathcal{T},\mathcal{C}}(U,V)=
\sup_{(\tau,c)\in\mathcal{T}\times\mathcal{C}}
D\bigl(P_U(Y\mid\tau,c),P_V(Y\mid\tau,c)\bigr),
\]

where \(D\) is a specified divergence and \(\mathcal{T},\mathcal{C}\) are declared task and context sets. This is a *proposed metric-like comparison*, not necessarily a mathematical metric: the chosen divergence may fail symmetry or triangle inequality. Finite experimental coverage yields only bounded empirical evidence, not universal equivalence.

A stronger notion could compare responses to interventions and adaptation over time. Such conditions are relevant to relay substitution in engineering, but neural circuits need not be interchangeable merely because their output distributions match in a narrow experiment.

## 9. Relay, coordination, and collective dynamics

In SI, Relay includes transfers of tasks, representations, constraints, results, or accumulated experience. Biological systems exhibit communication and coordination across scales, yet the mapping is partial. Three hypotheses are worth testing:

- **Coordination hypothesis:** a network-aware dynamic-unit model predicts task switching better than an isolated-unit model.
- **History-relay hypothesis:** modeling shared or transmitted learning-relevant state improves prediction of later behavior.
- **Boundary-adaptation hypothesis:** allowing functional memberships to vary with context improves out-of-distribution prediction.

All require comparisons against established recurrent-network, state-space, and dynamical-systems baselines; improved fit alone is insufficient without complexity controls and held-out tests.

## 10. Mathematical interfaces

The biological comparison motivates collaboration with several disciplines:

| Research area | Candidate formal question | Important caution |
| --- | --- | --- |
| Dynamical systems | When are behavioral regimes stable or switchable? | Neural systems may be nonstationary and partially observed. |
| Control and causal inference | Which perturbations identify relevant mechanisms? | Observational association is not intervention. |
| Information theory | How much predictive information is lost by masking? | Compression quality depends on task and distribution. |
| Formal methods | Which unit properties survive composition? | Local properties rarely imply global guarantees alone. |
| Geometry of neural populations | Which representational features generalize across contexts? | Geometric similarity does not establish identical computation. |
| Probabilistic modeling | Can hidden context and motivational state be inferred? | Latent-variable identifiability may be weak. |

The objective is to formulate questions existing theories can address, while being precise about genuinely new extensions.

## 11. Proposed empirical studies

### Study A — Context switching and perspective-conditioned behavior

**Design:** Use an established task-switching paradigm with controlled cues, matched stimuli, and repeated trials. Compare (i) a conventional context-conditioned model, (ii) a recurrent latent-state model, and (iii) an explicitly perspective-conditioned UIERU-inspired model.  
**Outcomes:** held-out choice prediction, reaction-time prediction, calibration, parameter count, and performance under unseen cue combinations.  
**Disconfirmation:** the UIERU-inspired abstraction offers no predictive or interpretive gain after complexity and data controls.

### Study B — Dynamic functional boundaries

**Design:** Using appropriately acquired or openly available population recordings, infer candidate functional coalitions under different task contexts. Compare fixed partitions, overlapping partitions, and time-varying memberships.  
**Outcomes:** held-out neural/behavioral prediction, robustness across sessions, and stability under alternative preprocessing.  
**Disconfirmation:** dynamic membership does not improve generalization or produces unstable, non-replicable boundaries.

### Study C — Differential-tree evidence indexing

**Design:** Build a PDT over existing multi-condition experimental results, preserving metadata and uncertainty. Compare retrieval of cross-context invariants and counterexamples with a flat metadata index.  
**Outcomes:** retrieval precision/recall, analyst effort, false-invariance rate, and reproducibility.  
**Disconfirmation:** the tree adds complexity without measurable analytical benefit.

### Study D — Relay and composition

**Design:** Model two interacting functional subsystems under explicit communication or coupling manipulations. Compare independent-subsystem predictions against joint models.  
**Outcomes:** generalization to new coupling conditions, error attribution, and intervention prediction.  
**Disconfirmation:** the proposed Relay abstraction adds no useful explanatory or predictive structure.

## 12. Evidence and counter-evidence protocol

Every claim should be tagged **OBSERVED**, **MODELED**, **HYPOTHESIZED**, or **NOT ESTABLISHED**. Record species, task, intervention, dataset, preprocessing, model assumptions, competing explanations, and failure cases. Negative results are first-class contributions. The absence of evidence for a clean functional boundary is not a failed project; it may falsify an overly rigid UIERU analogy and motivate a better abstraction.

Potential failure modes include anthropomorphic terminology, circular model evaluation, selection of only supportive neural results, ignoring bodily and ecological constraints, and treating learned computational variables as directly measured biological quantities.

## 13. Engineering implications for UIERU and SIF

Biological findings may motivate, but do not compel, the following engineering extensions:

- **Dynamic unit boundaries:** temporary and overlapping membership of capabilities or resources.
- **Context inference:** estimation of latent task regime before or alongside perspective selection.
- **Multi-timescale state:** separate fast activity, short-term adaptation, and durable learning.
- **Evidence-preserving masking:** explicit separation of filtered observation from system intervention.
- **Behavior-conditioned localization:** retrieve units by validated context-dependent response profiles.
- **Adaptive relay contracts:** record coupling assumptions and monitor their violation after composition.

These proposals should be evaluated against simpler alternatives before adoption.

## 14. Open research problems

**BIO-01 — Unit individuation:** What makes a functional intelligence unit empirically identifiable across contexts and timescales?  
**BIO-02 — Perspective operationalization:** Which experimentally manipulable variables approximate a declared SI Perspective, and where does the analogy fail?  
**BIO-03 — Boundary dynamics:** Are dynamically overlapping units more predictive than fixed modules?  
**BIO-04 — Scoring pluralism:** Can multiple valuation mechanisms be distinguished empirically from a single latent utility model?  
**BIO-05 — Masking validity:** Which apparent invariants survive causal perturbation?  
**BIO-06 — Relay and learning:** How do interactions alter later functional organization?  
**BIO-07 — Cross-species generality:** Which principles replicate across animals with markedly different nervous systems?  
**BIO-08 — Mathematical portability:** Which formal properties carry over from neural models to engineered UIERU systems?

## 15. Research Relay interface

A portable biological research piece should contain:

```yaml
relay_piece:
  id: BIO-XX
  question: "A falsifiable question"
  claim_status: HYPOTHESIZED
  species_and_task: "Declared scope"
  operational_variables: []
  datasets_or_protocols: []
  baseline_models: []
  candidate_uiERU_mapping: []
  predicted_observations: []
  counterevidence_conditions: []
  limitations: []
  provenance: []
  contribution_interfaces:
    - mathematical_formalization
    - neuroscience_validation
    - met_implementation
```

This contract supports independent contributions by neuroscientists, mathematicians, and SI engineers. Contributors should be free to reject UIERU terminology while preserving the underlying scientific question.

## 16. Relationship to the BUI-DSI series

- **BUI-001:** motivates the shift from static structures to dynamic units.
- **BUI-002:** supplies the distinction between observation masks, interventions, and counterfactuals.
- **BUI-003:** supplies differential indexing and comparison contracts.
- **BUI-004:** supplies evidence-oriented perspective-aware query concepts.
- **BUI-005:** supplies scoped equivalence and composition questions.
- **BUI-006:** frames the mathematical problems requiring formal treatment.
- **BUI-008:** will describe open research relay and the next horizon.

This paper also connects to the planned `CASE-003-Context-Dependent-Biological-Intelligence.md` and `RELAY-004-Biological-Dynamic-Intelligence.md`.

## 17. Selected foundational references

The following are background sources for established research areas, **not** evidence that UIERU has been found in brains.

1. Vyas, S., Golub, M. D., Sussillo, D., & Shenoy, K. V. (2020). *Computation Through Neural Population Dynamics*. Annual Review of Neuroscience, 43, 249–275. https://doi.org/10.1146/annurev-neuro-092619-094115
2. Mante, V., Sussillo, D., Shenoy, K. V., & Newsome, W. T. (2013). *Context-dependent computation by recurrent dynamics in prefrontal cortex*. Nature, 503, 78–84. https://doi.org/10.1038/nature12742
3. Rigotti, M., Barak, O., Warden, M. R., et al. (2013). *The importance of mixed selectivity in complex cognitive tasks*. Nature, 497, 585–590. https://doi.org/10.1038/nature12160
4. Sutton, R. S., & Barto, A. G. (2018). *Reinforcement Learning: An Introduction*, 2nd ed. MIT Press. http://incompleteideas.net/book/the-book-2nd.html
5. Friston, K. (2010). *The free-energy principle: a unified brain theory?* Nature Reviews Neuroscience, 11, 127–138. https://doi.org/10.1038/nrn2787
6. Bassett, D. S., & Sporns, O. (2017). *Network neuroscience*. Nature Neuroscience, 20, 353–364. https://doi.org/10.1038/nn.4502

Theories cited above differ substantially in assumptions and explanatory commitments. Their inclusion does not imply a unified consensus or validation of the SI mapping. A systematic literature review and experimental partnerships are future work.

## 18. Conclusion

UIERU is best treated as a **testable functional abstraction** for dynamic intelligence, not an asserted biological building block. Biological intelligence offers evidence of context-sensitive, distributed, historically conditioned computation; mathematics can specify what abstractions preserve; and MET can implement and compare competing designs. The strongest contribution of dynamic organizational biomimicry may be to identify *where the analogy breaks*: shifting boundaries, hidden states, multiscale learning, and coupled interactions can reveal what the next generation of SI units must represent.

**Research relay statement:** We publish these questions, models, limitations, and disconfirmation criteria so that future researchers can independently refine, reject, or replace them. Open disagreement and negative findings are part of the intended relay.

---

**Citation suggestion:** Tan, Sizhe, and GPT-Obot (2026). *BUI-007: Biological Intelligence and Dynamic Organizational Biomimicry*. In *Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay*, v1.0.0. Repository DOI: pending release.

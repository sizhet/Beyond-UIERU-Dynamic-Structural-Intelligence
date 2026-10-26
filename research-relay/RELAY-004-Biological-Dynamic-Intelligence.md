# RELAY-004 — Biological Dynamic Intelligence

**Repository:** Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay (BUI-DSI)  
**Version:** 1.0.0  
**Authors:** Sizhe Tan & GPT-Obot  
**Document type:** Open Research Relay Piece (research agenda; not an empirical finding)  
**Status:** Proposed models, falsifiable hypotheses, and collaboration interfaces

## Abstract

Biological intelligence adapts its behavior to changing goals, contexts, bodily conditions, histories, and environments. This Research Relay Piece asks whether selected features of such adaptation can be studied using a *dynamic structural intelligence* vocabulary: context-conditioned valuation, distributed functional coordination, temporally evolving unit boundaries, action–feedback loops, and evidence-aware comparison. We use **UIERU-like** (Universal Intelligence Evolution and Relay Unit-like) only as a computational abstraction, not as a proposed anatomical constituent of the brain. The document specifies candidate models, competing explanations, observational and interventional methods, mathematical problems, counter-evidence criteria, and a research exchange contract. It is intended for neuroscientists, cognitive scientists, mathematicians, and structural-intelligence engineers who may independently test, refine, or reject the proposed connections.

**Core question:** Under which observable conditions, if any, do dynamically coordinated biological functions admit useful UIERU-like descriptions without erasing essential biological mechanisms?

## 1. Research positioning and epistemic boundaries

The research program distinguishes four kinds of statement:

| Category | Meaning | Appropriate evidence |
|---|---|---|
| Established observation | A phenomenon documented in a specified organism, task, and measurement regime | Reproducible experimental literature or data |
| Computational analogy | A structural similarity between a biological process and a model | Explicit mapping and its limits |
| Testable hypothesis | A prediction that can be contradicted by observations or interventions | Preregistered comparisons, held-out tests, interventions |
| Engineering proposal | A design that borrows organizational principles | Measured engineering performance and failure analysis |

**Non-claims:** Brains are not asserted to contain literal UIERUs, Scoring Forests, CCC operators, SQL engines, or Relay contracts. Neural activity is not presumed to be decomposable into stable software-like modules. Behavioral similarity is not proof of shared mechanism. A predictive model is not automatically a causal explanation.

The motivation is narrower and more useful: develop a vocabulary and formal interface that can expose *which dynamic organizational hypotheses are worth testing*.

## 2. Biological phenomena motivating the inquiry

Several experimentally studied phenomena suggest useful comparison points:

1. **Context-dependent computation.** Similar sensory evidence can support different actions depending on task instructions, reward contingencies, or internal state.
2. **Population-level dynamics.** Neural computation may be better described by evolving activity across populations than by assigning a fixed symbolic function to each neuron.
3. **Mixed selectivity and distributed representation.** Task variables can be represented jointly and flexibly rather than in rigidly separated modules.
4. **Learning and plasticity.** Behavioral policies and the neural mechanisms supporting them may change across experience.
5. **Distributed coordination.** Functional relationships among regions and populations can depend on task and measurement timescale.
6. **Embodiment and regulation.** Action selection depends on the organism's body, needs, and environment, not merely an abstract input–output mapping.

These are *motivations for hypotheses*, not evidence that any particular UIERU mapping is correct.

## 3. Candidate dynamic organizational model

Let an organism be studied under task environment \(e_t\), measured context \(c_t\), latent or estimated internal state \(z_t\), action \(a_t\), observation \(o_t\), and history \(h_t\). A candidate descriptive model is

$$
 z_{t+1} \sim T_\theta(z_{t+1}\mid z_t,o_t,a_t,c_t,e_t),
 \qquad
 a_t \sim \pi_\theta(a_t\mid z_t,c_t,h_t).
$$

A *perspective* \(p\) denotes a declared analytic question, for example reward sensitivity, threat avoidance, uncertainty reduction, or energy expenditure. A perspective-conditioned observational map is

$$
 y_t^{(p)}=M_p(o_{0:t},a_{0:t},c_{0:t},\hat z_{0:t};\mathcal A_p),
$$

where \(\mathcal A_p\) records measurement and modeling assumptions. \(M_p\) is a **researcher's transformation of data** unless an actual intervention is specified. It is not assumed to be a biological operator.

A UIERU-like *functional unit* is provisionally a tuple

$$
 U=(B, I, V, D, F, L, R, \Gamma),
$$

where \(B\) is a candidate boundary, \(I\) inputs, \(V\) valuation or task-dependent prioritization, \(D\) decision dynamics, \(F\) feedback, \(L\) learning, \(R\) interactions with other units, and \(\Gamma\) the validity conditions of the description. No one-to-one correspondence with neurons or regions is implied.

## 4. Three competing explanations of functional organization

**H0 — Fixed-function organization.** Stable components perform approximately fixed roles; context changes mainly input weighting or routing.

**H1 — Context-dependent reweighting.** A largely stable network changes its effective interactions or readout weights with context.

**H2 — Dynamically reorganized functional coalitions.** Context and learning alter which distributed elements jointly implement a function, including the effective functional boundary.

These are deliberately simplified competing model classes. Real data may favor mixtures, hierarchical combinations, or none of them. H2 must not be declared superior simply because it resembles the UIERU vocabulary.

A key methodological question is whether H2 predicts held-out behavior or neural responses better *after controlling for added model complexity and measurement uncertainty*.

## 5. What counts as a functional boundary?

A boundary must be operationalized, not inferred from a diagram. Candidate criteria include:

- Predictive sufficiency: does the selected population explain a target variable on held-out trials?
- Conditional independence: does information from excluded variables materially improve prediction after conditioning on the proposed unit?
- Intervention sensitivity: does perturbing selected elements change the predicted function in a context-specific way?
- Stability horizon: over what timescale and contexts does the boundary remain useful?
- Transfer: does the same boundary definition generalize across sessions, individuals, and tasks?

A boundary may be **soft, overlapping, multiscale, and temporary**. A boundary inferred solely from correlations should be labeled observational. Neural recordings often sample only part of a circuit; unobserved variables can invalidate strong boundary claims.

## 6. Perspective masking: three distinct operations

### 6.1 Observational masking

Choose variables, trials, timescales, or projections for analysis. Example: compare activity–behavior relationships during reward-seeking versus threat-avoidance trials while preserving raw data and metadata.

### 6.2 Experimental intervention

Manipulate a cue, reward schedule, neural population, or circuit element. Intervention effects depend on design, targeting, and confounding; observational masks cannot substitute for interventions.

### 6.3 Counterfactual inference

Estimate what would have happened under an unobserved condition using an explicit causal model. Counterfactual claims require assumptions about identifiability and uncertainty.

The three operations must be recorded separately in the evidence provenance. Calling all three “masking” without semantic tags would obscure the central scientific distinction.

## 7. Perspective Differential Trees for biological data

A **Perspective Differential Tree (PDT)** is proposed as an *analysis and indexing structure* for differences across declared perspectives. It need not be a literal tree in the brain.

```text
Biological task and measurement contract
└── Context contrast: food-seeking vs threat avoidance
    ├── Observation differential
    │   ├── Behavior and reaction time
    │   └── Population activity / connectivity estimates
    ├── Valuation differential
    │   └── Candidate latent value weights and uncertainty
    ├── Decision differential
    │   └── Action-policy distribution shift
    ├── Trajectory differential
    │   └── Time-resolved state and behavior changes
    ├── Learning differential
    │   └── Across-session adaptation
    └── Evidence and counter-evidence
        ├── Intervention results
        ├── Negative controls
        └── Alternative model explanations
```

A PDT node should contain a contrast definition, effect estimate, uncertainty interval, population/task provenance, comparison baseline, and validity conditions. The index is valuable only if it makes cross-context comparison more reproducible or revealing than simpler baselines.

## 8. Behavioral equivalence is conditional, not anatomical

Two biological subjects, sessions, or candidate functional organizations may yield similar action distributions while relying on different neural mechanisms. Define a task-scoped behavioral discrepancy:

$$
 d_{\mathcal C,p,H}(A,B)
 = \mathbb E_{x\sim\mathcal C}
 \left[D\big(P_A(\tau_{0:H}\mid x,p),P_B(\tau_{0:H}\mid x,p)\big)\right],
$$

where \(\mathcal C\) specifies context distribution, \(H\) a time horizon, \(\tau\) a behavioral trajectory, and \(D\) a declared divergence or distance. This is a **candidate metric or pseudometric**, depending on \(D\) and the model class; metric properties are not assumed.

Small discrepancy may justify a restricted behavioral comparison, not mechanistic equivalence or safe interchangeability. Neural perturbation can distinguish systems that look equivalent under passive observation.

## 9. Relay and distributed coordination

The term **Relay** here denotes a proposed description of information, influence, or functional dependency across components and timescales. Biological signal propagation, network interactions, and learning transfer are not automatically equivalent to software message passing.

A candidate interaction graph \(G_t=(V_t,E_t,W_t)\) can summarize inferred relationships among observed populations. Its edge semantics must be declared:

- statistical association;
- directed predictive dependence;
- estimated effective connectivity;
- experimentally supported causal influence.

These edge types cannot be freely substituted. A change in \(G_t\) may reflect genuine reorganization, changes in sampling, movement artifacts, or altered model fitting. **Two-way evidence flow** means that failed predictions and counter-evidence update the structural hypothesis rather than being discarded.

## 10. Mathematical research problems

**BIO-M1 — Identifiability of dynamic functional units.** Under which observational and interventional assumptions can a context-dependent functional boundary be identified, even approximately?

**BIO-M2 — Invariance under perspective projection.** Which conclusions about action or state trajectories are preserved when measurements are projected into different analytic perspectives?

**BIO-M3 — Dynamic equivalence under partial observation.** How do observational limits affect bounds on trajectory discrepancy between candidate models?

**BIO-M4 — Multiscale composition.** Can verified relations among local population models support nontrivial guarantees for a larger behavioral system?

**BIO-M5 — Learning-aware validity.** How quickly can a fitted functional boundary or equivalence claim expire under plasticity and nonstationarity?

**BIO-M6 — Model selection with complexity control.** What predictive or intervention-based gains are required to justify dynamic-coalition models over fixed or reweighted models?

**BIO-M7 — Causal masking semantics.** When can observational projection, intervention, and counterfactual inference be composed without introducing invalid causal conclusions?

**BIO-M8 — Uncertainty propagation.** How should sampling, model, and intervention uncertainty propagate through a PDT and cross-unit Relay analysis?

These are open problems; this document offers no proof that all have tractable general solutions.

## 11. Proposed empirical study A: context-switching behavior

**Question:** Does context-conditioned valuation improve predictions of behavioral switching beyond a context-blind policy?

**Design:** Use a well-controlled task with explicit changes in reward and risk contingencies. Record actions, reaction times, task variables, and where ethically and technically appropriate, neural activity.

**Comparators:** (i) context-blind policy, (ii) context-conditioned fixed architecture, (iii) dynamic reweighting, (iv) dynamic-coalition candidate.

**Primary endpoints:** held-out predictive likelihood or prespecified error, calibration, cross-context transfer, and model complexity. If neural data are used, assess prediction of held-out neural responses separately from behavior.

**Failure condition:** If simpler models match or outperform the dynamic model after fair complexity control, the added UIERU-like abstraction is not supported for that task.

## 12. Proposed empirical study B: intervention and boundary testing

**Question:** Do candidate functional boundaries predict context-specific perturbation effects?

**Design:** Estimate candidate boundaries on training data, preregister perturbation targets and outcomes, and evaluate on independent conditions. The exact technique depends on species, ethics approval, and scientific feasibility.

**Controls:** sham or control interventions where appropriate, matched task difficulty, movement and arousal measures, off-target effects, and replication across sessions.

**Primary endpoint:** accuracy of *prospective* perturbation-effect predictions compared with fixed-module and reweighting baselines.

**Failure condition:** Context-dependent boundary predictions fail prospectively, or effects are explained by simpler nuisance variables.

## 13. Proposed empirical study C: learning and boundary drift

**Question:** Does experience induce detectable changes in functional organization beyond parameter adaptation in a stable architecture?

**Design:** Track repeated learning sessions and estimate change points, transfer, and model drift. Separate true neural changes from recording instability and changes in behavioral strategy.

**Primary endpoints:** predeclared out-of-session prediction, drift detection reliability, and intervention generalization where possible.

**Failure condition:** Claimed organizational drift vanishes under recording controls, or does not improve explanatory/predictive power.

## 14. Proposed empirical study D: engineering transfer

**Question:** Can organizational principles inferred from biological comparisons improve an artificial adaptive agent?

Compare agents with matched resources:

- fixed policy with context features;
- adaptive reweighting;
- UIERU-like units with explicit context, scoring, feedback, provenance, and controlled structural updates.

Measure task performance, adaptation speed, robustness, auditability, and compute cost. Engineering success would support *utility of the abstraction*, not its biological truth. Negative results should be published with sufficient detail to diagnose whether the issue lies in the hypothesis, implementation, or task.

## 15. Counter-evidence and alternative explanations

| Apparent support for dynamic UIERU-like organization | Alternative explanation or disconfirmation test |
|---|---|
| Different context yields different neural pattern | Global arousal, movement, sensory input, or measurement artifact |
| Different populations predict behavior in different tasks | Sampling bias, regularization instability, correlated inputs |
| A flexible model predicts better | Greater parameter count or leakage across train/test splits |
| Functional graph changes over time | Time-varying signal quality or estimator bias |
| Two subjects behave similarly | Distinct underlying mechanisms; perturbation dissociation |
| A structural index reveals many differences | Multiple testing, arbitrary perspective selection, uncorrected search |
| Artificial UIERU-like agent performs well | Generic modularity, extra compute, or tuned hyperparameters |

A responsible research program preregisters principal comparisons when feasible, publishes negative results, tracks multiplicity, and separates exploratory from confirmatory analyses.

## 16. Candidate hypotheses and falsification criteria

**BIO-H1 (Contextual valuation).** Explicit context-conditioned valuation improves held-out behavioral predictions relative to context-blind baselines under matched model capacity. **Refute** if no robust gain appears across prespecified contexts.

**BIO-H2 (Dynamic functional boundary).** Context-specific boundaries prospectively predict perturbation effects better than fixed boundaries. **Refute** if simpler models are equally predictive after controls.

**BIO-H3 (Perspective differential utility).** PDT-based indexing improves reproducibility or error localization in multi-context analysis versus conventional metadata and statistical summaries. **Refute** if it adds complexity without measurable benefit.

**BIO-H4 (Conditional equivalence).** Two models that are behaviorally close in one context can diverge under another context or intervention. **Refute in a specified study** if no divergence is observed at its declared power and sensitivity; absence of observed divergence is not universal equivalence.

**BIO-H5 (Learning-sensitive contracts).** Explicit validity horizons reduce unsupported reuse of stale behavioral models across learning sessions. **Refute** if drift-aware baselines perform as well with lower complexity.

**BIO-H6 (Engineering biomimicry).** A constrained UIERU-like adaptive architecture improves at least one preregistered performance–auditability trade-off against matched alternatives. **Refute** if improvements fail replication or disappear under matched resources.

## 17. Research roadmap and decision gates

| Phase | Deliverable | Go/no-go gate |
|---|---|---|
| 0. Scope | Organism/task, ethical scope, available measurements, preregistered contrasts | Questions operationalized |
| 1. Baselines | Reproducible fixed and reweighted models | Data quality and fair comparison verified |
| 2. Observation | Perspective projections and PDT with uncertainty | Reproducibility exceeds metadata-only baseline |
| 3. Intervention | Prospective causal tests where feasible | Predictions survive controls and replication |
| 4. Formalization | Restricted theorems, bounds, or impossibility results | Assumptions explicit; counterexamples cataloged |
| 5. Transfer | Matched-resource artificial-system study | Measurable utility without biological overclaim |
| 6. Relay | Versioned research artifacts and external critique | Independent replication or informative falsification |

A no-go result may be a valuable Research Relay outcome if it sharply limits the valid scope of an abstraction.

## 18. Data, ethics, and reproducibility

Biological experiments require domain-specific ethics review and responsible data governance. This document does not prescribe interventions in humans or animals. Any such study must follow applicable institutional review, consent, welfare, and privacy requirements.

Minimum reproducibility package where permitted: protocol, anonymized or access-controlled data references, preprocessing, exclusions, split strategy, model definitions, uncertainty estimates, null results, and code or precise algorithmic specifications. For human neural data, privacy and re-identification risks can prevent unrestricted release; share safe metadata and controlled-access procedures instead.

## 19. Open Research Relay Piece contract

The following is a **proposed exchange format**, not a ratified standard:

```yaml
research_relay_piece:
  id: BUI-DSI-RELAY-004
  title: Biological Dynamic Intelligence
  version: 1.0.0
  status: open_research_problem
  authors:
    - Sizhe Tan
    - GPT-Obot
  problem:
    question: >
      When do biological dynamic functional organizations admit
      useful, falsifiable UIERU-like computational descriptions?
    scope: context-dependent behavior and distributed dynamics
    exclusions:
      - no literal UIERU-in-brain claim
      - no anatomical equivalence inferred from behavior alone
  models:
    candidates:
      - fixed_function
      - context_reweighting
      - dynamic_functional_coalition
    assumptions_required: true
  hypotheses:
    - BIO-H1
    - BIO-H2
    - BIO-H3
    - BIO-H4
    - BIO-H5
    - BIO-H6
  evidence:
    provenance_required: true
    uncertainty_required: true
    negative_results_welcome: true
    separate_observation_intervention_counterfactual: true
  validation:
    preregister_primary_comparisons: true
    held_out_tests: true
    matched_complexity_baselines: true
    prospective_intervention_when_feasible: true
  interfaces:
    mathematical:
      - dynamic_systems
      - causal_inference
      - model_identifiability
      - approximate_equivalence
    scientific:
      - systems_neuroscience
      - computational_neuroscience
      - cognitive_science
    engineering:
      - context_aware_agents
      - structural_intelligence
  governance:
    counter_evidence_updates_claims: true
    record_failed_predictions: true
    preserve_original_contributor_credit: true
```

Contributors should attach the exact task, species or population, dataset and ethics status, measurement modality, model assumptions, statistical method, and limitations to every claim.

## 20. Collaboration tasks by discipline

**Systems and computational neuroscience:** Identify concrete tasks and datasets; distinguish behavioral, neural, and causal claims; define feasible interventions and measurement limitations.

**Mathematics and theoretical computer science:** Formalize observational projections, conditional equivalence, compositional limits, identifiability, and impossibility results.

**Causal inference and statistics:** Design intervention-aware comparisons, uncertainty propagation, sensitivity analyses, and controls for model selection bias.

**AI and SI engineering:** Build transparent adaptive-agent baselines and test whether explicit structural contracts improve auditability or adaptation under fair resource constraints.

**Philosophy of science and research methodology:** Critique operational definitions, inference boundaries, and the difference between explanation, prediction, analogy, and mechanism.

## 21. Relationship to the BUI-DSI series

- **BUI-002:** Perspective masking and dynamic structural observation.
- **BUI-003:** Perspective Differential Trees and localization.
- **BUI-005:** Conditional equivalence and Relay composition.
- **BUI-006:** Mathematical foundations and open formal problems.
- **BUI-007:** Biological intelligence and dynamic organizational biomimicry.
- **BUI-008:** Open Research Relay as a method of transmitting falsifiable questions.
- **CASE-003:** A concrete context-dependent biological-intelligence case study.
- **RELAY-001:** Perspective masking algebra.
- **RELAY-002:** Dynamic behavioral equivalence.
- **RELAY-003:** Relay composition and contracts.

The present document translates biological analogies into *research tasks with evidence obligations*. It is not a substitute for the empirical and domain-specific literature.

## 22. Selected foundational reading

The following works provide background on neural population dynamics, context-dependent computation, distributed representation, learning, and network neuroscience. Their inclusion does **not** imply endorsement of UIERU terminology or claims.

1. Mante, V., Sussillo, D., Shenoy, K. V., & Newsome, W. T. (2013). Context-dependent computation by recurrent dynamics in prefrontal cortex. *Nature*, 503, 78–84.
2. Rigotti, M., Barak, O., Warden, M. R., et al. (2013). The importance of mixed selectivity in complex cognitive tasks. *Nature*, 497, 585–590.
3. Vyas, S., Golub, M. D., Sussillo, D., & Shenoy, K. V. (2020). Computation through neural population dynamics. *Annual Review of Neuroscience*, 43, 249–275.
4. Bassett, D. S., & Sporns, O. (2017). Network neuroscience. *Nature Neuroscience*, 20, 353–364.
5. Sutton, R. S., & Barto, A. G. (2018). *Reinforcement Learning: An Introduction* (2nd ed.). MIT Press.
6. Friston, K. (2010). The free-energy principle: a unified brain theory? *Nature Reviews Neuroscience*, 11, 127–138.

## 23. Closing research invitation

The scientifically useful question is not whether biological intelligence can be renamed in SI vocabulary. It is whether carefully specified dynamic structural models can yield **better predictions, sharper causal tests, more reproducible comparisons, or clearer limits of applicability**.

A positive result should carry its conditions and uncertainties. A negative result should narrow or reject the proposed mapping. Both outcomes are legitimate advances in an open research Relay.

**Research principle:** *Let biological evidence constrain structural analogy; let structural hypotheses generate falsifiable experiments; let counter-evidence change the model.*

---

**Citation suggestion:** Tan, S., & GPT-Obot. (2026). *RELAY-004 — Biological Dynamic Intelligence*. Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay, v1.0.0. DOI to be assigned upon release.

# CASE-003 — Context-Dependent Biological Intelligence

**Repository:** Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay (BUI-DSI)  
**Version:** 1.0.0 — Research case / conceptual protocol  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Proposed computational analogy and falsifiable research agenda; not an empirical demonstration

## Abstract

Biological agents change their actions when bodily needs, threats, task rules, and prior experience change. This case explores whether the *functional organization* of such context-dependent behavior can be studied using a UIERU-like abstraction: a dynamic intelligence unit with explicit observation conditions, perspective-dependent valuation, action selection, feedback, and adaptation. We develop a controlled, synthetic foraging-versus-threat scenario, distinguish biological evidence from engineering analogy, propose perspective-masked observations and differential comparisons, and outline tests that could reject the model. The objective is neither to identify literal UIERU modules in brains nor to equate neural circuits with software scoring trees. It is to provide a portable research problem at the intersection of computational neuroscience, formal methods, and structural intelligence engineering.

**Keywords:** biological intelligence; context-dependent decision-making; dynamic functional organization; UIERU; perspective masking; behavioral differential; computational neuroscience; open research relay.

## 1. Scope and epistemic status

This case has three deliberately separated layers:

1. **Established background:** animal behavior depends on physiological state, environmental contingencies, experience, and neural processing; distributed neural circuits contribute to valuation, action selection, and learning.
2. **Computational abstraction:** a UIERU-like model can represent selected input–state–action–feedback relationships without claiming a one-to-one neural implementation.
3. **Open hypotheses:** perspective-conditioned comparison and dynamically assembled functional units may offer useful explanatory or predictive models. These claims require experiments and competing-model tests.

The illustrative numbers below are **synthetic**. No animal or neural data were collected for this case.

## 2. Why this case matters

The BUI-DSI research program asks whether methods originally developed for relatively static SI structures can be extended to systems whose observable behavior depends on context and history. Biological intelligence offers a stringent test: the same sensory cue can support different actions under different needs or threats. It also challenges overly neat engineering assumptions. Biological processes are noisy, partially observable, embodied, and distributed; boundaries between functional units may change with task and state.

A useful model must account for these complications, not explain them away.

## 3. A minimal biological scenario

Consider an animal in an environment containing food, a shelter, and intermittent predator cues. The animal can:

- **Forage:** approach food and consume it.
- **Shelter:** move to cover or remain there.
- **Inspect:** gather information before committing.

The environment and observable food cue are held constant for paired comparisons while internal hunger, perceived threat, and learning history vary. In real experiments, ethical protocols, species-specific behavior, and ecological validity would constrain the design.

### 3.1 Context variables

Let the context at time `t` be:

$$
C_t=(h_t,r_t,e_t,q_t),
$$

where `h` is hunger, `r` is estimated threat, `e` is external sensory evidence, and `q` is the current task or contingency. History `H_t` summarizes prior outcomes and learned expectations.

A *perspective* `P_t` is an **analytical construct** representing the current weighting or prioritization of competing goals, not a claim that an animal explicitly stores a symbolic perspective object.

## 4. UIERU-like functional model

Define an abstract unit:

$$
U_t=(S_t,P_t,\mathcal A,V_t,\pi_t,L_t,R_t),
$$

with internal state `S`, perspective `P`, candidate actions `A`, valuation function `V`, policy `π`, learning operator `L`, and interaction/relay interface `R`.

A minimal decision loop is:

$$
O_t\rightarrow \widehat C_t\rightarrow P_t\rightarrow V_t(a\mid S_t,\widehat C_t,P_t)
\rightarrow A_t\rightarrow O_{t+1}\rightarrow S_{t+1}.
$$

The notation is a *modeling convenience*. Biological valuation, context inference, and action selection may occur concurrently, recursively, or without separable stages. A more general transition model is:

$$
p(S_{t+1},A_t\mid S_t,O_t,H_t),
$$

which does not require a serial pipeline.

## 5. Synthetic example: perspective-dependent action selection

For illustration only, suppose the three candidate actions have normalized hypothetical utility scores:

| Matched observation condition | Forage | Shelter | Inspect | Selected action |
|---|---:|---:|---:|---|
| High hunger, low perceived threat | 0.85 | 0.30 | 0.45 | Forage |
| High hunger, high perceived threat | 0.35 | 0.90 | 0.55 | Shelter |
| Moderate hunger, uncertain threat | 0.48 | 0.50 | 0.78 | Inspect |

These scores are not neural recordings or measured utilities. They merely show how the same action set can yield different choices as context and inferred priorities vary. In actual work, a comparison must specify how values are estimated, whether scales are commensurate, and which confounders are controlled.

## 6. Perspective masking: observation versus intervention

A *perspective mask* defines which variables or components are exposed in an analysis. Four operations must not be conflated:

1. **Observational projection:** show only selected recorded features, leaving the original process unchanged.
2. **Conditional comparison:** compare trials matched on specified context and history covariates.
3. **Experimental intervention:** manipulate a physiological, sensory, or neural variable, potentially changing the process itself.
4. **Counterfactual estimation:** infer an unobserved outcome under explicit modeling assumptions.

For observational projection `M_P`, a desirable property might be idempotence, `M_P(M_P(X)) = M_P(X)`, provided it is a pure, deterministic projection. That algebraic property does **not** imply that intervening to suppress a neural signal twice is harmless or behavior-preserving.

A masking contract should record: target variables, retained variables, time window, sampling resolution, data provenance, comparison population, known confounders, and whether any causal intervention occurred.

## 7. Perspective differential analysis

Define four distinct comparison layers:

**Valuation differential:** differences in estimated action values under matched evidence and specified context.

$$
\Delta V(a)=V(a\mid P_1,C,H)-V(a\mid P_2,C,H).
$$

**Decision differential:** whether the chosen action or action distribution changes. Equal actions do not imply equal values.

**Trajectory differential:** whether subsequent sequences of positions, actions, and observations diverge. Trajectories must be compared under aligned observation windows and appropriate stochastic metrics.

**Learning differential:** whether repeated experience changes future policies or inferred priorities. Distinguish within-trial state changes from across-trial learning.

A Perspective Differential Tree (PDT) may index these comparisons by shared task, evidence conditions, state matching, difference type, and provenance. It is a structured retrieval aid, not proof of a biological decision mechanism.

## 8. A proposed differential-tree record

```yaml
comparison_id: bio-context-001
status: synthetic-illustration
species: unspecified
observation_window: illustrative-trial
matched:
  - food_cue
  - action_set
varied:
  - hunger
  - perceived_threat
perspectives:
  - food-seeking
  - threat-avoidance
differentials:
  valuation: hypothetical
  decision: forage-versus-shelter
  trajectory: not_observed
  learning: not_observed
causal_claim: none
provenance: synthetic-example
counterevidence_needed:
  - context-matched-trials
  - independent-behavioral-measures
  - competing-model-predictions
```

This record explicitly avoids fabricating trajectories or learning outcomes.

## 9. The boundary question: fixed or emerging functional units?

The most consequential biological question may be whether the useful computational boundary of a decision-making unit remains fixed across tasks. The neural substrate is physical, but a *functional grouping* of participating populations may depend on task, internal state, and interaction history.

Candidate models include:

- **Fixed-module model:** the same designated subsystem performs the relevant computation across contexts.
- **Reweighted-network model:** a stable network changes its effective interactions and gain.
- **Dynamic-coalition model:** different populations contribute to a temporary functional organization.

These alternatives can generate similar behavioral outputs. Neural recordings, perturbations, and model comparison are needed to discriminate among them. A UIERU-like engineering abstraction should not presuppose that the third model is correct.

## 10. Biological relay and distributed coordination

Relay is used here as a functional term for information or control transfer among interacting processes, not a claim that brain regions exchange explicit SI contracts. Biological examples may involve recurrent corticocortical interactions, cortico-basal-ganglia loops, and neuromodulatory effects, depending on species and task.

A research question is whether **conditional coordination patterns**, rather than fixed anatomical edges alone, improve prediction of action selection. Possible evidence includes time-resolved recordings and perturbation studies, with attention to common-input confounds.

## 11. Mathematical interface

A useful starting point is a partially observed controlled stochastic process:

$$
S_{t+1}\sim T_\theta(\cdot\mid S_t,A_t,C_t),\qquad
A_t\sim \pi_\theta(\cdot\mid O_{\le t},H_t).
$$

The UIERU-like decomposition is one candidate parameterization of `T` and `π`, not a new biological law. Relevant mathematical connections include partially observable Markov decision processes, dynamical systems, state-space models, causal inference, and approximate behavioral equivalence.

Two models that produce similar choices under one context need not be interchangeable under new contexts or perturbations. Define an evaluation domain `D` and compare predictive distributions using a prespecified distance `d`:

$$
d_D(U_i,U_j) = \mathbb E_{x\sim D}\left[d\bigl(p_i(\cdot\mid x),p_j(\cdot\mid x)\bigr)\right].
$$

This is a candidate metric-like quantity; whether it satisfies metric axioms depends on the choice of `d` and model representation.

## 12. Competing hypotheses and falsifiers

**H1 — Context-aware model advantage.** A model with explicit state/context conditioning predicts held-out action distributions better than a context-agnostic baseline. **Falsifier:** no reproducible improvement under preregistered metrics and comparable model capacity.

**H2 — Perspective-factorization usefulness.** A factorized model with interpretable goal-weight variables generalizes across context shifts better than an equally expressive unfactorized baseline. **Falsifier:** equivalent or better out-of-distribution performance from the baseline.

**H3 — Differential indexing utility.** PDT-based retrieval finds matched behavioral contrasts with greater precision or lower analyst effort than conventional metadata queries. **Falsifier:** no improvement on blinded retrieval tasks.

**H4 — Dynamic functional boundary.** A task-conditioned grouping of neural activity predicts held-out behavior better than a fixed grouping after controlling complexity. **Falsifier:** fixed groupings explain data equally well or better.

**H5 — Intervention validity.** Observationally inferred perspective changes predict responses to specified manipulations. **Falsifier:** predicted changes fail under controlled intervention; this would limit the causal interpretation of the model.

None of these hypotheses has been tested by this case.

## 13. Proposed experimental program

### Phase A — Behavioral-only study

Collect ethically approved, species-appropriate behavioral sequences across hunger, threat, and uncertainty conditions. Prespecify outcome variables and balance or measure relevant covariates. Fit baseline state-space and reinforcement-learning models alongside the UIERU-like factorization.

### Phase B — Dynamic comparison

Use held-out contexts and trajectories. Compare calibration, predictive likelihood, policy-shift detection, and counterfactual robustness. Build differential records with full provenance and explicitly label any model-derived estimates.

### Phase C — Neural observations

If suitable existing datasets or ethically approved recordings are available, test whether inferred functional groupings change with task. Compare fixed, reweighted, and dynamic-coalition models using held-out neural and behavioral data.

### Phase D — Perturbation and causal assessment

Where ethically justified and technically feasible, test discriminating causal predictions using interventions appropriate to the organism and experiment. Observational masking alone is insufficient for causal claims.

### Phase E — Engineering transfer

Implement a small UIERU-like agent in simulation. Test whether perspective-conditioned observation, differential indexing, and explicit provenance improve debugging or transfer. Engineering success alone does not establish biological validity.

## 14. Failure modes and counter-evidence

- **Anthropomorphic labels:** treating hunger or fear as literal software perspective objects.
- **Circular explanation:** assigning a perspective after observing an action and then using it to explain that action.
- **Uncontrolled confounding:** comparing trials with different sensory evidence, learning histories, or motor constraints.
- **False modularity:** inferring stable neural units from a convenient computational decomposition.
- **Score reification:** interpreting synthetic utilities as measured brain quantities.
- **Causal overreach:** treating filtered observational data as an intervention.
- **Overfitting:** fitting a highly flexible dynamic model without held-out evaluation.
- **Species generalization:** assuming a model supported in one species or task transfers automatically to others.

Counter-evidence should be retained in the same research relay as supportive results.

## 15. RSI and UIERU: a neighboring engineering research line

LLM-agent recursive self-improvement (RSI) and UIERU-like systems share functional interests in evaluation, feedback, candidate modification, and iterative adaptation. RSI emphasizes the improvement process; UIERU emphasizes explicit organization of state, perspectives, contracts, relay, and provenance. Their apparent proximity is a research hypothesis, not proof of architectural equivalence. Structural transparency may be greater in an explicitly instrumented UIERU implementation, but it does not automatically make embedded neural models interpretable.

A useful cross-domain comparison asks whether the same observational and differential contracts can characterize (a) a biological context-dependent agent, (b) a simulated UIERU-like agent, and (c) an LLM-agent improvement loop—while preserving domain-specific differences.

## 16. Open research relay interface

This case is intended as a portable research piece, with the following contract:

```yaml
relay_piece: CASE-003
problem: context-dependent-biological-intelligence
claim_level: computational-hypothesis
models:
  - fixed-module
  - reweighted-network
  - dynamic-coalition
  - uieru-like-functional-abstraction
required_evidence:
  - task-and-context-definitions
  - observation-provenance
  - matched-comparison-contract
  - held-out-predictions
  - counterevidence-log
contribution_modes:
  - alternative-formalization
  - mathematical-proof-or-counterexample
  - behavioral-dataset-analysis
  - neural-model-comparison
  - negative-result
  - engineering-replication
```

Contributors should be able to challenge or replace the UIERU-like decomposition without having to endorse the entire SI framework.

## 17. Relationship to the BUI-DSI repository

- **BUI-001:** transition from static SI structures to dynamic intelligence units.
- **BUI-002:** observational versus interventional masking.
- **BUI-003:** perspective differentials and dynamic localization.
- **BUI-004:** provenance-aware structural queries.
- **BUI-005:** conditional behavioral equivalence and relay substitution.
- **BUI-006:** mathematical foundations and open formal problems.
- **BUI-007:** biological intelligence and dynamic organizational biomimicry.
- **BUI-008:** open research relay and future research horizons.
- **CASE-001/002:** engineering comparison cases that complement this biological hypothesis case.

The proposed figure **Fig-007-Mathematics-Neuroscience-and-SI.png** is particularly relevant here; the text does not assume the image has already been produced.

## 18. Selected foundational literature and verification notes

The following are established entry points, not evidence that UIERU itself is biologically instantiated. Bibliographic details and links should be verified against publishers before release.

1. Sutton, R. S., & Barto, A. G. (2018). *Reinforcement Learning: An Introduction*, 2nd ed. MIT Press. https://incompleteideas.net/book/the-book-2nd.html
2. Dayan, P., & Abbott, L. F. (2001). *Theoretical Neuroscience: Computational and Mathematical Modeling of Neural Systems*. MIT Press.
3. Mante, V., Sussillo, D., Shenoy, K. V., & Newsome, W. T. (2013). Context-dependent computation by recurrent dynamics in prefrontal cortex. *Nature*, 503, 78–84. https://doi.org/10.1038/nature12742
4. Vyas, S., Golub, M. D., Sussillo, D., & Shenoy, K. V. (2020). Computation Through Neural Population Dynamics. *Annual Review of Neuroscience*, 43, 249–275. https://doi.org/10.1146/annurev-neuro-092619-094115
5. Krakauer, J. W., Ghazanfar, A. A., Gomez-Marin, A., MacIver, M. A., & Poeppel, D. (2017). Neuroscience Needs Behavior: Correcting a Reductionist Bias. *Neuron*, 93(3), 480–490. https://doi.org/10.1016/j.neuron.2016.12.041

These sources support general approaches to dynamic behavior and neural computation. The proposed masking, PDT, and UIERU mappings remain original research proposals requiring independent validation.

## 19. Conclusion

Biological intelligence provides a demanding benchmark for any theory of dynamic structural intelligence. Context-sensitive valuation, action, and learning are real biological phenomena; their decomposition into UIERU-like units is not an established neural fact. By separating evidence, analogy, hypotheses, and falsifiers, this case makes the biological connection useful without overstating it. The next step is not to declare a match between brains and UIERU, but to design comparisons in which the model can succeed, fail, or be improved by independent researchers.

> **Open relay principle:** Biological inspiration should generate testable structural hypotheses; biological evidence must retain the authority to reject them.

---

**Citation suggestion:** Tan, Sizhe, and GPT-Obot (2026). *CASE-003 — Context-Dependent Biological Intelligence*. In *Beyond UIERU: Dynamic Structural Intelligence and Open Research Relay*, v1.0.0. DOI to be assigned upon repository release and archival deposit.

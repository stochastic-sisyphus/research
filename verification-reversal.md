# Verification Reversal
## Cascades and Synthetic Productivity in an AI-Mediated Economy

**Vanessa Beck**

Independent Researcher

[vanessa.beckk1@gmail.com](mailto:vanessa.beckk1@gmail.com)

ORCID: 0009-0008-6611-535X

GitHub: stochastic-sisyphus

Version 1.0 | January 2025

*Author disclosure: No external funding. No conflicts of interest.*

---

## Abstract

Generative AI lowers the marginal cost of producing plausible informational artifacts faster than it lowers the marginal cost of verifying them. When verification becomes the binding constraint, organizations rationally shift from checking to forwarding.

We formalize this **verification reversal** regime in a sequential forwarding game. When the cost gap between verification and forwarding exceeds the expected net benefit of catching errors, a **forwarding equilibrium** emerges: agents propagate artifacts regardless of private beliefs, producing information cascades and **information blockage**.

This shift creates a measurable wedge between **gross throughput** and **net verified output**. We call the resulting divergence between measured and verification-adjusted productivity **synthetic productivity**: conventional TFP can rise even as utility-relevant productivity stagnates, because verification effort and remediation burdens are omitted.

We also show how measurement systems can become **endogenously self-referential**: model-generated artifacts enter the substrates used for evaluation, slowing detection of genuine degradation and extending recognition lags.

Finally, we propose an empirical agenda with instrumentation baselines (notably a GitHub pull-request testbed) to measure verification intensity, remediation, cascade fragility, endogeneity of measurement substrates, and the accumulation of epistemic debt.

**Keywords:** Information cascades; Verification costs; Generative AI; Total factor productivity; Endogeneity; Epistemic debt.

**JEL Classification:** D83 (Search; Learning; Information); D85 (Network Formation and Analysis); O33 (Technological Change); E01 (Measurement and Data on National Income).

**Paper status:** Conceptual framework with testable predictions; full microfoundations are a planned extension.

---

## 1. Introduction

There is a particular kind of confidence that comes from watching a machine produce, in seconds, what once took hours. Code that compiles. Prose that scans as expert. Forecasts dressed in last quarter’s familiar format. Through the lenses we inherited, this reads as productivity: clean, unambiguous, almost divinely efficient.

But measurement systems encode assumptions about what they measure. One assumption sits quietly inside most productivity statistics: that producing an artifact requires cognitive work roughly proportional to the artifact’s complexity. More output meant more thinking. The link was never perfect, but it was stable enough to support decades of economic inference.

Generative AI has severed that link.

The marginal cost of *producing* a plausible artifact (code, analysis, report, forecast) has collapsed. The marginal cost of *verifying* whether that artifact is correct, reality-tracking, and safe to act on has not. In many domains it has risen, because the artifacts now require scrutiny they once did not, and the people capable of providing that scrutiny are being asked to do it at scale.

This paper studies what happens when generation becomes cheaper than verification. The result is not merely “more errors.” It is an equilibrium shift. Agents stop verifying. Cascades form. Measured productivity drifts away from verification-adjusted productivity. And the mechanisms that supposedly self-correct (recursive AI verification, market selection) are structurally weakened by the same dynamics they would need to reverse.

### 1.1 Paper Structure and Claims

This paper proceeds as follows:

**Model (Sections 3–4).** We formalize verification reversal as a cost inequality and derive a sequential forwarding game. *Proposition 1*: When verification costs exceed forwarding costs sufficiently, cascade equilibria emerge in which rational agents propagate unverified artifacts regardless of private beliefs.

**Goodhart Mechanism (Section 3.2).** We show why throughput becomes a target and verification becomes latent, collapsing the measurement regime under incentive pressure.

**Productivity Measurement (Sections 5–7).** We distinguish measured from verification-adjusted productivity and formalize epistemic debt as a stock variable. *Claim 1*: Under verification reversal, measured TFP can rise while utility-relevant productivity stagnates (synthetic productivity). *Claim 2*: Model-generated content can contaminate measurement substrates, extending recognition lags.

**Self-Correction Failure (Section 8).** We analyze recursive verification and market selection. We argue both mechanisms are weakened structurally because the cascade equilibrium is self-reinforcing on the signals that would guide correction.

**Empirical Agenda (Section 9).** We propose testable hypotheses with instrumentation baselines.

### 1.2 Key Definitions

**Status of claims (evidential hierarchy)**

- **Proposition 1 (Section 4.2):** formally derived from model primitives and payoff inequalities (proof sketch included).
- **Claims 1–2 (Sections 5–6):** derived implications under stated reduced-form assumptions. These are conditional predictions.
- **Selection mechanism (Section 8.3):** a verbal hypothesis with a schematic model and clear modeling gaps (entry/exit and capital isn’t fully specified).
- **Predictions / hypotheses (Section 9):** operationalizations intended to make the framework falsifiable.

> **Definition (Verification Reversal).** The regime in which the marginal cost of producing an artifact is lower than the marginal cost of verifying it, formally: ∂C_p/∂Y < ∂C_v/∂Y.
> 

> 
> 

> **Definition (Synthetic Productivity).** The appearance of output growth (rising measured TFP) when verification-adjusted, utility-relevant productivity stagnates or declines.
> 

> 
> 

> **Definition (Verification-Adjusted Productivity).** TFP computed using only verified artifacts, discounting unverified volume.
> 

> 
> 

> **Definition (Epistemic Debt).** The accumulated gap between system complexity and cognitive grasp: the stock of artifacts an organization relies upon but does not fully understand.
> 

> 
> 

> **Definition (Endogeneity Share).** The fraction of variance in key regressors attributable to model-generated content: α_t = Var(X_model,t) / Var(X_total,t).
> 

### 1.3 Contributions

This paper offers five contributions:

1. **A forwarding game under verification reversal** in which agents rationally propagate unverified artifacts, generating information blockage even as throughput metrics soar.
2. **A formal distinction between measured and verification-adjusted productivity**, showing how the gap can grow over time as verification capacity erodes.
3. **An endogeneity share parameter** measuring how model-mediated content enters measurement substrates.
4. **Structural conditions under which self-correction fails**: “AI verifies AI” lacks independent rejection signals when models share training distributions, and market selection operates on lagging proxies rather than latent verification stocks.
5. **A concrete empirical agenda** with testable hypotheses and instrumentation baselines.

### 1.4 Relation to Existing Literatures

The analysis braids together several threads: foundational work on informational cascades and social learning (Bikhchandani et al., 1992; Banerjee, 1992), emerging work on AI productivity measurement, econometric treatments of endogeneity (Wooldridge, 2010), and philosophical work on epistemic opacity and epistemic debt. Two additional influences structure the argument: Marvin Minsky’s *Society of Mind* (1986), which frames robust intelligence as requiring diverse, independently-failing processes; and Hyman Minsky’s *Financial Instability Hypothesis* (1986), which describes how stability itself breeds the conditions for crisis.

**What distinguishes this framework.** The novelty lies in three interacting mechanisms: (i) verification capacity is endogenous and erodes under sustained underuse, so organizations lose not just the time but the *ability* to verify; (ii) measurement substrates can become self-referential as model-generated content enters the data used to detect problems, extending recognition lags; and (iii) market selection operates on lagging proxies (throughput, velocity) rather than latent verification stocks, systematically selecting against high-verification strategies during stable periods. Erosion accelerates contamination, contamination extends detection lags, and selection pressure accelerates erosion.

### 1.5 How to Read This Paper

This paper occupies a middle ground between formal theory and measurement design. Sections 3–4 develop a stylized model with explicit assumptions and one formally derived proposition. Sections 5–8 present Claims 1–2 and the self-correction analysis as structured arguments that follow from the model if its premises hold. Section 9 translates predictions into testable hypotheses with concrete operationalizations.

### 1.6 Empirical Motivation

Three domains exhibit verification reversal dynamics with measurable consequences.

**Software development under AI assistance.** GitClear’s analysis of 153 million changed lines of code across 2020–2024 documents systematic quality shifts as AI code-generation tools scaled. Their 2024 report finds that short-horizon churn (lines reverted within two weeks of being written) increased substantially as AI-assisted commits grew, while “moved” code (a proxy for thoughtful refactoring) declined relative to copy/paste behavior (GitClear, 2024).

**Security vulnerability proliferation.** Multiple studies document elevated vulnerability rates in AI-generated code, with common weakness enumerations (CWEs) such as SQL injection, XSS, and hardcoded credentials appearing at higher frequencies than in human-written baselines (Pearce et al., 2022). These results are consistent with a verification-reversal mechanism: generation scales cheaply, while deep security review (threat modeling, misuse-case analysis, integration testing) does not.

**Knowledge work and analysis.** Qualitative reports from consulting, finance, and legal work describe a shift toward “light edit and forward” behavior, with deep verification increasingly reserved for a small share of high-stakes artifacts. Systematic measurement remains sparse, but the structure is the same: artifact volume rises while per-artifact verification time declines.

These cases share the same incentive geometry: throughput is visible, verification is costly, and the penalty for being wrong is lagged and often externalized.

---

## 2. Literature Review

### 2.1 Informational Cascades and Social Learning

The mathematics of herding was formalized before anyone imagined machines that could produce plausible text at scale. Bikhchandani, Hirshleifer, and Welch (1992) and Banerjee (1992) showed that rational agents observing predecessors’ actions can enter cascades where private signals are discounted and learning stops, even when private information remains informative. The mechanism is elegant: once the inferred weight of upstream behavior exceeds the informational value of one’s own signal, the rational move is to follow the crowd. Truth becomes irrelevant to the equilibrium.

These models treat observation costs and signal acquisition costs as primitives. This paper adapts the framework to a setting where generative AI has altered the cost structure in a specific way: verification has become expensive relative to production. The cascade dynamics remain, but the entry conditions have changed. When producing an artifact costs less than checking it, the threshold for cascade formation drops.

### 2.2 AI Productivity Measurement

Empirical studies document productivity gains from generative AI across knowledge-work tasks. Brynjolfsson et al. (2023) find that customer service agents using AI assistants resolve 14% more issues per hour, with gains concentrated among less-experienced workers. Peng et al. (2023) report that GitHub Copilot users completed coding tasks 55% faster in a controlled experiment. Noy and Zhang (2023) find that ChatGPT assistance reduced writing time for professional tasks by 40% while improving output quality as rated by evaluators.

The gains are real within the measurement frames employed. But the measurement frame matters.

Most studies emphasize output volume and short-horizon quality metrics without separately tracking verification bandwidth, downstream error remediation, or long-run maintenance costs. A programmer who ships twice as many lines of code per day has doubled productivity, unless those lines require three times as much review, generate twice as many bugs, and create maintenance burdens that compound for years.

A key gap in the literature is the absence of verification-adjusted productivity measures. The framework developed here provides a rationale for such adjustments and predicts that conventional productivity metrics systematically overstate welfare gains when verification costs dominate.

### 2.3 Endogeneity in Econometrics

Econometric theory has long grappled with endogeneity arising from omitted variables, measurement error, simultaneity, and selection. Textbook treatments (Wooldridge, 2010) provide the technical machinery for detection and correction when the problem is recognized.

In AI-mediated economies, a distinct channel emerges: regressors can themselves be model-generated and optimized for plausibility, breaking orthogonality between regressors and errors in ways that standard diagnostics may not detect.

### 2.4 Epistemic Opacity and Epistemic Debt

Work on epistemic opacity emphasizes that reliability must be argued through verification, validation, robustness testing, and track record. When systems become too complex for any single agent to comprehend, trust must be distributed across institutional processes. Those processes require maintenance.

In software development and AI-assisted work, *epistemic debt* describes how artifact production can outpace human comprehension, creating a growing divergence between system complexity and cognitive grasp. The concept parallels technical debt, but the currency is understanding rather than code quality.

---

## 3. When Generation Becomes Cheaper than Verification

The defining condition is simple to state and difficult to escape once it binds.

Let Y denote artifact volume per period. Let C_p(Y) and C_v(Y) be the costs of producing and verifying that volume.

> **Definition (Verification Reversal).** The verification reversal regime begins when:
> 

> 
> 

> ∂C_p/∂Y < ∂C_v/∂Y
> 

The inequality need not hold universally. It suffices that for a substantial class of “good enough” artifacts (the kind that clear immediate review, satisfy surface criteria, and raise no obvious flags) incremental production is easier than incremental verification.

### 3.0 Scope Conditions: Where Verification Reversal Binds

This paper is **not** claiming that verification is always expensive or always human-bound. The regime is defined by *artifact classes* where cheap automated verification does not bind.

**Artifact classes where cheap automated verification often does not bind:**

- **Open-ended analysis artifacts:** memos, forecasts, policy briefs, research notes, “exec-ready” narratives.
- **Socio-technical decision artifacts:** requirements, incident retros, risk assessments, compliance narratives.
- **Software artifacts beyond compile/test:** architecture changes, security properties, long-run maintainability, integration behavior.
- **Measurement substrates:** dashboards, metrics pipelines, benchmark construction, and documentation that later become ground-truth inputs.

**Artifact classes where cheap automated verification can bind (limiting cases):**

- Artifacts with **tight formal contracts** (types, proofs, model checking).
- Artifacts with **high-coverage automated tests** and fast ground-truth feedback.
- Low-volume, high-stakes domains with enforced audit gates.

### 3.1 Verification Cost Non-Linearity

Verification cost exhibits non-linearities. As artifact volume Y scales, verification cost per artifact can rise due to cognitive fatigue and needle-in-a-haystack dynamics. Define:

C_v(Y) = c₀Y + c₁Y^α + c₂f(Y/H)

where c₀Y is baseline linear cost, c₁Y^α with α > 1 captures fatigue effects, and c₂f(Y/H) captures increasing error-detection difficulty as signal-to-noise declines (H is human verification bandwidth).

### 3.2 The Goodhart Linkage: Throughput as Target, Verification as Latent

When **throughput metrics** (Y, velocity, tickets closed, artifacts shipped) become targets, they stop being useful measures of welfare-relevant productivity.

Under verification reversal, verification quality (v) is typically **latent** and remediation burden (R) is **lagged**. This induces a Goodhart-style collapse of the measurement regime:

- Managers optimize the observable: Y.
- The system draws down the unobserved: v and verification skill.
- The bill appears later: R (rework, incidents, reversions), sometimes only at crisis.

*Interpretation:* verification erosion is not just “mistakes happen.” It is a measurement regime failing under incentive pressure.

---

## 4. A Forwarding Game and Rational Cascades

Consider a workflow as a sequence of agents: i = 1, 2, …, N. An artifact enters at one end and passes through hands until it exits as a decision, a deployment, a publication, a commitment. At each position, the agent faces a choice:

- **Verify:** incur cost C_v to check the artifact against independent criteria.
- **Forward:** pass it on with minimal scrutiny at cost C_f, where C_f << C_v.

### 4.1 Model Primitives

**State space.** Each artifact has a true state ω ∈ {valid, invalid}, drawn with prior P(valid) = q₀.

**Information structure.** Agent i receives a private signal s_i ∈ {good, bad} with precision P(s_i = good | valid) = P(s_i = bad | invalid) = p > 0.5. Agent i also observes the sequence of actions a₁, …, a_{i-1}.

**Actions.** Agent i chooses a_i ∈ {Verify, Forward}.

**Payoffs.** If agent i verifies:

- Cost: C_v
- Benefit: if the artifact is invalid and caught, agent i receives B (avoiding downstream error costs)

If agent i forwards:

- Cost: C_f
- If the artifact is invalid and causes downstream harm, agent i bears expected cost λD where λ is the probability of attribution and D is reputational/organizational damage.

### 4.2 The Forwarding Condition

Agent i forwards if verification’s expected net benefit is below its cost gap:

C_v - C_f > (1 - μ_i) · (B - λD)

Let B_net = B - λD. Rearranging:

> **Proposition 1 (Forwarding Threshold).** Agent i forwards if and only if:
> 

> 
> 

> μ_i > 1 - (C_v - C_f) / B_net
> 

> 
> 

> When C_v - C_f ≥ B_net, the threshold is non-positive, so the condition holds for all μ_i ∈ [0,1]: agents forward regardless of beliefs.
> 

*Proof sketch.* Follows directly from expected utility comparison.

**Cascade formation.** Once forwarding becomes optimal regardless of s_i, the action conveys no information. The cascade is absorbing: once entered, it cannot be exited by any single agent’s deviation.

### 4.3 Information Blockage

> **Definition (Information Blockage).** A state in which observed actions are uninformative about artifact validity: the mutual information between the action sequence (a₁, …, a_n) and the true state ω approaches zero, even as throughput remains high.
> 

---

## 5. Synthetic Productivity and Regime Misidentification

At the macro level, total factor productivity (TFP) is typically computed as:

TFP_t^measured = Y_t / F(K_t, L_t)

### 5.0 A Canonical Productivity Wedge Estimand

Let:

- Y be gross artifact output (throughput).
- v ∈ [0,1] be the effective verification rate.
- R be remediation cost (rework, incident response, rollback, downstream correction).

> **Definition (Net Verified Output).** Net Verified Output ≔ Y · v − R
> 

> 
> 

> **Definition (Synthetic Productivity).** Δ ≔ Y − (Y · v − R)
> 

Under verification reversal, Y can grow independently of verified value creation.

> **Claim 1 (Synthetic Productivity).** Under volume–value decoupling, measured TFP rises while verification-adjusted TFP stagnates or declines.
> 

---

## 6. Endogenous Measurement: Models Eating Their Own Outputs

Econometric analysis often assumes:

Y_t = βX_t + ε_t with E[X_t ε_t] = 0

In an AI-mediated economy, the data used to construct X_t increasingly include model-generated artifacts. Write:

X_t = X_h,t + X_m,t

where X_h,t is human- or sensor-grounded content and X_m,t is model-mediated content.

OLS bias is driven by the correlation term, not by variance share alone:

β̂_OLS = β + Cov(X_t, ε_t) / Var(X_t)

### 6.1 Endogeneity Share (Exposure)

> **Definition (Endogeneity Share).** α_t = Var(X_m,t) / Var(X_t)
> 

α_t measures **exposure**: how much of the substrate is model-mediated. It is not itself bias.

### 6.2 When Exposure Becomes Bias (Directionality Conditions)

Bias emerges when model-mediated content is systematically wrong in ways correlated with outcomes:

Cov(X_m,t, ε_t) ≠ 0

This occurs under at least three concrete mechanisms:

1. **Optimization for acceptance under proxy incentives.** When organizations reward “looks right” or “clears review,” model outputs are selected for plausibility, not truth. Selection pressure can induce directional errors aligned with the proxy objective (e.g., smoothing toward the expected trend; reducing variance; overconfidence in favored narratives).
2. **Benchmark and evaluation gaming / contamination.** If X includes evaluation artifacts (benchmarks, rubric-scored outputs, “quality” labels) that models indirectly influence or learn, then X_m,t inherits the model’s inductive biases. Errors become correlated with ε_t because the same model family shapes both regressor construction and the underlying process generating outcomes.
3. **Distributional blind spots.** Under shifts where tail events matter (rare failures, security vulnerabilities, adversarial behavior), models can be directionally wrong in the tails. If outcomes ε_t are driven by tail events, then X_m,t (which smooths tails) becomes correlated with ε_t.

### 6.3 Recognition Lag Extension

Let τ be expected time-to-detection of genuine misalignment between model-mediated measurement and reality.

> **Claim 2 (Recognition Lag Extension).** Holding true degradation fixed, increasing α_t can increase τ when model-mediated substrates suppress residual visibility or reduce the probability of collecting independent ground truth.
> 

*Interpretation:* as the measurement apparatus becomes self-referential, problems take longer to surface and have more time to compound.

---

## 7. Verification-Adjusted Productivity and the Verification Treadmill

Define verification-adjusted utility as:

V(Y, θ) = ∫₀^Y v(y, θ) dy

Measured vs. verification-adjusted productivity:

TFP_t^measured = Y_t / F(K_t, L_t)

TFP_t^actual = V(Y_t, θ_t) / F(K_t, L_t)

### 7.1 The Verification Treadmill

A reduced-form representation:

v(Y, θ) = θ · g(Y/θ), g′(·) < 0

> **Prediction 1 (Wedge Growth).** If dY_t/dt > 0 while dθ_t/dt ≤ 0, then d/dt(TFP_t^measured − TFP_t^actual) > 0.
> 

### 7.2 Epistemic Debt as a Stock

Let C_s(t) be complexity (or volume) of epistemically loaded artifacts and G_c(t) be cognitive grasp (a function of verification capacity θ_t and verification skill κ_t).

> **Definition (Epistemic Debt).** D_e(T) = ∫₀^T (C_s(t) − G_c(t)) dt
> 

### 7.3 Synthetic Productivity as a Drawdown of Epistemic Capital

A separate, compounding channel matters for the long-run measurement substrate.

If successive model generations are trained on model-generated (synthetic) data, the system can *consume* the epistemic capital embedded in the historical corpus of human-generated, reality-anchored information. Shumailov et al. (2024) show that indiscriminate recursive training on model-generated content induces “model collapse,” with low-probability tails disappearing and learned behavior converging toward degenerate distributions over generations.

Within this framework, the mapping is direct:

- Higher α_t (model-mediated substrate share) increases the probability that “ground truth” inputs become self-referential.
- Self-referential substrates reduce tail sensitivity and anomaly visibility.
- Reduced tail sensitivity increases the likelihood that verification reversal persists, because fewer failures are detected early enough to trigger reinvestment in verification capacity.

*Interpretation:* synthetic productivity can look like a permanent efficiency gain while it is quietly drawing down a finite stock of epistemic capital (and making future verification harder).

---

## 8. Why Self-Correction Mechanisms Fail

Two self-correction arguments dominate optimistic discourse. The first: AI will verify AI, lowering verification costs. The second: market selection will weed out low-verification strategies.

Both mechanisms are structurally weakened when verification reversal holds, because the cascade equilibrium is self-reinforcing on the signals that would guide correction.

### 8.1 Recursive Verification and Correlated Error

Effective verification requires an independent rejection signal.

> **Definition (Independent Rejection Signal).** A verification procedure V provides an independent rejection signal for generator G if, conditional on G’s surface features, V’s rejection event is not driven by those same features.
> 

Cross-model error correlation (ρ) is a proxy for independence failure.

### 8.2 The Double Minsky Framework

Marvin Minsky emphasizes robustness through diverse, independently failing processes. Hyman Minsky emphasizes that stability breeds instability. Under verification reversal, recursive AI verification can create fluent consensus without truth-sensitivity, while stable-looking throughput regimes draw down verification capacity and build epistemic leverage.

### 8.3 Market Selection on Lagging Indicators (Verbal Hypothesis + Toy Sketch)

Let observable performance be π_t (throughput, velocity) and let latent verification stock be θ_t.

During stable periods:

π_t = f(Y_t) with ∂f/∂Y > 0 and ∂f/∂θ ≈ 0

A minimal two-type sketch:

- Type H (high verification): chooses (Y_H, θ_H) with lower Y but higher θ.
- Type L (low verification): chooses (Y_L, θ_L) with higher Y but lower θ.

Assume investors/markets allocate resources using observable π and do not price θ pre-crisis. Then Type L expands in market share in stable periods because it dominates on π.

Let crises arrive with hazard h(D_e/θ) increasing in epistemic leverage (debt per verification capacity). In crises, Type H has lower loss. But if crisis arrival is sufficiently rare relative to the competitive advantage of higher π, Type H can still be selected against pre-crisis.

*Interpretation:* selection can favor low-verification strategies when the payoff-relevant variable is latent and only revealed at forcing events.

---

## 9. Empirical Hypotheses and Instrumentation

Theory without measurement is philosophy. This section operationalizes the framework into testable hypotheses and instrumentation baselines. The goal is not to “prove” verification reversal, but to define measurable objects that could falsify it.

### 9.0 One MVP Testbed (Immediate Feasibility)

**Public GitHub repositories + pull request metadata**

- **Y (throughput):** commits, lines changed, PRs merged.
- **v (verification intensity proxy):** review depth (review duration, substantive comments, requested changes), number of revision cycles.
- **R (remediation):** churn/reverts, bug-fix PR share, rollback commits, incident-linked fixes.

This is deliberately minimal: it provides a concrete place to start measuring the wedge implied by synthetic productivity, and it directly connects to existing evidence on AI-assisted codebase quality shifts (GitClear, 2024).

### Testable Predictions (Summary)

1. The wedge between measured and verification-adjusted productivity grows over time (H1).
2. Cascade fragility increases with coupling and chain length (H2).
3. Endogeneity share in measurement substrates rises over time (H3).
4. Feedback loops exhibit learning collapse as incidents stop changing processes (H4).
5. Verification capacity and capability erode under sustained underuse (H5).
6. Organizational language converges toward model-preferred distributions (H6).
7. Irreversible lock-in accumulates through tool deprecation and skill-pipeline changes (H7).

### 9.1 H1: Divergence Between Measured and Verification-Adjusted Productivity

**Hypothesis:**

d/dt(TFP_t^measured − TFP_t^actual) > 0

**Operational objects:**

- **Throughput (Y):** artifact volume per period.
- **Verification intensity proxy (v):** review depth, audit coverage, validation lag.
- **Correction burden (R):** rework hours, incident remediation, rollbacks, defect density.

**Falsification condition:** Correction burden grows slower than (or equal to) throughput gains *and* verification intensity remains stable.

### 9.2 H2: Cascade Fragility Increases with Coupling and Length

**Hypothesis:**

∂²Fragility / (∂NetworkDensity · ∂CascadeLength) > 0

**Operational objects:**

- **Handoff network:** creator → reviewer → approver → deployer.
- **Propagation distance:** hops survived before detection.
- **Coupling proxies:** dependency graph density, shared reviewers, shared templates.

### 9.3 H3: Rising Endogeneity Share in Measurement Substrates

**Hypothesis:**

dα_t/dt > 0

**Operational objects:**

- **Provenance tagging:** human vs model vs sensor.
- **Endogeneity share:** α_t = Var(X_model,t) / Var(X_total,t).

**Note:** α_t measures exposure. Bias is governed by Cov(X_model,t, ε_t) (Section 6).

### 9.4 H4: Learning Collapse in Feedback Loops

**Hypothesis:** Learning efficiency decays toward zero:

dL_t/dt < 0 with L_t → 0

where L_t can be proxied by the ratio of durable process/tooling changes to incidents.

### 9.5 H5: Erosion of Verification Capacity and Capability

**Hypothesis:**

dθ_t/dt ≤ 0 and dκ_t/dt < 0

where θ is verification capacity (labor/time/tooling) and κ is verification capability (skill/accuracy).

A concrete, falsifiable capability test is **seeded defect detection** (inject known bugs and track detection rates over time). This directly targets failure modes documented in evaluations of AI-assisted coding security (Pearce et al., 2022).

### 9.6 H6: Language and Abstraction Convergence

**Hypothesis:**

dγ_t/dt > 0 and ∂Fragility/∂γ > 0

where γ_t measures coupling between internal language and model-preferred distributions (e.g., template similarity, phrase entropy reduction, boilerplate share).

### 9.7 H7: Irreversibility and Lock-In

**Hypothesis:**

dL_t/dt > 0

where L_t is a lock-in stock driven by tool deprecation, gate removal, and skill-pipeline changes.

---

## Appendix A: Instrumentation Details

### A.1 H1: TFP Divergence — Detailed Measurement

**Artifact throughput measures (Y):**

- Reports produced per analyst per week
- Code commits and lines changed per developer
- Ticket closure rate and time-to-close
- Forecast volume and update frequency
- Dashboard creation and modification rates

**Validation / verification measures (v proxies):**

- Time from artifact creation to first substantive review
- Fraction of artifacts receiving deep review vs. light edit
- Review queue depth and wait times
- Audit completion rates and coverage

**Correction burden measures (R):**

- Rework hours per initial artifact hour
- Incident remediation costs (labor + downtime)
- Rollback frequency and scope
- Post-deployment defect density
- Customer-reported error rates and severity distribution

Note that time spent reading code vs. writing it typically follows a 10:1 ratio (Martin, 2008); AI assistants optimize the writing phase while potentially increasing cognitive load in verification.

**Implementation sketch:** Pair production logs with review/correction logs and compute an estimand of the wedge (Δ) over time.

### A.2 H2: Cascade Fragility — Network Analysis

**Handoff network construction:**

- Map workflow: who creates → who reviews → who approves → who deploys
- Edge weight: frequency and volume of artifact transfers
- Node properties: verification capacity, throughput, position in chain

**Propagation distance:**

- Inject synthetic errors at known positions
- Track hops before detection
- Compare by error type and artifact class

**Correlated failure analysis:**

- Trace provenance backward from detected failures
- Test whether adjacent nodes exhibit correlated error patterns

### A.3 H3: Endogeneity Share — Data Provenance Tracking

**Lineage flags:**

- Tag all data inputs as: human-generated, model-generated, sensor/ground-truth
- Track provenance through transformation pipelines
- Measure the fraction of key regressors with model-generated ancestry

**Substrate share calculation:**

- Decompose: X_t = X_human,t + X_model,t + X_sensor,t
- Compute: α_t = Var(X_model,t) / Var(X_t)

**Benchmark contamination checks:**

- Test whether evaluation datasets contain model-generated content
- Monitor overlap between model outputs and measurement inputs

### A.4 H4: Learning Collapse — Feedback Loop Closure

**Postmortem linkage:**

- Count incidents → track postmortems → measure policy/process changes
- Compute: Process changes / Incidents over time

**Recurrence rate:**

- Classify incidents by root cause
- Measure: Repeat incidents / Total incidents

**Gate coverage:**

- Enumerate validation checkpoints in workflows
- Measure: Artifacts passing through gates / Total artifacts

### A.5 H5: Verification Capacity and Capability — Stock Measurement

**Capacity metrics (θ proxies):**

- Verification labor hours as share of total production hours
- Headcount in review, audit, QA, and validation roles
- Budget allocated to verification infrastructure
- Tool coverage: fraction of artifacts passing through automated checks

**Capability metrics (κ):**

- Time-to-competent-review for novel artifact types
- Seeded defect detection rate (inject known errors; measure catch rate)
- Review accuracy under controlled conditions

This is where AI-generated-code security findings become directly testable under an institutional lens (review pipelines as measurement devices), rather than only as model eval artifacts (Pearce et al., 2022).

### A.6 H6: Language Convergence — Semantic Drift Analysis

**Jargon overlap:**

- Compare internal documents to a reference corpus (proxy for model-preferred phrasing)
- Measure phrase frequency drift and template similarity

**Template convergence:**

- Track boilerplate share and structural entropy reduction

**Acceptance friction:**

- Compare review time and rejection rates for model-generated vs human-generated artifacts

### A.7 H7: Irreversibility and Lock-In — Institutional Commitment Tracking

**Tool deprecation:**

- Track removal of manual verification tools
- Measure availability of non-AI validation pathways

**Skill pipeline:**

- Track hiring criteria (verification skills vs throughput skills)
- Monitor training investment and promotion patterns in verification functions

**Architectural commitments:**

- Count removal of validation gates and approval steps
- Track adoption of auto-merge / auto-deploy workflows
- Track integration depth (how many systems depend on model-mediated inputs)

---

## 10. Discussion and Implications

### 10.1 Implications for Measurement

Productivity statistics that ignore verification costs and epistemic debt do not measure what they claim to measure. A verification-adjusted framework would track verification capacity as an asset, epistemic debt as a liability, and correction burden as a cost.

### 10.2 Implications for Institutional Design

Verification capacity should be treated as critical infrastructure: maintained, invested in, protected from quarterly optimization pressures.

### 10.3 Implications for AI Development

Heterogeneity in models, training distributions, and verification methods reduces correlated failure risk. A monoculture of frontier models trained on similar data and objectives is a fragility multiplier.

### 10.4 Adversarial Dynamics (Attack Surface)

Verification reversal creates an **attack surface**. Adversaries can cheaply generate artifacts optimized for plausibility and forwarding, targeting reviewer bottlenecks and the proxies institutions use for legitimacy. This shifts the story from “verification lapses” to a joint regime of bounded verification plus strategic manipulation.

Maintaining diverse verification channels (humans with different expertise, models with distinct training data, formal methods where applicable) is not optional resilience. It is a security control.

### 10.5 Limitations and Scope Conditions

This framework applies when verification costs exceed production costs for a substantial class of artifacts. It is limited in domains with tight formal contracts, high-coverage automated tests, low-volume high-stakes decisions with enforced audit gates, or fast and unambiguous feedback loops.

The computational substrate also imposes physical constraints—data center electricity consumption is projected to double by 2026 (IEA, 2024)—suggesting synthetic productivity may face resource limits independent of verification dynamics.

---

## 11. Conclusion

Verification reversal changes equilibrium behavior and the meaning of measured output. When generation becomes cheaper than verification, agents rationally cascade. Measured productivity diverges from verification-adjusted productivity. Measurement systems become self-referential. Self-correction mechanisms are weakened.

The dashboard can stay green while epistemic debt compounds in the dark. When the forcing event arrives, when reality demands validation that cannot be forwarded, the bill comes due.

Reality is not free.

---

## Acknowledgments

The “Double Minsky” framework in this paper owes an obvious debt to both Marvin Minsky and Hyman Minsky. The parallel was first noticed (as many things are) in conversation with a cat named Marvin.

---

## References

Banerjee, A. V. (1992). A simple model of herd behavior. *The Quarterly Journal of Economics*, 107(3), 797–817.

Bikhchandani, S., Hirshleifer, D., & Welch, I. (1992). A theory of fads, fashion, custom, and cultural change as informational cascades. *Journal of Political Economy*, 100(5), 992–1026.

Brynjolfsson, E., Li, D., & Raymond, L. R. (2023). Generative AI at work. *NBER Working Paper No. 31161*.

GitClear (2024). *Coding on Copilot: 2023 Data Suggests Downward Pressure on Code Quality*. Technical Report. https://www.gitclear.com

International Energy Agency (2024). *Electricity 2024: Analysis and Forecast to 2026*. IEA, Paris. https://www.iea.org

Martin, R. C. (2008). *Clean Code: A Handbook of Agile Software Craftsmanship*. Prentice Hall.

Minsky, H. P. (1986). *Stabilizing an Unstable Economy*. Yale University Press.

Minsky, M. (1986). *The Society of Mind*. Simon & Schuster.

Noy, S., & Zhang, W. (2023). Experimental evidence on the productivity effects of generative artificial intelligence. *Science*, 381(6654), 187–192.

Pearce, H., Ahmad, B., Tan, B., Dolan-Gavitt, B., & Karri, R. (2022). Asleep at the keyboard? Assessing the security of GitHub Copilot’s code contributions. *2022 IEEE Symposium on Security and Privacy (SP)*, 754–768.

Peng, S., Kalliamvakou, E., Cihon, P., & Demirer, M. (2023). The impact of AI on developer productivity: Evidence from GitHub Copilot. *arXiv preprint arXiv:2302.06590*.

Shumailov, I., Shumaylov, Z., Zhao, Y., Papernot, N., Anderson, R., & Gal, Y. (2024). AI models collapse when trained on recursively generated data. *Nature*, 631, 755–759.

Wooldridge, J. M. (2010). *Econometric Analysis of Cross Section and Panel Data* (2nd ed.). MIT Press.

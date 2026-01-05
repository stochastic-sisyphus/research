# Verification Reversal: Cascades and Synthetic Productivity in an AI-Mediated Economy

**Vanessa Beck**

Independent Researcher  
vanessa.beckk1@gmail.com  
ORCID: 0009-0008-6611-535X  
GitHub: stochastic-sisyphus

Version 1.0 | January 2025

*Author disclosure: No external funding. No conflicts of interest.*

---

## Abstract

Generative AI has pushed the marginal cost of producing informational artifacts below the marginal cost of verifying them. This paper studies the resulting *verification reversal* regime and its consequences for information quality, productivity measurement, and institutional stability.

**Mechanism.** A sequential forwarding game shows that when verification costs exceed production costs, rational agents propagate unverified artifacts, forming information cascades even as throughput metrics rise.

**Results.** We derive conditions under which (1) measured total factor productivity diverges from verification-adjusted productivity, a pattern we term *synthetic productivity*; (2) model-generated data contaminate econometric feedback loops, extending recognition lags; and (3) two standard self-correction arguments (recursive AI verification and market selection) fail structurally.

**Measurement.** We propose instrumentation strategies for verification capacity, endogeneity share, cascade fragility, and epistemic debt.

**Implications.** Conventional productivity statistics may systematically overstate welfare gains from generative AI by ignoring verification costs and epistemic debt accumulation.

**Keywords:** Information cascades; Verification costs; Generative AI; Total factor productivity; Endogeneity; Epistemic debt.

**JEL Classification:** D83 (Search; Learning; Information); D85 (Network Formation and Analysis); O33 (Technological Change); E01 (Measurement and Data on National Income).

**Paper status:** Conceptual framework with testable predictions; formal microfoundations are a planned extension.

---

## 1. Introduction

There is a particular kind of confidence that comes from watching a machine produce, in seconds, what once took hours. Code that compiles. Prose that scans as expert. Forecasts dressed in last quarter's familiar format. Measured through the lenses we inherited, this looks like productivity: pure, unambiguous, a gift from the efficiency gods.

But measurement systems encode assumptions about what they measure. The assumption embedded in most productivity metrics is older than it appears: that producing an artifact requires cognitive work roughly proportional to the artifact's complexity. More output, more thinking. The link was never perfect, but it was robust enough to anchor decades of economic inference.

Generative AI has severed that link.

The marginal cost of *producing* a plausible artifact (code, analysis, report, forecast) has collapsed. The marginal cost of *verifying* whether that artifact is correct, coherent with reality, safe to act upon? That cost has not collapsed. In many domains it has risen, because the artifacts now require scrutiny they once did not need, and the humans who might provide that scrutiny are drowning in volume.

This paper studies what happens when generation becomes cheaper than verification. The answer is not merely "more errors." The answer is a regime shift in equilibrium behavior: rational agents stop verifying, information cascades form, measured productivity diverges from actual productivity, and the mechanisms that might self-correct (recursive AI verification, market selection) turn out to be structurally compromised by the very dynamics they would need to correct.

### 1.1 Paper Structure and Claims

This paper proceeds as follows:

**Model (Sections 3-4).** We formalize verification reversal as a cost inequality and derive a sequential forwarding game. *Proposition 1*: When verification costs exceed production costs for a substantial artifact class, cascade equilibria emerge in which rational agents propagate unverified artifacts regardless of private beliefs.

**Productivity Measurement (Sections 5-7).** We distinguish measured from verification-adjusted productivity and formalize epistemic debt as a stock variable. *Claim 1*: Under verification reversal, measured TFP can rise while utility-relevant productivity stagnates (synthetic productivity). *Claim 2*: Model-generated content contaminates measurement substrates, extending recognition lags.

**Self-Correction Failure (Section 8).** We analyze recursive verification and market selection. *Conjecture*: Both mechanisms fail structurally because the cascade equilibrium is self-reinforcing on the signals that would guide correction.

**Empirical Agenda (Section 9).** We propose seven testable hypotheses with instrumentation baselines.

### 1.2 Key Definitions

To ensure precision, we define terms that will be used consistently throughout:

> **Definition (Verification Reversal).** The regime in which the marginal cost of producing an artifact is lower than the marginal cost of verifying it, formally: ∂C_p/∂Y < ∂C_v/∂Y.

> **Definition (Synthetic Productivity).** The appearance of output growth (rising measured TFP) when verification-adjusted, utility-relevant productivity stagnates or declines.

> **Definition (Verification-Adjusted Productivity).** TFP computed using only verified artifacts, discounting unverified volume.

> **Definition (Epistemic Debt).** The accumulated gap between system complexity and cognitive grasp: the stock of artifacts an organization relies upon but does not fully understand.

> **Definition (Endogeneity Share).** The fraction of variance in key regressors attributable to model-generated content: α_t = Var(X_model,t) / Var(X_total,t).

### 1.3 Contributions

This paper offers five contributions:

1. **A forwarding game under verification reversal** in which agents rationally propagate unverified artifacts, generating information blockage even as throughput metrics soar.

2. **A formal distinction between measured and verification-adjusted productivity**, showing how the gap can grow over time as verification capacity erodes.

3. **An endogeneity share parameter** measuring how model-generated content contaminates the econometric substrates we use to detect problems.

4. **Structural conditions under which self-correction fails**: "AI verifies AI" lacks independent rejection signals when models share training distributions, and market selection operates on lagging indicators.

5. **A concrete empirical agenda** with testable hypotheses and instrumentation baselines.

### 1.4 Relation to Existing Literatures

The analysis braids together several intellectual threads: foundational work on informational cascades and social learning (Bikhchandani et al., 1992; Banerjee, 1992), the emerging literature on AI productivity measurement, econometric treatments of endogeneity (Wooldridge, 2010), and philosophical work on epistemic opacity and epistemic debt. Two additional influences structure the argument: Marvin Minsky's *Society of Mind* (1986), which frames robust intelligence as requiring diverse, independently-failing processes; and Hyman Minsky's *Financial Instability Hypothesis* (1986), which describes how stability itself breeds the conditions for crisis.

**What distinguishes this framework.** This is not merely "cascades with AI." The novelty lies in three structural claims: (i) verification capacity is endogenous and erodes under sustained underuse, so organizations lose not just the time but the *ability* to verify; (ii) measurement substrates become endogenously contaminated as model-generated content enters the data used to detect problems, extending recognition lags through a feedback loop that standard econometric diagnostics may not detect; and (iii) market selection operates on lagging proxies (throughput, velocity) rather than latent verification stocks, systematically selecting out high-verification strategies during the accumulation phase when they would matter most. These three mechanisms interact: erosion accelerates contamination, contamination extends the lag before selection can correct, and selection pressure accelerates erosion.

### 1.5 How to Read This Paper

This paper occupies a middle ground between formal theory and empirical measurement. Sections 3-4 develop a stylized model with explicit assumptions and one formally derived proposition. Sections 5-8 present Claims 2-4 as derived implications under stated assumptions; these are not proven theorems but structured arguments that follow from the model if its premises hold. Section 9 translates theoretical predictions into testable hypotheses with concrete operationalizations. Readers seeking formal proofs should treat Claims 2-4 as conjectures awaiting fuller specification; readers seeking empirical guidance should focus on Section 9's instrumentation baselines. A companion paper developing full game-theoretic microfoundations is planned.

### 1.6 Empirical Motivation

Three domains exhibit verification reversal dynamics with measurable consequences:

**Software development under AI assistance.** GitClear's analysis of 153 million changed lines of code across 2020-2024 documents systematic quality shifts as AI code-generation tools scaled. Their 2024 report finds that "code churn" (lines reverted within two weeks of being written) increased substantially as AI-assisted commits grew, while "moved" code (the primary indicator of thoughtful refactoring) declined relative to "copy/paste" code (GitClear, 2024). The pattern suggests organizations optimized for throughput while verification infrastructure lagged.

**Security vulnerability proliferation.** Multiple studies document elevated vulnerability rates in AI-generated code, with common weakness enumerations (CWEs) including SQL injection, cross-site scripting, and hardcoded credentials appearing at higher frequencies than in human-written baselines (Pearce et al., 2022). The precise rates vary by model, prompt structure, and evaluation methodology, but the directional finding (that surface-plausible code can systematically embed security flaws) is robust across studies.

**Knowledge work and analysis.** Qualitative reports from consulting, financial research, and legal services describe a modal shift toward "light edit and forward" behavior, with deep verification increasingly reserved for high-stakes sections while routine artifacts pass through review with minimal scrutiny. Systematic measurement remains sparse, but the pattern (artifact volume rising while per-artifact verification time declines) appears across multiple knowledge-intensive sectors.

These cases share a structure: artifact production accelerated while verification capacity remained constant or declined, forwarding behavior increased, and error detection shifted downstream or post-deployment.

---

## 2. Literature Review

### 2.1 Informational Cascades and Social Learning

The mathematics of herding was formalized before anyone imagined machines that could produce plausible text at scale. Bikhchandani, Hirshleifer, and Welch (1992) and Banerjee (1992) showed that rational agents observing predecessors' actions can enter cascades where private signals are discounted and learning stops, even when private information remains informative. The mechanism is elegant: once the inferred weight of upstream behavior exceeds the informational value of one's own signal, the rational move is to follow the crowd. Truth becomes irrelevant to the equilibrium.

These models treat observation costs and signal acquisition costs as primitives. This paper adapts the framework to a setting where generative AI has altered the cost structure in a specific way: verification has become expensive relative to production. The cascade dynamics remain, but the entry conditions have changed. When producing an artifact costs less than checking it, the threshold for cascade formation drops.

Subsequent work has studied cascade fragility, network structure effects, and reversal conditions. The present work extends these insights by endogenizing verification as a scarce organizational input (one that erodes under sustained underuse) and linking cascade dynamics to macroeconomic productivity measurement.

### 2.2 AI Productivity Measurement

Empirical studies document productivity gains from generative AI across knowledge-work tasks. Brynjolfsson et al. (2023) find that customer service agents using AI assistants resolve 14% more issues per hour, with gains concentrated among less-experienced workers. Peng et al. (2023) report that GitHub Copilot users completed coding tasks 55% faster in a controlled experiment. Noy and Zhang (2023) find that ChatGPT assistance reduced writing time for professional tasks by 40% while improving output quality as rated by evaluators.

The gains are real within the measurement frame employed. But the measurement frame matters.

Most studies emphasize output volume and short-horizon quality metrics without separately tracking verification bandwidth, downstream error remediation, or long-run maintenance costs. A programmer who ships twice as many lines of code per day has doubled productivity, unless those lines require three times as much review, generate twice as many bugs, and create maintenance burdens that compound for years. The studies rarely track long enough to see the compounding.

A key gap in the literature is the absence of verification-adjusted productivity measures. The framework developed here provides a rationale for such adjustments and predicts that conventional productivity metrics systematically overstate welfare gains when verification costs dominate.

### 2.3 Endogeneity in Econometrics

Econometric theory has long grappled with endogeneity arising from omitted variables, measurement error, simultaneity, and selection. Textbook treatments (Wooldridge, 2010) provide the technical machinery for detection and correction when the problem is recognized.

In AI-mediated economies, a distinct channel emerges: regressors themselves can be model-generated and optimized for plausibility, breaking orthogonality between regressors and errors in ways that standard diagnostics may not detect. This endogeneity is not random noise. If systems are tuned to preserve plausible-looking relationships (because plausibility is what they optimize for), contrary signals are smoothed away and stability tests increasingly operate on self-referential substrates.

### 2.4 Epistemic Opacity and Epistemic Debt

Work on epistemic opacity in complex computation emphasizes that reliability cannot be assumed; it must be argued through verification, validation, robustness testing, and track record. When systems become too complex for any single agent to comprehend, trust must be distributed across institutional processes. Those processes require maintenance.

In software development and AI-assisted work, *epistemic debt* describes how artifact production can outpace human comprehension, creating a growing divergence between system complexity and cognitive grasp. The concept parallels technical debt, but the currency is understanding rather than code quality.

These ideas motivate treating verification capacity and verification skill as stocks that can erode under sustained underuse. An organization that stops verifying does not merely accumulate unverified artifacts; it loses the ability to verify.

### 2.5 Market Selection and Information

Classical arguments suggest markets reward accuracy and penalize error-prone strategies. Over time, the accurate survive and the sloppy fail. Selection pressure should drive the system toward truth.

The argument assumes selection acts on the relevant variable. But market selection operates on observable proxies, not latent verification stocks. An organization that maintains robust verification capacity incurs visible costs: slower throughput, higher headcount in review functions, longer time-to-ship. The benefits of that investment remain latent until a crisis reveals them, and crises are rare enough that careers end before vindication arrives.

High-verification firms are systematically selected out during the accumulation phase, precisely when their resilience would matter most. This is not a bug in the selection mechanism; it is the mechanism working as designed on the wrong objective.

---

## 3. When Generation Becomes Cheaper than Verification

The defining condition is simple to state and difficult to escape once it binds.

Let Y denote artifact volume per period. Let C_p(Y) and C_v(Y) be the costs of producing and verifying that volume.

> **Definition (Verification Reversal).** The verification reversal regime begins when:
>
> ∂C_p/∂Y < ∂C_v/∂Y

The inequality need not hold universally. It suffices that for a substantial class of "good enough" artifacts (the kind that clear immediate review, satisfy surface criteria, and raise no obvious flags) incremental production is easier than incremental verification.

Once this binds broadly, verification undergoes a reclassification. In the old regime, verification capacity read as *capability*: the mark of a rigorous organization, a feature to advertise, a competitive advantage. In the new regime, verification reads as *overhead*: a cost center, a drag on velocity, a bottleneck to be optimized away.

This reclassification follows from the incentive structure. When performance metrics reward throughput and the cost of verification is visible while the cost of *not* verifying remains latent, the rational actor prunes verification capacity. The organization that maintains robust checking loses to the organization that ships faster, until the forcing event that reprices the debt.

### 3.1 Verification Cost Non-Linearity

The verification cost function exhibits critical non-linearities. As artifact volume Y scales, verification cost per artifact rises due to cognitive fatigue and needle-in-a-haystack dynamics. Define:

C_v(Y) = c₀Y + c₁Y^α + c₂f(Y/H)

where c₀Y is the baseline linear cost, c₁Y^α with α > 1 captures fatigue effects (verification becomes harder as reviewers process more artifacts), and c₂f(Y/H) represents the increasing difficulty of finding errors as signal-to-noise ratio declines (H is human verification bandwidth).

*Interpretation*: This non-linearity implies that even if C_p remains constant, verification costs can explode as volume scales, accelerating the transition to cascade equilibria.

---

## 4. A Forwarding Game and Rational Cascades

Consider a workflow as a sequence of agents: i = 1, 2, ..., N. An artifact enters at one end and passes through hands until it exits as a decision, a deployment, a publication, a commitment. At each position, the agent holding the artifact faces a choice:

- **Verify**: Incur cost C_v to check the artifact against independent criteria.
- **Forward**: Pass it on with minimal scrutiny at cost C_f, where C_f << C_v.

### 4.1 Model Primitives

**State space.** Each artifact has a true state ω ∈ {valid, invalid}, drawn with prior P(valid) = q₀.

**Information structure.** Agent i receives a private signal s_i ∈ {good, bad} with precision P(s_i = good | valid) = P(s_i = bad | invalid) = p > 0.5. Agent i also observes the sequence of actions a₁, ..., a_{i-1} taken by predecessors.

**Actions.** Agent i chooses a_i ∈ {Verify, Forward}.

**Payoffs.** If agent i verifies:
- Cost: C_v
- Benefit: If the artifact is invalid and caught, agent i receives B (avoiding downstream error costs)
- If valid, no additional benefit beyond avoiding C_v

If agent i forwards:
- Cost: C_f
- If the artifact is invalid and causes downstream harm, agent i bears expected cost λD where λ is the probability of attribution and D is the reputational/organizational damage

**Belief updating.** Let μ_i = P(valid | s_i, a₁, ..., a_{i-1}) denote agent i's posterior belief. Under Bayesian updating, observing a forward from agent j provides information only if agent j's action was informative (i.e., not in a cascade).

**Equilibrium concept.** Perfect Bayesian Equilibrium: agents choose actions to maximize expected utility given beliefs, and beliefs are updated consistently with Bayes' rule where applicable.

### 4.2 The Forwarding Condition

Agent i forwards if the expected cost of verification exceeds the expected benefit:

C_v - C_f > [μ_i · 0 + (1 - μ_i) · B] - [(1 - μ_i) · λD]

Simplifying, agent i forwards when:

C_v - C_f > (1 - μ_i) · (B - λD)

Let B_net = B - λD denote the net benefit of catching an error (verification benefit minus expected cost if error propagates). Rearranging:

> **Proposition 1 (Forwarding Threshold).** Agent i forwards if and only if:
>
> μ_i > 1 - (C_v - C_f) / B_net
>
> When C_v - C_f ≥ B_net, the threshold is non-positive, so the condition holds for all μ_i ∈ [0,1]: agents forward regardless of beliefs about validity.

*Proof sketch.* The inequality follows directly from expected utility comparison. Under verification reversal, C_v - C_f is large. If this cost gap exceeds B_net (the net benefit of catching an error), then 1 - (C_v - C_f)/B_net ≤ 0, and the forwarding condition is satisfied for any posterior μ_i, including posteriors that place high probability on invalidity. Forwarding becomes the dominant action not because agents believe artifacts are valid, but because verification costs exceed the expected benefit of catching errors. ∎

**Cascade formation.** Once forwarding becomes the equilibrium action for agent i regardless of signal s_i, agent i's action conveys no information about the artifact's validity. Subsequent agents observe only that agent i forwarded, cannot infer whether s_i was good or bad, and face the same cost structure. The cascade is absorbing: once entered, it cannot be exited by any single agent's deviation.

### 4.3 Information Blockage

As forwarding becomes near-universal, actions lose informational content. Almost everyone forwards. Few agents perform deep checks. Observing a forward tells you nothing about validity, only that the previous agent faced the same incentives you face.

> **Definition (Information Blockage).** A state in which observed actions are uninformative about artifact validity: the mutual information between the action sequence (a_1, ..., a_n) and the true state ω approaches zero, even as throughput metrics remain high.

*Interpretation*: This is not collective irrationality. It is individual rationality aggregating to collective blindness. Each agent optimizes correctly given their local information and incentive structure. The system outcome is a cascade that no one chose and no one can unilaterally escape.

---

## 5. Synthetic Productivity and Regime Misidentification

At the macroeconomic level, total factor productivity (TFP) is typically computed as:

TFP_t^measured = Y_t / F(K_t, L_t)

where Y_t is measured output and F(·) is a production function of capital and labor.

The implicit assumption is that Y_t measures something real: value created, problems solved, decisions improved. When artifact volume served as a reasonable proxy for cognitive work, this assumption was defensible. A report took hours because it required hours of thinking. More reports meant more thinking. The proxy held.

Under verification reversal, the proxy breaks. Y_t increasingly reflects AI-generated artifacts rather than verified, utility-producing work. The production structure has shifted:

- **Old regime** (human-cognition constrained): Y_t = F(K_t, L_cognitive,t)
- **New regime** (compute constrained): Y_t = G(K_t, C_compute,t)

These are structurally different production functions with different bottlenecks, different scaling properties, and different meanings of "more output."

> **Definition (Regime Misidentification).** Applying old-regime inference rules to new-regime data, such that the econometrician sees productivity growth because the model cannot distinguish artifacts-that-required-thought from artifacts-that-required-tokens.

**Assumption (Volume-Value Decoupling).** Under verification reversal, artifact volume Y_t can increase while the fraction of artifacts that are verified (and thus reliably value-producing) declines. Formally: dY_t/dt > 0 while d(V(Y_t, θ_t)/Y_t)/dt < 0.

> **Claim 1 (Synthetic Productivity).** Under Volume-Value Decoupling, measured TFP rises while verification-adjusted TFP stagnates or declines:
>
> d(TFP^measured)/dt > 0  while  d(TFP^actual)/dt ≤ 0
>
> The productivity miracle is an accounting error waiting for an audit.

---

## 6. Endogenous Measurement: Models Eating Their Own Outputs

The problem deepens when we trace measurement data to their sources.

Econometric analysis assumes:

Y_t = βX_t + ε_t  with  E[X_t ε_t] = 0

The orthogonality condition requires that regressors be independent of the error term. In an AI-mediated economy, the data used to construct X_t increasingly include model-generated artifacts:

X_t = h(Model_t(Y_{t-1}, X_{t-1}, θ))

The model generates outputs that become inputs to the next period's measurements. Reports cite AI-generated analyses. Forecasts incorporate AI-generated forecasts. The data substrate becomes self-referential.

This induces endogeneity:

Cov(X_t, ε_t) ≠ 0

and the resulting OLS bias:

β̂_OLS = β + Cov(X_t, ε_t) / Var(X_t)

### 6.1 Endogeneity Share

Define the model-generated component of key regressors as X_model,t and the total as X_total,t.

> **Definition (Endogeneity Share).**
>
> α_t = Var(X_model,t) / Var(X_total,t)

As α_t → 1, diagnostics and stability tests are increasingly performed on data that has been filtered through the very models we are trying to evaluate.

Let τ represent expected time-to-detection of genuine misalignment between model outputs and reality.

**Assumption (Signal Degradation).** Detection of misalignment requires observing residuals ε_t that exceed a threshold. When regressors X_t contain model-generated components, the observed residuals are:

ε̃_t = ε_t - f(X_model,t, ε_t)

where f captures the smoothing effect of model-generated content on apparent errors. As α_t increases, the correlation between X_model,t and ε_t rises, reducing the variance of observable residuals.

> **Claim 2 (Recognition Lag Extension).**
>
> Under the Signal Degradation assumption, dτ/dα > 0.
>
> Higher endogeneity share extends recognition lags. Problems take longer to surface. By the time they surface, they have compounded.

*Intuition.* When models generate data that feeds back into measurement, they optimize for plausibility within the training distribution. Anomalies that would otherwise surface as large residuals get smoothed toward the mode. The signal that something is wrong becomes harder to detect, not because the underlying problem is smaller but because the measurement apparatus has been compromised.

---

## 7. Verification-Adjusted Productivity and the Verification Treadmill

Artifact volume is not welfare. The distinction matters.

Define verification-adjusted utility as:

V: ℝ⁺ × [0,1] → ℝ⁺,  V(Y, θ) = ∫₀^Y v(y, θ) dy

where θ is verification capacity and v(y, θ) ∈ [0,1] is the effective verification rate, the probability that artifact y has been checked against reality.

The gap between what we measure and what matters:

TFP_t^measured = Y_t / F(K_t, L_t)

TFP_t^actual = V(Y_t, θ_t) / F(K_t, L_t)

### 7.1 The Verification Treadmill

As outputs multiply, verification resources spread thinner. A simple representation:

v(Y, θ) = θ · g(Y/θ),  g'(·) < 0

The verification rate per artifact declines as the ratio of artifacts to verification capacity rises. This is not a contingent fact about current organizations; it is a structural property of the production function. Verification does not scale the way generation scales.

> **Prediction 1 (Wedge Growth).** If dY_t/dt > 0 while dθ_t/dt ≤ 0, then:
>
> d/dt(TFP_t^measured - TFP_t^actual) > 0

### 7.2 Epistemic Debt as a Stock

Let C_s(t) denote the complexity (or volume) of epistemically loaded artifacts: the systems, reports, codebases, and models that an organization relies upon but may not fully understand. Let G_c(t) denote the system's cognitive grasp: the capacity to verify, comprehend, and maintain those artifacts, a function of verification capacity θ_t and verification skill κ_t.

> **Definition (Epistemic Debt).**
>
> D_e(T) = ∫₀^T (C_s(t) - G_c(t)) dt

Under sustained underuse of verification tasks, verification skill decays:

dκ_t/dt < 0

The organization loses not merely the time to verify but the ability. Epistemic debt accumulates even when surface metrics remain positive, especially when surface metrics remain positive, because positive metrics reduce the perceived urgency of verification.

### 7.3 Synthetic Productivity as Non-Renewable Resource

*Interpretation*: If successive model generations are trained on synthetic data produced by predecessors, the system consumes the epistemic capital accumulated in the historical corpus of human-generated, verified information. Model collapse studies show that training on synthetic data leads to distribution shift where models forget tail events and over-index on probable outputs. In "replace" scenarios where human data is entirely replaced by synthetic data, performance degrades exponentially. This suggests current productivity gains depend on unreplaced stocks of verified human knowledge, a finite resource under active depletion.

---

## 8. Why Self-Correction Mechanisms Fail

Two self-correction arguments dominate optimistic discourse about AI-mediated information systems. The first: AI will verify AI, driving verification costs back down and restoring the old equilibrium. The second: market selection will weed out low-verification strategies over time, as errors accumulate and the careless fail.

Both arguments are structurally flawed. They fail not because of implementation details but because the cascade equilibrium is self-reinforcing on the very signals that would guide correction.

### 8.1 Recursive Verification and Correlated Error

Effective verification requires an independent rejection signal: a check that can say "no" for reasons unrelated to why the original system said "yes." When a radiologist reviews an X-ray, the radiologist's errors are largely independent of the machine's errors. The combination is more reliable than either alone.

When a language model reviews the output of another language model, the independence assumption fails. If generator and verifier share training distributions and optimization objectives, their errors correlate.

> **Definition (Cross-Model Error Correlation).**
>
> ρ_{M₁,M₂} = Cov(ε_{M₁}, ε_{M₂}) / (σ_{M₁} σ_{M₂})

Robust cross-verification requires ρ → 0. When ρ is high, agreement between models increases surface coherence without increasing truth-sensitivity. Two models agreeing tells you they agree. It does not tell you they are correct.

Current autoregressive language models optimize for cross-entropy minimization over text corpora: they learn to predict what comes next in sequences of human-generated text. This objective function rewards producing outputs that *look like* authoritative text, not outputs that *are* true. The training distribution is skewed toward polished, finalized, confident prose. The models learn the tone of authority because authority is a high-probability sequence in the training data. Epistemic humility ("I lack sufficient information; I should check before proceeding") is statistically rare in training corpora, so it is structurally underlearned.

When we stack "AI to verify AI" on top of "AI to generate," we do not automatically get verification. We often get the same attractor, twice: fluent consensus within the distribution.

### 8.2 The Double Minsky Framework

The parallel to two Minskys (Marvin and Hyman) illuminates the structural problem.

Marvin Minsky's *Society of Mind* frames robust intelligence as a coalition of diverse, specialized processes with distinct internal models and distinct error profiles. When processes disagree, the disagreement itself is information. The system learns from the conflict. Effective verification requires precisely this: independent error modes that fail for different reasons.

Using one frontier generative model to verify another violates this requirement. It is not a second opinion; it is a statistical monoculture. When models share training data, objectives, architectures, and evaluation incentives, their errors correlate. Under high correlation, recursive verification becomes *recursive dilution*: each additional check increases confidence without increasing accuracy. Truth is displaced by consensus-within-the-distribution.

This creates a structural parallel to Hyman Minsky's *Financial Instability Hypothesis*. In Minsky's framework, stability breeds instability: long periods without crisis encourage leverage, and leverage makes the eventual crisis worse. Organizations can enter a "Ponzi" stage of financing where apparent assets are backed by borrowed credibility rather than fundamental value.

*Interpretation (Ponzi Stage of Information Production).* Organizations can enter a regime where apparent epistemic assets (reports, analyses, forecasts, decisions) are financed by borrowed credibility. Professional polish functions as collateral within internal reporting systems. The system looks stable in the indicators because the indicators measure coherence, not correctness. The cost of verification remains higher than the expected penalty for being wrong, until a forcing event makes the gap non-forwardable.

### 8.3 Market Selection on Lagging Indicators

Let π_t be an observable performance metric: throughput, velocity, time-to-ship, artifacts-per-quarter. Let verification-adjusted utility remain latent, unobservable until crisis. During the cascade regime:

π_t = f(Y_t, θ_{t-ℓ})  with  ∂f/∂Y > 0,  ∂f/∂θ ≈ 0

Observable performance improves with artifact volume. Verification capacity has approximately zero effect on observable performance, until the forcing event that reveals the gap.

For markets to correct the cascade, epistemic debt must be priced before it is called. But market selection operates on observable signals. When the wedge Y^measured - V(Y, θ) remains unobservable pre-crisis, selection mechanically favors high-Y, low-θ strategies.

Organizations that maintain verification capacity incur visible costs: slower throughput, larger review teams, longer cycle times. They are punished in every quarter where no crisis occurs. Organizations that strip verification capacity show better numbers, attract more investment, win more contracts, hire away the talent from their slower competitors.

> **Conjecture (Selection Against Verification).** The organizations best positioned to weather a forcing event do not survive to the forcing event. High-verification strategies are systematically selected out during the accumulation phase.

*Supporting argument.* This conjecture requires a selection model we do not fully specify here. The intuition draws on Minsky's Financial Instability Hypothesis: strategies that appear conservative during stable periods are punished by competitive dynamics until they become rare. When the crisis arrives, the survivors are precisely those who were least prepared. Formalizing this requires modeling firm entry/exit, capital allocation, and the relationship between observable metrics and latent verification capacity. We leave this for future work but note that the pattern is empirically documented in financial regulation, where capital requirements exist precisely because market selection alone does not preserve adequate reserves.

### 8.4 Structural Lock-In

Both self-correction channels fail for the same structural reason: the cascade equilibrium is self-reinforcing on the very signals that would guide correction.

Recursive verification operates on outputs optimized for coherence within the training manifold. It cannot escape the manifold because escape would require independent grounding, and independent grounding is precisely what the cost structure has made expensive.

Market selection operates on throughput metrics that reward low-θ strategies. It cannot correct toward high-θ strategies because the benefits of verification remain latent until crisis, and pre-crisis performance is what determines survival.

Neither channel has access to an independent rejection signal. Neither channel can price epistemic debt before forcing events demand payment. By the time the debt is called, the capacity to pay has already been competed away.

---

## 9. Empirical Hypotheses and Instrumentation

Theory without measurement is philosophy. This section operationalizes the framework into testable hypotheses and instrumentation baselines. The goal is not to prove the theory but to create conditions under which it could be falsified, and to measure what current frameworks ignore.

### Testable Predictions (Summary)

1. The wedge between measured and verification-adjusted productivity grows over time (H1)
2. Cascade fragility increases with network density and chain length (H2)
3. Endogeneity share in measurement substrates rises over time (H3)
4. Feedback loops exhibit learning collapse as incidents stop changing processes (H4)
5. Verification capacity and capability erode under sustained underuse (H5)
6. Internal organizational language converges toward model-preferred distributions (H6)
7. Irreversible lock-in accumulates through tool deprecation and skill-pipeline changes (H7)

### 9.1 H1: Divergence Between Measured and Verification-Adjusted Productivity

**Hypothesis:**

d/dt(TFP_t^measured - TFP_t^actual) > 0

The wedge grows over time as verification capacity erodes while artifact volume scales.

**Falsification condition:** If correction burden (rework hours, incident remediation) grows slower than or equal to throughput gains, the hypothesis fails.

**Key proxies:**

- **Artifact throughput**: Reports produced, code committed, tickets closed, forecasts generated.
- **Validation lag**: Time from artifact creation to substantive review, audit completion rates, review queue depth.
- **Correction burden**: Rework hours per artifact hour, incident remediation costs, rollback frequency, post-deployment defect density.

**Critical decomposition:** Time spent reading code vs. writing it typically follows a 10:1 ratio (Martin, 2008). AI assistants optimize the writing phase (10% of effort) while potentially increasing cognitive load in the reading and verification phases (90% of effort) by generating unfamiliar patterns. Instrumentation should separately track: time-to-write (AI-accelerated), time-to-understand (potentially AI-degraded), and time-to-debug (lagging indicator of verification gaps).

### 9.2 H2: Cascade Fragility Increases with Coupling and Length

**Hypothesis:**

∂²Fragility / (∂NetworkDensity · ∂CascadeLength) > 0

Longer chains with more interconnection are more fragile to forcing events.

**Instrumentation baseline:**

- **Handoff graph reconstruction**: Map artifact flow through organizations. Who creates, who reviews, who approves, who deploys.
- **Error propagation distance**: When errors are detected, how many hops did they survive before detection?
- **Correlated failure rates**: Do errors cluster by position in the chain? By team? By artifact type?

### 9.3 H3: Rising Endogeneity Share in Measurement Substrates

**Hypothesis:**

dα_t/dt > 0

Model-generated content is an increasing fraction of measurement inputs over time.

**Concrete operationalization for α_t:** For a given data pipeline, implement provenance tagging at ingestion. Each data point receives a flag: `human`, `model`, or `sensor`. Then compute:

α_t = Σ_{i: tag_i = model} w_i · Var(X_i) / Σ_i w_i · Var(X_i)

where w_i is the importance weight of regressor X_i (e.g., standardized coefficient magnitude in a regression or feature importance in a model). This can be instrumented via: (a) watermarking model outputs at generation time, (b) post-hoc classifier-based detection of model-generated text, or (c) audit-based sampling of input provenance.

**Instrumentation baseline:**

- **Provenance flags**: Tag data inputs by origin: human-generated, model-generated, sensor/ground-truth.
- **Substrate share**: What fraction of key econometric series have model-generated ancestry?
- **Benchmark contamination checks**: Test whether evaluation datasets contain model-generated content.

**Data feasibility:** GitHub PR descriptions and commit messages (classifier-detectable), financial research reports with AI-disclosure metadata, corporate forecast databases with generation method flags, news aggregators with source provenance.

### 9.4 H4: Learning Collapse in Feedback Loops

When incidents do not change processes, the organization has stopped learning.

**Instrumentation baseline:**

- **Postmortem-to-process link rate**: How often do incidents result in policy or tooling changes?
- **Recurrence rate**: How often do similar errors recur after ostensible fixes?
- **Gate coverage**: What fraction of artifacts pass through validation checkpoints? Is coverage stable or declining?

### 9.5 H5: Erosion of Verification Capacity and Capability

**Hypothesis:**

dθ_t/dt ≤ 0,  dκ_t/dt < 0

Verification capacity (headcount, time, tools) stagnates or declines. Verification capability (skill, accuracy) actively decays.

**Concrete operationalization for θ_t:** In a software development context, define:

θ_t = Review hours with substantive comments / Total production hours

where "substantive comment" requires code modification or design discussion (excluding approvals, typo fixes, and rubber-stamp LGTMs). This can be instrumented directly from GitHub/GitLab PR metadata: review duration, comment count and type, revision cycles before merge.

**Concrete operationalization for κ_t:** Seeded defect detection rate. Periodically inject known bugs (SQL injection vulnerabilities, off-by-one errors, race conditions) into the review pipeline at random intervals. Measure detection rate over time. If κ_t declines while θ_t is stable, capability is eroding faster than capacity.

**Instrumentation baseline:**

- **Verification labor share**: Review hours as fraction of production hours.
- **Role persistence**: Tenure and seniority in verification functions. Are reviewers promoted out? Laid off? Never hired?
- **Seeded defect detection**: Inject known errors; measure detection rate over time.

### 9.6 H6: Language and Abstraction Convergence

**Hypothesis:**

dγ_t/dt > 0  ⟹  ∂Fragility/∂γ > 0

where γ_t measures coupling between internal language and model-preferred distributions.

As organizations adopt model-generated content, internal language converges toward model-preferred distributions.

**Instrumentation baseline:**

- **Jargon overlap**: Phrase frequency drift between internal documents and model training proxies.
- **Template convergence**: Similarity between internal report structures and model-generated templates.
- **Acceptance friction**: Do model-generated artifacts receive lighter review than human-generated artifacts of similar complexity?

### 9.7 H7: Irreversibility and Lock-In

Some organizational changes are difficult to reverse. Deprecating tools, eliminating roles, removing gates: these create path dependencies.

**Instrumentation baseline:**

- **Tool deprecation**: Track removal of manual verification tools and alternative pathways.
- **Skill pipeline**: Monitor hiring criteria, training investment, promotion patterns in verification functions.
- **Architectural commitments**: Count removal of validation gates, adoption of auto-approve workflows, integration depth of model-generated inputs.

---

## 10. Discussion and Implications

Once the marginal cost of verification exceeds that of generation, the equilibrium shifts. Rational agents converge on forwarding strategies that create cascades. Measured productivity diverges from actual productivity. Measurement systems consume their own outputs. And the mechanisms that might self-correct (recursive verification, market selection) are compromised by the same dynamics they would need to correct.

### 10.1 Implications for Measurement

Productivity statistics that ignore verification costs and epistemic debt do not measure what they claim to measure. When artifact volume can grow independently of verified value creation, TFP becomes a misleading indicator. National statistical agencies, corporate reporting standards, and performance management systems all embed the assumption that output proxies value. Under verification reversal, the assumption fails.

A verification-adjusted measurement framework would track verification capacity as an asset, epistemic debt as a liability, and correction burden as a cost.

### 10.2 Implications for Institutional Design

Verification capacity should be treated as critical infrastructure: maintained, invested in, protected from quarterly optimization pressures. This is difficult when competitive dynamics reward stripping that capacity. It may require coordination mechanisms, regulatory floors, or institutional commitments that survive individual incentive pressures.

The analogy to financial regulation is precise. We do not allow banks to optimize away capital reserves simply because the reserves are costly and crises are rare.

### 10.3 Implications for AI Development

Heterogeneity in models, training distributions, and verification methods reduces correlated failure risk. A monoculture of frontier models trained on similar data with similar objectives and similar evaluation criteria is a fragility multiplier. The errors correlate. The cascade deepens.

This suggests value in maintaining diverse verification channels: human review with different expertise, models with different architectures and training data, and formal methods where applicable. The goal is not to verify that models agree with each other (that is easy and uninformative). The goal is to create conditions where disagreement is possible and informative.

### 10.4 Implications for Incentive Design

The core problem is that verification-heavy strategies are penalized pre-crisis and validated only post-crisis. The feedback loop is too slow and too noisy to guide individual or organizational behavior.

Correcting this requires either shortening the feedback loop (making verification value observable pre-crisis through audits, stress tests, and synthetic error injection) or changing the incentive structure so that verification capacity is rewarded directly rather than only through crisis avoidance.

### 10.5 Limitations and Scope Conditions

This framework applies when verification costs exceed production costs for a substantial class of artifacts. Several boundary conditions limit its scope:

**Domains with cheap automated verification.** In software with robust test suites, continuous integration pipelines, and type systems, verification can remain cheaper than production. Compilation failures, unit test failures, and integration test failures provide near-instantaneous feedback at marginal cost approaching zero. The model predicts cascades are less likely in such environments unless verification infrastructure erodes.

**High-stakes, low-volume decisions.** Domains where errors carry catastrophic consequences and artifact volume is low (e.g., aircraft certification, pharmaceutical approvals, nuclear safety protocols) maintain verification-heavy regimes. Institutional and regulatory structures enforce verification regardless of cost.

**Artifacts with immediate, unambiguous feedback.** When ground truth is revealed quickly and costlessly (such as short-term weather forecasts or real-time system monitoring), verification occurs naturally through outcome observation. Information cascades are fragile when feedback loops are tight and unambiguous.

**Heterogeneous verification capacity.** Organizations with institutional commitment to verification, such as adversarial review processes, red teams, or independent audit functions, can resist cascade dynamics even under high verification costs.

**Model limitations.** The forwarding game assumes agents optimize individually under cost constraints. It abstracts from reputational capital accumulation, career concerns, and institutional path dependence. The endogeneity formalization treats model outputs as optimized for plausibility but does not model adversarial dynamics or deliberate manipulation. The verification-adjusted productivity function is a reduced form; microfoundations linking verification to long-run welfare remain underspecified.

**Measurement challenges.** Distinguishing verification-adjusted from measured productivity requires observing verification effort, error remediation costs, and downstream failure rates, data that are often proprietary or untracked.

**What would falsify this framework:** Evidence that verification costs scale sublinearly with artifact volume under AI assistance; demonstration that recursive AI verification achieves independent rejection signals (ρ → 0); or market evidence that high-verification strategies outcompete low-verification strategies pre-crisis.

### 10.6 Physical Constraints on Synthetic Productivity

The computational substrate for AI-mediated production imposes hard physical limits. Global data center electricity consumption is projected to double between 2022 and 2026, with AI workloads driving a substantial share of this growth (International Energy Agency, 2024). This creates a binding constraint: measured productivity gains from artifact generation are partially offset by rising energy costs and infrastructure requirements. The wedge between digital throughput and physical resource consumption suggests that synthetic productivity, even when measured correctly, may face diminishing returns as energy efficiency gains decelerate and computational demands scale super-linearly with model capabilities.

---

## 11. Conclusion

Verification reversal changes equilibrium behavior and the meaning of measured output. When generation becomes cheaper than verification, the link between artifact volume and underlying cognitive work breaks. Organizations rationally cascade. Productivity metrics overstate welfare. Measurement systems consume contaminated inputs. Self-correction mechanisms fail.

This paper has provided:

1. A sequential forwarding model (Proposition 1) for cascade formation under high verification costs, showing how rational individual behavior aggregates to collective informational blockage.

2. A formal separation of measured from verification-adjusted productivity (Claim 1), with conditions under which the wedge grows over time.

3. An endogeneity share parameter (Claim 2) capturing measurement contamination from model-generated content.

4. Structural analysis of why "AI verifies AI" lacks independent rejection signals and why market selection may operate on lagging indicators that reward low-verification strategies (Conjecture).

5. A falsifiable empirical agenda with instrumentation baselines for measuring verification capacity, epistemic debt, cascade fragility, and endogeneity share.

The framework predicts that conventional productivity statistics will overstate welfare gains from generative AI by ignoring verification costs and epistemic debt accumulation. The measured miracle may be borrowed time.

The dashboard will be green. The epistemic debt will compound in the dark. And when the forcing event arrives, when reality demands validation that cannot be forwarded, the bill will come due.

Whether we have maintained the capacity to pay is a choice we are making now, in every organization, in every quarter, in every decision to ship faster rather than check harder. The choice is being made. The consequences will follow.

Reality is not free. Neither is your lunch.

---

## Acknowledgments

The "Double Minsky" framework in this paper owes an obvious debt to both Marvin Minsky and Hyman Minsky, whose work on distributed intelligence and financial instability respectively illuminates the dynamics of epistemic leverage. The parallel was first noticed (as many things are) in conversation with a cat named Marvin, who has demonstrated throughout his life that verification capacity, once lost, can sometimes be rebuilt, but only with patience, resources, and a willingness to invest when the returns are uncertain.

---

## References

Banerjee, A. V. (1992). A simple model of herd behavior. *The Quarterly Journal of Economics*, 107(3), 797-817.

Bikhchandani, S., Hirshleifer, D., & Welch, I. (1992). A theory of fads, fashion, custom, and cultural change as informational cascades. *Journal of Political Economy*, 100(5), 992-1026.

Brynjolfsson, E., Li, D., & Raymond, L. R. (2023). Generative AI at work. *NBER Working Paper No. 31161*.

GitClear (2024). *Coding on Copilot: 2023 Data Suggests Downward Pressure on Code Quality*. Technical Report. https://www.gitclear.com/coding_on_copilot_data_shows_ais_downward_pressure_on_code_quality

International Energy Agency (2024). *Electricity 2024: Analysis and Forecast to 2026*. IEA, Paris. https://www.iea.org/reports/electricity-2024

Martin, R. C. (2008). *Clean Code: A Handbook of Agile Software Craftsmanship*. Prentice Hall.

Minsky, H. P. (1986). *Stabilizing an Unstable Economy*. Yale University Press.

Minsky, M. (1986). *The Society of Mind*. Simon & Schuster.

Noy, S., & Zhang, W. (2023). Experimental evidence on the productivity effects of generative artificial intelligence. *Science*, 381(6654), 187-192.

Pearce, H., Ahmad, B., Tan, B., Dolan-Gavitt, B., & Karri, R. (2022). Asleep at the keyboard? Assessing the security of GitHub Copilot's code contributions. *2022 IEEE Symposium on Security and Privacy (SP)*, 754-768.

Peng, S., Kalliamvakou, E., Cihon, P., & Demirer, M. (2023). The impact of AI on developer productivity: Evidence from GitHub Copilot. *arXiv preprint arXiv:2302.06590*.

Wooldridge, J. M. (2010). *Econometric Analysis of Cross Section and Panel Data* (2nd ed.). MIT Press.

---

## Appendix A: Instrumentation Details

### A.1 H1: TFP Divergence - Detailed Measurement

**Artifact throughput measures:**
- Reports produced per analyst per week
- Code commits and lines changed per developer
- Ticket closure rate and time-to-close
- Forecast volume and update frequency
- Dashboard creation and modification rates

**Validation lag measures:**
- Time from artifact creation to first substantive review
- Time from artifact creation to validation sign-off
- Fraction of artifacts receiving deep review vs. light edit
- Review queue depth and wait times
- Audit completion rates and coverage

**Correction burden measures:**
- Rework hours per initial artifact hour
- Incident remediation costs (labor + system downtime)
- Rollback frequency and scope
- Post-deployment bug density
- Customer-reported error rates and severity distribution

**Implementation:** Pair production logs with review/correction logs. Track (Y_t, V_t, C_t) where Y_t is artifact volume, V_t is verification effort, and C_t is correction burden. Compute:

Gap_t = Y_t/F(K_t, L_t) - (Y_t - C_t)/F(K_t, L_t + V_t)

Test whether dGap_t/dt > 0.

### A.2 H2: Cascade Fragility - Network Analysis

**Handoff network construction:**
- Map workflow: who creates → who reviews → who approves → who deploys
- Edge weight: frequency and volume of artifact transfers
- Node properties: verification capacity, throughput, position in chain

**Error propagation distance:**
- Inject synthetic errors at known positions
- Track how many hops before detection
- Measure variation by error type and artifact class

**Correlated failure analysis:**
- When errors occur, trace provenance backward
- Compute error similarity between adjacent nodes
- Test whether Cor(ε_i, ε_{i+1}) > 0 and increases with cascade length

**Implementation:** Use version control, review systems, and incident logs to reconstruct dependency graphs. Measure:

Fragility = E[Propagation_Distance] / (Network_Density · Cascade_Length)

### A.3 H3: Endogeneity Share - Data Provenance Tracking

**Lineage flags:**
- Tag all data inputs as: human-generated, model-generated, sensor/ground-truth
- Track provenance through transformation pipelines
- Measure fraction of key regressors with model-generated ancestry

**Substrate share calculation:** For each measured series X_t, decompose:

X_t = X_human,t + X_model,t + X_sensor,t

Compute:

α_t = Var(X_model,t) / Var(X_t)

**Benchmark contamination:**
- Check whether evaluation datasets include model-generated content
- Test whether test sets leak training distribution artifacts
- Measure overlap between model outputs and measurement inputs

**Implementation:** Instrument data pipelines with provenance metadata. Test whether dα_t/dt > 0 and whether Cor(α_t, Bias_t) > 0.

### A.4 H4: Learning Collapse - Feedback Loop Closure

**Postmortem linkage:**
- Count incidents → track postmortems → measure policy/process changes
- Compute: Process changes / Incidents over time
- Test whether this ratio declines

**Recurrence rate:**
- Classify incidents by root cause
- Measure: Repeat incidents / Total incidents
- Test whether this rate increases

**Gate coverage:**
- Enumerate validation checkpoints in workflows
- Measure: Artifacts passing through gates / Total artifacts
- Test whether coverage declines

**Implementation:** Use incident management systems, change logs, and workflow analytics. Track learning efficiency:

L_t = Process improvements_t / Errors detected_t

Test whether dL_t/dt → 0.

### A.5 H5: Verification Capacity and Capability - Stock Measurement

**Capacity metrics:**
- Verification labor hours as share of total production hours
- Headcount in review, audit, QA, and validation roles
- Budget allocated to verification infrastructure
- Tool coverage: fraction of artifacts passing through automated checks

**Capability metrics:**
- Time-to-competent-review for novel artifact types
- Seeded defect detection rates (inject known errors, measure catch rate)
- Review accuracy under controlled conditions
- Skill retention: performance after periods of low verification activity

**Implementation:**
- Track θ_t = Verification hours_t / Production hours_t
- Measure κ_t via standardized error-detection tests
- Test whether dθ_t/dt ≤ 0 and dκ_t/dt < 0

### A.6 H6: Language Convergence - Semantic Drift Analysis

**Jargon overlap:**
- Compare internal documents to reference corpus (proxy for model training distribution)
- Measure phrase frequency drift
- Track adoption of model-preferred terminology

**Template convergence:**
- Measure similarity between internal report structures and model-generated templates
- Track boilerplate growth and standardization
- Compute entropy reduction in document structure

**Acceptance friction:**
- Measure review time for model-generated vs. human-generated artifacts
- Test whether model-generated content receives lighter scrutiny
- Track rejection rates by artifact source

**Implementation:** Use text analysis tools to compute:

γ_t = Model-aligned phrases_t / Total phrases_t

Test whether dγ_t/dt > 0 and whether higher γ_t correlates with lower verification intensity.

### A.7 H7: Irreversibility and Lock-In - Institutional Commitment Tracking

**Tool deprecation:**
- Track removal of manual verification tools
- Measure availability of non-AI validation pathways
- Count workflow steps that assume AI availability

**Skill pipeline changes:**
- Track hiring criteria: verification skills vs. throughput skills
- Measure training investment: generation tools vs. validation tools
- Monitor promotion criteria and performance incentives

**Architectural commitments:**
- Count removal of validation gates and approval steps
- Measure adoption of auto-merge, auto-deploy workflows
- Track integration depth (how many systems depend on AI-generated inputs)

**Implementation:** Define lock-in stock:

L_t = Σ_commitments Irreversibility_Weight · Adoption_Depth

Test whether dL_t/dt > 0 and whether higher L_t correlates with higher minimum forcing-event magnitude required for cascade reversal.

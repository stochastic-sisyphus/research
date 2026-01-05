# Verification Reversal: Cascades and Synthetic Productivity in an AI-Mediated Economy

**Vanessa Beck**

Independent Researcher  
vanessa.beckk1@gmail.com  
ORCID: 0009-0008-6611-535X  
GitHub: stochastic-sisyphus

Version 1.0 | January 2025

*Author disclosure: No external funding. No conflicts of interest.*

-----

## Abstract

Generative AI has pushed the marginal cost of producing informational artifacts below the marginal cost of verifying them. This paper studies the resulting *verification reversal* regime and its consequences for information quality, productivity measurement, and institutional stability.

**Mechanism.** A sequential forwarding game shows that when verification costs exceed production costs, rational agents propagate unverified artifacts, forming information cascades even as throughput metrics rise.

**Results.** We derive conditions under which (1) measured total factor productivity diverges from verification-adjusted productivity, a pattern we term *synthetic productivity*; (2) model-generated data contaminate econometric feedback loops, extending recognition lags; and (3) two standard self-correction arguments (recursive AI verification and market selection) fail structurally.

**Measurement.** We propose instrumentation strategies for verification capacity, endogeneity share, cascade fragility, and epistemic debt.

**Implications.** Conventional productivity statistics may systematically overstate welfare gains from generative AI by ignoring verification costs and epistemic debt accumulation.

**Keywords:** Information cascades; Verification costs; Generative AI; Total factor productivity; Endogeneity; Epistemic debt.

**JEL Classification:** D83 (Search; Learning; Information); D85 (Network Formation and Analysis); O33 (Technological Change); E01 (Measurement and Data on National Income).

-----

## Table of Contents

1. Introduction
1. Literature Review
1. Verification Reversal: Definition and Cost Structure
1. The Forwarding Game: Model and Equilibrium
1. Synthetic Productivity and Measurement Divergence
1. Endogenous Measurement Contamination
1. Verification-Adjusted Productivity and Epistemic Debt
1. Why Self-Correction Mechanisms Fail
1. Empirical Hypotheses and Instrumentation
1. Discussion and Implications
1. Conclusion

Appendix A: Notation Summary  
Appendix B: Proofs  
Appendix C: Instrumentation Details

-----

## 1. Introduction

There is a particular kind of confidence that comes from watching a machine produce, in seconds, what once took hours. Code that compiles. Prose that scans as expert. Forecasts dressed in last quarter’s familiar format. Measured through the lenses we inherited, this looks like productivity: pure, unambiguous, a gift from the efficiency gods.

But measurement systems encode assumptions about what they measure. The assumption embedded in most productivity metrics is older than it appears: that producing an artifact requires cognitive work roughly proportional to the artifact’s complexity. More output, more thinking. The link was never perfect, but it was robust enough to anchor decades of economic inference.

Generative AI has severed that link.

The marginal cost of *producing* a plausible artifact (code, analysis, report, forecast) has collapsed. The marginal cost of *verifying* whether that artifact is correct, coherent with reality, safe to act upon? That cost has not collapsed. In many domains it has risen, because the artifacts now require scrutiny they once did not need, and the humans who might provide that scrutiny are drowning in volume.

This paper studies what happens when generation becomes cheaper than verification. The answer is not merely “more errors.” The answer is a regime shift in equilibrium behavior: rational agents stop verifying, information cascades form, measured productivity diverges from actual productivity, and the mechanisms that might self-correct (recursive AI verification, market selection) turn out to be structurally compromised by the very dynamics they would need to correct.

### 1.1 Paper Structure and Claims

**Model (Sections 3-4).** We formalize verification reversal as a cost inequality and derive a sequential forwarding game. *Proposition 1*: When verification costs exceed production costs for a substantial artifact class, cascade equilibria emerge in which rational agents propagate unverified artifacts regardless of private beliefs.

**Productivity Measurement (Sections 5-7).** We distinguish measured from verification-adjusted productivity and formalize epistemic debt as a stock variable. *Proposition 2*: Under verification reversal, measured TFP can rise while utility-relevant productivity stagnates (synthetic productivity). *Proposition 3*: Model-generated content induces endogeneity bias. *Proposition 4*: Recognition lags extend as endogeneity share rises.

**Self-Correction Failure (Section 8).** We analyze recursive verification and market selection. *Proposition 5*: Recursive verification fails under correlated error. *Conjecture 1*: Market selection systematically penalizes high-verification strategies during the accumulation phase.

**Empirical Agenda (Section 9).** We propose seven testable hypotheses with instrumentation baselines.

### 1.2 Key Definitions

> **Definition 1 (Verification Reversal).** The regime in which the marginal cost of producing an artifact is lower than the marginal cost of verifying it:
> 
> ∂C_prod/∂Y < ∂C_ver/∂Y

> **Definition 2 (Synthetic Productivity).** The appearance of output growth (rising measured TFP) when verification-adjusted, utility-relevant productivity stagnates or declines.

> **Definition 3 (Verification-Adjusted Productivity).** TFP computed using only verified artifacts, discounting unverified volume.

> **Definition 4 (Epistemic Debt).** The accumulated gap between system complexity and cognitive grasp: the stock of artifacts an organization relies upon but does not fully understand.

> **Definition 5 (Endogeneity Share).** The fraction of variance in key regressors attributable to model-generated content:
> 
> α_t = Var(X_model,t) / Var(X_total,t)

### 1.3 Contributions

This paper offers five contributions:

1. **A forwarding game under verification reversal** with explicit model primitives and a formally derived cascade equilibrium (Proposition 1).
1. **A formal distinction between measured and verification-adjusted productivity** with conditions under which the wedge grows over time (Proposition 2).
1. **An endogeneity share parameter** measuring how model-generated content contaminates econometric substrates (Proposition 3).
1. **Structural conditions under which self-correction fails**: recursive AI verification lacks independent rejection signals when models share training distributions (Proposition 5), and market selection operates on lagging indicators (Conjecture 1).
1. **A concrete empirical agenda** with testable hypotheses and instrumentation baselines.

### 1.4 Relation to Existing Literatures

The analysis braids together several intellectual threads: foundational work on informational cascades and social learning (Bikhchandani et al., 1992; Banerjee, 1992), costly verification theory (Townsend, 1979; Gale & Hellwig, 1985), information acquisition (Verrecchia, 1982), productivity measurement (Syverson, 2011), the emerging literature on AI productivity effects (Brynjolfsson et al., 2023; Peng et al., 2023; Noy & Zhang, 2023), econometric treatments of endogeneity (Wooldridge, 2010), and social learning in networks (Acemoglu et al., 2011).

**What distinguishes this framework.** This is not merely “cascades with AI.” The novelty lies in three structural claims:

(i) *Verification capacity is endogenous and erodes under sustained underuse*, so organizations lose not just the time but the *ability* to verify;

(ii) *Measurement substrates become endogenously contaminated* as model-generated content enters the data used to detect problems, extending recognition lags through a feedback loop that standard econometric diagnostics may not detect;

(iii) *Market selection operates on lagging proxies* (throughput, velocity) rather than latent verification stocks, systematically selecting out high-verification strategies during the accumulation phase when they would matter most.

These three mechanisms interact: erosion accelerates contamination, contamination extends the lag before selection can correct, and selection pressure accelerates erosion.

### 1.5 How to Read This Paper

This paper occupies a middle ground between formal theory and empirical measurement. Sections 3-4 develop a stylized model with explicit assumptions and formally derived propositions. Sections 5-8 present additional propositions as derived implications under stated assumptions. Section 9 translates theoretical predictions into testable hypotheses with concrete operationalizations. Readers seeking formal proofs should consult Appendix B. Readers seeking empirical guidance should focus on Section 9’s instrumentation baselines.

### 1.6 Empirical Motivation

Three domains exhibit verification reversal dynamics with measurable consequences:

**Software development under AI assistance.** GitClear’s analysis of 153 million changed lines of code across 2020-2024 documents systematic quality shifts as AI code-generation tools scaled. Their 2024 report finds that “code churn” (lines reverted within two weeks of being written) increased substantially as AI-assisted commits grew, while “moved” code (the primary indicator of thoughtful refactoring) declined relative to “copy/paste” code (GitClear, 2024).

**Security vulnerability proliferation.** Multiple studies document elevated vulnerability rates in AI-generated code, with common weakness enumerations (CWEs) including SQL injection, cross-site scripting, and hardcoded credentials appearing at higher frequencies than in human-written baselines (Pearce et al., 2022).

**Knowledge work and analysis.** Qualitative reports from consulting, financial research, and legal services describe a modal shift toward “light edit and forward” behavior, with deep verification increasingly reserved for high-stakes sections while routine artifacts pass through review with minimal scrutiny.

These cases share a structure: artifact production accelerated while verification capacity remained constant or declined, forwarding behavior increased, and error detection shifted downstream or post-deployment.

### 1.7 Definitions and Notation Preview

> **Definition (Artifact).** An *artifact* is a discrete unit of informational output: a code commit, a report section, an analysis, a forecast, a recommendation. Artifacts are the objects that flow through organizational workflows and are either verified or forwarded.

**Core notation.** The following symbols appear throughout; formal definitions are in Appendix A.

|Symbol    |Meaning                                                |
|----------|-------------------------------------------------------|
|ω ∈ {H, L}|Artifact quality state (High/Low)                      |
|Y_t       |Artifact volume at time t                              |
|θ_t       |Verification capacity (organizational resource)        |
|κ_t       |Verification skill (ability to detect errors)          |
|α_t       |Endogeneity share (fraction of model-generated content)|
|τ         |Recognition lag (time to detect problems)              |
|π^cut     |Indifference cutoff for verify/forward decision        |
|π^F, π^V  |Forward and verify cascade thresholds                  |

*Working paper note:* This paper develops a theoretical framework with measurement implications. Formal microfoundations for the selection dynamics (Conjecture 1) are planned for a follow-up paper. Empirical implementation of the proposed instrumentation is ongoing.

-----

## 2. Literature Review

### 2.1 Informational Cascades and Social Learning

The mathematics of herding was formalized before anyone imagined machines that could produce plausible text at scale. Bikhchandani, Hirshleifer, and Welch (1992) and Banerjee (1992) showed that rational agents observing predecessors’ actions can enter cascades where private signals are discounted and learning stops, even when private information remains informative. The mechanism is elegant: once the inferred weight of upstream behavior exceeds the informational value of one’s own signal, the rational move is to follow the crowd. Truth becomes irrelevant to the equilibrium.

This paper adapts the framework to a setting where generative AI has altered the cost structure in a specific way: verification has become expensive relative to production. The cascade dynamics remain, but the entry conditions have changed.

### 2.2 Costly Verification

Townsend (1979) introduced costly state verification in financial contracting: lenders cannot freely observe borrower outcomes and must pay to verify. Gale and Hellwig (1985) developed optimal debt contracts under these conditions. This literature treats verification costs as exogenous parameters shaping contract design.

The present work endogenizes verification capacity: organizations that underuse verification experience skill decay, so the cost of verification rises endogenously. The insight from financial contracting—that verification costs shape equilibrium behavior—extends to information economies where artifact generation has become cheap.

### 2.3 AI Productivity Measurement

Empirical studies document productivity gains from generative AI across knowledge-work tasks. Brynjolfsson et al. (2023) find that customer service agents using AI assistants resolve 14% more issues per hour. Peng et al. (2023) report that GitHub Copilot users completed coding tasks 55% faster. Noy and Zhang (2023) find that ChatGPT assistance reduced writing time for professional tasks by 40%.

The gains are real within the measurement frame employed. But most studies emphasize output volume and short-horizon quality metrics without separately tracking verification bandwidth, downstream error remediation, or long-run maintenance costs. A key gap in the literature is the absence of verification-adjusted productivity measures.

### 2.4 Endogeneity in Econometrics

Econometric theory has long grappled with endogeneity arising from omitted variables, measurement error, simultaneity, and selection. Wooldridge (2010) provides the technical machinery for detection and correction when the problem is recognized.

In AI-mediated economies, a distinct channel emerges: regressors themselves can be model-generated and optimized for plausibility, breaking orthogonality between regressors and errors in ways that standard diagnostics may not detect.

-----

## 3. Verification Reversal: Definition and Cost Structure

### 3.1 The Verification Reversal Condition

Let Y denote artifact volume per period. Let C_prod(Y) and C_ver(Y) be the costs of producing and verifying that volume.

> **Definition 1 (Verification Reversal, restated).** The verification reversal regime holds when:
> 
> ∂C_prod/∂Y < ∂C_ver/∂Y
> 
> That is, the marginal cost of producing an additional artifact is lower than the marginal cost of verifying it.

The inequality need not hold universally. It suffices that for a substantial class of “good enough” artifacts—the kind that clear immediate review, satisfy surface criteria, and raise no obvious flags—incremental production is easier than incremental verification.

### 3.2 Verification Cost Non-Linearity

The verification cost function exhibits critical non-linearities. As artifact volume Y scales, verification cost per artifact rises due to cognitive fatigue and needle-in-a-haystack dynamics.

> **Assumption 1 (Verification Cost Structure).** The verification cost function takes the form:
> 
> C_ver(Y) = c₀Y + c₁Y^α + c₂f(Y/H)
> 
> where:
> 
> - c₀Y is the baseline linear cost
> - c₁Y^α with α > 1 captures fatigue effects (verification becomes harder as reviewers process more artifacts)
> - c₂f(Y/H) represents the increasing difficulty of finding errors as signal-to-noise ratio declines (H is human verification bandwidth)

*Interpretation*: This non-linearity implies that even if C_prod remains constant, verification costs can explode as volume scales, accelerating the transition to cascade equilibria.

### 3.3 Verification as Overhead

Once verification reversal binds broadly, verification undergoes a reclassification. In the old regime, verification capacity read as *capability*: the mark of a rigorous organization, a feature to advertise, a competitive advantage. In the new regime, verification reads as *overhead*: a cost center, a drag on velocity, a bottleneck to be optimized away.

This reclassification follows from the incentive structure. When performance metrics reward throughput and the cost of verification is visible while the cost of *not* verifying remains latent, the rational actor prunes verification capacity.

-----

## 4. The Forwarding Game: Model and Equilibrium

Consider a workflow as a sequence of agents: i = 1, 2, …, N. An artifact enters at one end and passes through hands until it exits as a decision, a deployment, a publication, a commitment. At each position, the agent holding the artifact faces a choice:

- **Verify (V)**: Incur cost c_V to check the artifact against independent criteria.
- **Forward (F)**: Pass it on with minimal scrutiny at cost c_F, where c_F << c_V.

### 4.1 Model Primitives

**State space.** Each artifact has a true quality state ω ∈ {H, L} (High or Low quality), drawn with prior P(ω = H) = π₀.

> **Assumption 2 (Information Structure).** Agent i receives a conditionally independent private signal s_i ∈ {h, ℓ} with precision q ∈ (0.5, 1):
> 
> P(s_i = h | ω = H) = P(s_i = ℓ | ω = L) = q

Agent i also observes the sequence of actions a₁, …, a_{i-1} taken by predecessors.

**Actions.** Agent i chooses action a_i ∈ {V, F}.

> **Assumption 3 (Verification as Ground-Truth Revelation).** If agent i chooses to verify (a_i = V), the true state ω is revealed perfectly to agent i. Verification is a costly but definitive check against external reality. This is the key asymmetry: production is cheap but uninformative; verification is expensive but resolves uncertainty completely.
> 
> *Policy after revelation:* If verification reveals ω = L (low quality), the agent blocks the artifact and receives benefit B net of reputational cost R. If verification reveals ω = H (high quality), the agent forwards the artifact. The expected payoff from verification thus depends on the probability of catching a low-quality artifact.

> **Assumption 4 (Payoff Structure).** Payoffs depend on action, true state, and downstream outcomes:
> 
> |           |ω = H (High quality)|ω = L (Low quality)|
> |-----------|--------------------|-------------------|
> |Verify (V) |-c_V                |-c_V + B - R       |
> |Forward (F)|-c_F                |-c_F - D_i         |
> 
> where:
> 
> - c_V: verification cost
> - c_F: forwarding cost (c_F << c_V)
> - B: benefit of catching a low-quality artifact (enabled by Assumption 3: verification reveals ω = L)
> - R: reputational cost of blocking (stopping the line)
> - D_i: agent i’s exposure to deployment failure costs

We assume D is spread across agents or absorbed by the organization, so individual exposure to D may be small.

> **Remark (Action Cascade vs. Adoption Cascade).** The cascade object in this paper is an *action cascade*: agents converge on forwarding (or verifying) regardless of private signals. This differs from standard herding models where agents adopt beliefs about a state. Here, information blockage occurs in the *decision to check*, not in beliefs about quality. Agents in a forward cascade may privately doubt artifact quality but rationally choose not to verify.

**Belief updating.** Let π_i = P(ω = H | s_i, a₁, …, a_{i-1}) denote agent i’s posterior belief.

> **Lemma 1 (Bayesian Updating with Private Signal).** Given prior π_{i-1} = P(ω = H | a₁, …, a_{i-1}) and private signal s_i, agent i’s posterior is:
> 
> π_i(h) = q·π_{i-1} / [q·π_{i-1} + (1-q)(1-π_{i-1})]  if s_i = h
> 
> π_i(ℓ) = (1-q)·π_{i-1} / [(1-q)·π_{i-1} + q(1-π_{i-1})]  if s_i = ℓ

*Proof.* Direct application of Bayes’ rule using the signal structure in Assumption 2. ∎

**Equilibrium concept.** We solve for Perfect Bayesian Equilibrium (PBE).

> **Definition 6 (Perfect Bayesian Equilibrium).** A Perfect Bayesian Equilibrium consists of:
> 
> (i) A strategy profile σ = (σ₁, …, σ_N) where σ_i: {h, ℓ} × {V, F}^{i-1} → Δ({V, F}) maps agent i’s private signal and observed history to a probability distribution over actions.
> 
> (ii) A belief system μ = (μ₁, …, μ_N) where μ_i gives agent i’s posterior probability that ω = H.
> 
> Such that:
> 
> - (Sequential Rationality) Each agent’s strategy maximizes expected payoff given beliefs and successors’ strategies.
> - (Belief Consistency) Beliefs are derived from Bayes’ rule wherever possible given the strategy profile.

### 4.2 Optimal Verification Decision

Agent i compares expected payoffs from verification versus forwarding.

> **Lemma 2 (Verification Threshold).** Agent i strictly prefers to verify if and only if:
> 
> (1 - π_i(s_i)) · (B - R + D_i) > Δc
> 
> where Δc = c_V - c_F is the verification cost gap.

*Proof.* The expected payoff from forwarding is:

U_F = -c_F - (1 - π_i(s_i)) · D_i

The expected payoff from verifying is:

U_V = -c_V + (1 - π_i(s_i)) · (B - R)

Verification is preferred when U_V > U_F:

-c_V + (1 - π_i(s_i))(B - R) > -c_F - (1 - π_i(s_i))D_i

(1 - π_i(s_i))(B - R + D_i) > c_V - c_F = Δc ∎

### 4.3 Cascade Formation

We now state and prove the main result on cascade equilibria.

> **Proposition 1 (Cascade Formation Under Verification Reversal).** Suppose verification reversal holds with cost gap Δc.
> 
> **Action cutoff.** Define the indifference cutoff:
> 
> π^cut = 1 - Δc/(B - R + D_i)
> 
> Agent i verifies if π_i(s_i) < π^cut; forwards if π_i(s_i) > π^cut.
> 
> **Cascade thresholds.** Define the history-dependent cascade thresholds (derived in Appendix B.1):
> 
> - **Forward cascade threshold π^F:** the prior π_{i-1} satisfying π_i(ℓ) = π^cut, i.e., the level above which even a low signal cannot push the posterior below π^cut.
> - **Verify cascade threshold π^V:** the prior π_{i-1} satisfying π_i(h) = π^cut, i.e., the level below which even a high signal cannot push the posterior above π^cut.
> 
> Closed forms (where q is signal precision):
> 
> π^F = q·π^cut / [q·π^cut + (1-q)(1-π^cut)]
> 
> π^V = (1-q)·π^cut / [(1-q)·π^cut + q(1-π^cut)]
> 
> Note: π^V < π^cut < π^F when q > 0.5 (signals are informative).
> 
> **Equilibrium.** If π^cut ∈ (0,1), there exists a Perfect Bayesian Equilibrium with the following properties:
> 
> (Corner cases: If π^cut ≤ 0, forwarding is always optimal regardless of beliefs. If π^cut ≥ 1, verifying is always optimal regardless of beliefs. These occur when Δc ≥ B - R + D_i or Δc ≤ 0, respectively.)
> 
> (i) **Interior Region.** When π_{i-1} ∈ (π^V, π^F), agent i’s action depends on their private signal: verify if s_i = ℓ, forward if s_i = h. Actions are informative; beliefs update.
> 
> (ii) **Forward Cascade Region.** When π_{i-1} ≥ π^F, agent i forwards regardless of signal. The posterior π_i(ℓ) ≥ π^cut even with a bad signal, so verification is never optimal.
> 
> (iii) **Verify Cascade Region.** When π_{i-1} ≤ π^V, agent i verifies regardless of signal. The posterior π_i(h) ≤ π^cut even with a good signal, so forwarding is never optimal.
> 
> (iv) **Information Blockage.** In cascade regions, actions are uninformative about private signals. Observing a forward (or verify) does not update beliefs about ω. Learning stops.

*Proof.* See Appendix B.1. The argument proceeds by:

**Step 1:** Establish that the verification condition in Lemma 2 defines the indifference cutoff π^cut.

**Step 2:** Derive π^F: the prior above which even s_i = ℓ cannot push the posterior below π^cut.

**Step 3:** Derive π^V: the prior below which even s_i = h cannot push the posterior above π^cut.

**Step 4:** Verify the interior region structure.

**Step 5:** Confirm information blockage in cascade regions.

**Step 6:** Verify this constitutes a PBE: strategies are sequentially rational given beliefs, and beliefs are Bayes-consistent on the equilibrium path. ∎

> **Corollary 1 (Cascade Likelihood Increases with Cost Gap).** The width of the interior region shrinks as Δc increases. As Δc increases:
> 
> - π^cut decreases (indifference cutoff falls)
> - π^F decreases (forward cascades become easier to enter)
> - π^V increases (verify cascades become easier to enter)
> 
> The cascade regions [0, π^V] and [π^F, 1] expand, while the interior region (π^V, π^F) contracts. As Δc → B - R + D_i, the interior region collapses and cascades form immediately.

*Proof.* From Proposition 1, π^cut = 1 - Δc/(B - R + D_i). As Δc increases, π^cut decreases. Since π^F is increasing in π^cut (from its explicit formula), π^F decreases. Symmetrically, π^V is decreasing in π^cut, so π^V increases. The interior region (π^V, π^F) shrinks from both ends. ∎

### 4.4 Information Blockage

> **Definition 7 (Information Blockage).** Information blockage is the equilibrium state in which:
> 
> (i) Artifact throughput is high (most artifacts are forwarded).
> 
> (ii) Actions are uninformative about quality (forwarding reveals nothing about private signals).
> 
> (iii) Posterior beliefs are stable (no updating occurs despite information existing in private signals).
> 
> Formally: I(a₁, …, a_n ; ω) → 0 even as Y_t → ∞, where I(·;·) denotes mutual information.

*Interpretation*: This is not collective irrationality. It is individual rationality aggregating to collective blindness. Each agent optimizes correctly given their local information and incentive structure. The system outcome is a cascade that no one chose and no one can unilaterally escape.

-----

## 5. Synthetic Productivity and Measurement Divergence

At the macroeconomic level, total factor productivity (TFP) is typically computed as:

TFP_t^meas = Y_t / F(K_t, L_t)

where Y_t is measured output and F(·) is a production function of capital and labor.

### 5.1 Measured vs. Verification-Adjusted Productivity

> **Definition 8 (Measured TFP).** Measured total factor productivity at time t is:
> 
> TFP_t^meas = Y_t / F(K_t, L_t)
> 
> where Y_t is artifact volume (count of reports, commits, forecasts, etc.) and F(·) is a production function of capital K_t and labor L_t.

> **Definition 9 (Verification-Adjusted TFP).** Let θ_t ∈ [0,1] denote verification capacity (the fraction of artifacts that receive substantive verification). Let v: [0,1] → [0,1] denote the verification rate function, where v(θ_t) gives the probability that a randomly selected artifact has been verified. Verification-adjusted TFP is:
> 
> TFP_t^adj = Y_t · v(θ_t) / F(K_t, L_t)

> **Definition 2 (Synthetic Productivity, restated).** Synthetic productivity is the phenomenon where TFP_t^meas rises while TFP_t^adj stagnates or declines:
> 
> d(TFP_t^meas)/dt > 0  while  d(TFP_t^adj)/dt ≤ 0

### 5.2 Conditions for Wedge Growth

> **Proposition 2 (Synthetic Productivity Under Verification Reversal).** Suppose:
> 
> (i) Artifact volume grows: dY_t/dt > 0
> 
> (ii) Verification capacity is bounded or declining: dθ_t/dt ≤ 0
> 
> (iii) The verification rate function satisfies v’(θ) > 0 and v’’(θ) < 0 (diminishing returns to verification capacity)
> 
> Then the productivity wedge grows over time:
> 
> d/dt(TFP_t^meas - TFP_t^adj) > 0

*Proof.* See Appendix B.2. The measured-to-adjusted productivity gap is:

Gap_t = TFP_t^meas - TFP_t^adj = Y_t(1 - v(θ_t)) / F(K_t, L_t)

Taking the time derivative:

d(Gap_t)/dt = [Ẏ_t(1 - v(θ_t)) - Y_t·v’(θ_t)·θ̇_t] / F(K_t, L_t) + (terms from Ḟ)

Under the assumptions, Ẏ_t > 0, θ̇_t ≤ 0, and v(θ_t) < 1. The first term is positive; the second term is non-negative. Therefore d(Gap_t)/dt > 0. ∎

### 5.3 The Verification Treadmill

> **Definition 10 (Verification Treadmill).** The verification treadmill is the dynamic where artifact volume growth outpaces verification capacity growth, causing the effective verification rate to decline even if absolute verification effort is constant:
> 
> v_t = g(θ_t/Y_t),  g’(·) > 0
> 
> If d(Y_t/θ_t)/dt > 0, then dv_t/dt < 0.

The verification rate per artifact declines as the ratio of artifacts to verification capacity rises. This is not a contingent fact about current organizations; it is a structural property of the production function. Verification does not scale the way generation scales.

-----

## 6. Endogenous Measurement Contamination

The problem deepens when we trace measurement data to their sources.

### 6.1 Model-Generated Content in Regressors

Econometric analysis assumes:

Y_t = βX_t + ε_t  with  E[X_t ε_t] = 0

The orthogonality condition requires that regressors be independent of the error term. In an AI-mediated economy, the data used to construct X_t increasingly include model-generated artifacts:

X_t = X_t^human + X_t^model + X_t^sensor

where X_t^model = h(Model_t(Y_{t-1}, X_{t-1}, θ)).

> **Definition 5 (Endogeneity Share, restated).** The endogeneity share is:
> 
> α_t = Var(X_t^model) / Var(X_t)

### 6.2 Endogeneity Bias

> **Assumption 5 (Model Output Optimization).** Model-generated content is optimized for plausibility within the training distribution:
> 
> X_t^model = argmax_x P_train(x | context_t)
> 
> where P_train is the probability distribution learned from training data.

> **Proposition 3 (Endogeneity Bias).** Suppose the true data-generating process is:
> 
> Y_t = βX_t + ε_t,  E[ε_t | X_t^human, X_t^sensor] = 0
> 
> When X_t^model enters the regressor and is correlated with ε_t (because both are influenced by unobserved factors that models learn to predict), OLS estimates are biased:
> 
> β̂_OLS = β + Cov(X_t^model, ε_t) / Var(X_t) = β + α_t · Cov(X_t^model, ε_t) / Var(X_t^model)

*Proof.* Standard endogeneity result. The bias term scales with α_t, the model-generated share of regressor variance. ∎

### 6.3 Recognition Lag Extension

> **Definition 11 (Recognition Lag).** The recognition lag τ is the expected time between the onset of a genuine problem (e.g., quality degradation, model drift, systematic error) and its detection through standard monitoring.

> **Proposition 4 (Recognition Lag Increases with Endogeneity Share).** Under the following assumptions:
> 
> (i) Problems manifest as deviations from expected relationships: Y_t - E[Y_t | X_t] = ε_t + η_t where η_t is the problem signal
> 
> (ii) Model-generated content smooths anomalies: Cov(X_t^model, η_t) < 0
> 
> (iii) Detection occurs when cumulative evidence exceeds threshold: Σ_{s=0}^τ |η̂_s| > η̄
> 
> Then the recognition lag increases with endogeneity share:
> 
> dτ/dα > 0

*Proof.* See Appendix B.3. The intuition is that model-generated content, optimized for plausibility, tends to smooth anomalous signals rather than amplify them. Higher α means more smoothing, so problems take longer to accumulate detectable evidence. ∎

-----

## 7. Verification-Adjusted Productivity and Epistemic Debt

### 7.1 Verification-Adjusted Utility

Define verification-adjusted utility as:

V: ℝ⁺ × [0,1] → ℝ⁺,  V(Y, θ) = ∫₀^Y v(y, θ) dy

where θ is verification capacity and v(y, θ) ∈ [0,1] is the effective verification rate—the probability that artifact y has been checked against reality.

### 7.2 Epistemic Debt as a Stock

Let C_s(t) denote the complexity (or volume) of epistemically loaded artifacts—the systems, reports, codebases, and models that an organization relies upon but may not fully understand. Let G_c(t) = g(θ_t, κ_t) denote organizational cognitive grasp, where θ_t is verification capacity and κ_t is verification skill.

> **Definition 4 (Epistemic Debt, restated).** Epistemic debt is the accumulated gap:
> 
> D_e(T) = ∫₀^T (C_s(t) - G_c(t)) dt

### 7.3 Verification Skill Decay

> **Assumption 6 (Skill Decay Under Underuse).** Under sustained underuse of verification tasks, verification skill decays:
> 
> dκ_t/dt = -δ(κ_t - κ̲) + λ·(verification activity)_t
> 
> where δ > 0 is the decay rate and κ̲ is a lower bound.
> 
> When verification activity is low, dκ_t/dt < 0.

The organization loses not merely the time to verify but the ability. Epistemic debt accumulates even when surface metrics remain positive—especially when surface metrics remain positive, because positive metrics reduce the perceived urgency of verification.

### 7.4 Synthetic Productivity as Non-Renewable Resource

*Interpretation*: If successive model generations are trained on synthetic data produced by predecessors, the system consumes the epistemic capital accumulated in the historical corpus of human-generated, verified information. Model collapse studies show that training on synthetic data leads to distribution shift where models forget tail events and over-index on probable outputs. This suggests current productivity gains depend on unreplaced stocks of verified human knowledge—a finite resource under active depletion.

-----

## 8. Why Self-Correction Mechanisms Fail

Two self-correction arguments dominate optimistic discourse about AI-mediated information systems. The first: AI will verify AI, driving verification costs back down and restoring the old equilibrium. The second: market selection will weed out low-verification strategies over time, as errors accumulate and the careless fail.

Both arguments are structurally flawed.

### 8.1 Recursive Verification and Correlated Error

Effective verification requires an independent rejection signal: a check that can say “no” for reasons unrelated to why the original system said “yes.”

> **Definition 12 (Cross-Model Error Correlation).** Let M₁ and M₂ be two models. The cross-model error correlation is:
> 
> ρ₁₂ = Cov(ε_{M₁}, ε_{M₂}) / (σ_{M₁}·σ_{M₂})
> 
> where ε_{M_i} is model i’s error (deviation from ground truth).

> **Assumption 7 (Shared Training Distribution).** Models M₁ and M₂ are trained on overlapping data distributions with shared optimization objectives (e.g., cross-entropy minimization over similar text corpora).

> **Proposition 5 (Recursive Verification Fails Under Correlated Error).** Suppose M₂ is used to verify outputs of M₁. Effective verification requires independent rejection signals: ρ₁₂ ≈ 0.
> 
> Under Assumption 7 (shared training distribution), ρ₁₂ > 0. The verifier’s errors correlate with the generator’s errors. Agreement between models increases surface coherence without increasing truth-sensitivity:
> 
> P(M₂ accepts | M₁ correct) ≈ P(M₂ accepts | M₁ incorrect)
> 
> when both models make similar errors on similar inputs.

*Proof.* Models trained on similar distributions learn similar implicit priors about what constitutes “normal” or “expected” output. Errors—deviations from ground truth that nonetheless match training distribution patterns—are systematically shared. A verifier model cannot reject outputs that match its own learned distribution, even when those outputs are factually incorrect.

Formally, let T denote the training distribution and R denote reality. When P_T(x) ≠ P_R(x) for some inputs x, both models assign high probability to T-plausible outputs. Verification would require the verifier to detect P_T(x) ≠ P_R(x), but the verifier only has access to P_T. ∎

> **Remark (Recursive Dilution).** Under high ρ₁₂, stacking verifiers increases confidence without increasing accuracy. Each additional model confirmation reinforces the consensus within the training distribution. This is *recursive dilution*: the appearance of robustness through agreement, when agreement reflects shared bias rather than independent validation.

### 8.2 The Double Minsky Framework

The parallel to two Minskys—Marvin and Hyman—illuminates the structural problem.

**Marvin Minsky’s** *Society of Mind* frames robust intelligence as a coalition of diverse, specialized processes with distinct internal models and distinct error profiles. When processes disagree, the disagreement itself is information. The system learns from the conflict. Effective verification requires precisely this: independent error modes that fail for different reasons.

Using one frontier generative model to verify another violates this requirement. It is not a second opinion; it is a statistical monoculture.

**Hyman Minsky’s** *Financial Instability Hypothesis* describes how stability itself breeds the conditions for crisis. Organizations can enter a “Ponzi” stage of financing where apparent assets are backed by borrowed credibility rather than fundamental value.

> **Interpretation (Ponzi Stage of Information Production).** Organizations can enter a regime where apparent epistemic assets (reports, analyses, forecasts, decisions) are financed by borrowed credibility. Professional polish functions as collateral within internal reporting systems. The system looks stable in the indicators because the indicators measure coherence, not correctness.

### 8.3 Market Selection on Lagging Indicators

> **Definition 13 (Observable Performance).** Let π_t denote observable performance metrics: throughput, velocity, time-to-ship, artifacts-per-quarter. These are measured and rewarded in real-time.

> **Definition 14 (Latent Verification Value).** Let V_t(θ) denote the value of verification capacity θ. This value remains latent (unobservable in π_t) until a forcing event occurs.

> **Assumption 8 (Selection on Observables).** Market selection (investment, hiring, contracts, survival) operates on observable π_t, not on latent V_t(θ):
> 
> Selection pressure_t = f(π_t),  ∂f/∂π > 0

> **Assumption 9 (Replicator Dynamics).** Population shares of organizational strategies evolve according to replicator dynamics: strategies with above-average observable performance gain market share, while those with below-average performance lose share. Observable performance π_t is decreasing in verification capacity: ∂π/∂θ < 0.

> **Conjecture 1 (Adverse Selection Against Verification).** Under verification reversal and Assumptions 8-9:
> 
> (i) High-verification strategies reduce π_t (slower throughput, higher costs) but increase V_t(θ).
> 
> (ii) Low-verification strategies increase π_t but reduce V_t(θ).
> 
> (iii) Selection pressure favors low-verification strategies in every period without a forcing event.
> 
> (iv) High-verification organizations are systematically competed away during the accumulation phase.
> 
> When forcing events are rare, the population converges to low-θ equilibrium:
> 
> lim_{t→∞} E[θ_t | no forcing event by t] = θ̲

*Supporting argument.* In each period without a forcing event, organizations with higher θ underperform on π_t and lose market share. Organizations with lower θ outperform and gain share. Under replicator dynamics:

dθ_{pop,t}/dt = γ(π_t(θ) - π̄_{pop,t})·θ

where θ_{pop,t} is population average verification capacity, π̄_{pop,t} is population average observable performance, and γ > 0 governs selection strength. Since ∂π/∂θ < 0 under verification reversal, θ_{pop} declines monotonically absent forcing events.

*Note:* Full formalization requires specifying the selection mechanism, forcing event distribution, and conditions under which high-θ strategies can survive. This conjecture draws on the logic of Minsky’s Financial Instability Hypothesis: strategies that appear conservative during stable periods are systematically penalized until they become rare.

> **Corollary 2 (Resilience Erosion).** Under Conjecture 1, the organizations best positioned to weather forcing events (high-θ firms) are precisely those selected against pre-forcing-event. System-wide resilience declines as the accumulation phase lengthens.

### 8.4 Structural Lock-In

Both self-correction channels fail for the same structural reason: the cascade equilibrium is self-reinforcing on the very signals that would guide correction.

Recursive verification operates on outputs optimized for coherence within the training manifold. It cannot escape the manifold because escape would require independent grounding, and independent grounding is precisely what the cost structure has made expensive.

Market selection operates on throughput metrics that reward low-θ strategies. It cannot correct toward high-θ strategies because the benefits of verification remain latent until crisis, and pre-crisis performance is what determines survival.

Neither channel has access to an independent rejection signal. Neither channel can price epistemic debt before forcing events demand payment.

-----

## 9. Empirical Hypotheses and Instrumentation

Theory without measurement is philosophy. This section operationalizes the framework into testable hypotheses and instrumentation baselines.

### Summary of Testable Predictions

|Hypothesis|Prediction                               |Expected Sign              |Falsification Condition                   |
|----------|-----------------------------------------|---------------------------|------------------------------------------|
|H1        |Productivity wedge grows                 |d(Gap_t)/dt > 0            |Correction burden grows ≤ throughput gains|
|H2        |Cascade fragility increases with coupling|∂²Frag/∂Density·∂Length > 0|No relationship observed                  |
|H3        |Endogeneity share rises                  |dα_t/dt > 0                |α_t stable or declining                   |
|H4        |Learning collapse in feedback loops      |dL_t/dt → 0                |Process improvements track errors         |
|H5        |Verification capacity erodes             |dθ_t/dt ≤ 0, dκ_t/dt < 0   |Capacity and skill stable                 |
|H6        |Language convergence                     |dγ_t/dt > 0                |Internal language remains distinct        |
|H7        |Irreversible lock-in accumulates         |dL_t/dt > 0                |Lock-in stock stable                      |

### Feasibility Table: Data Sources and Operational Settings

|Hypothesis               |Primary Data Sources                                                           |Operational Settings                                     |Measurement Feasibility                                           |
|-------------------------|-------------------------------------------------------------------------------|---------------------------------------------------------|------------------------------------------------------------------|
|H1 (Productivity wedge)  |GitHub/GitLab commit logs, Jira ticket data, code review timestamps            |Software development teams with version control          |High: data exists, requires pairing production and correction logs|
|H2 (Cascade fragility)   |PR dependency graphs, approval chains, incident postmortems                    |Organizations with documented workflows                  |Medium: requires reconstructing artifact flow graphs              |
|H3 (Endogeneity share)   |AI-disclosure metadata, watermarking systems, classifier-detected provenance   |Firms with AI usage tracking policies                    |Medium: provenance tagging not yet standard                       |
|H4 (Learning collapse)   |Incident management systems (PagerDuty, Opsgenie), process change logs         |DevOps/SRE teams with mature incident response           |High: data exists in ITSM systems                                 |
|H5 (Verification erosion)|Review time logs, headcount data, seeded defect injection experiments          |Engineering organizations willing to run controlled tests|Medium: seeded defects require experimental setup                 |
|H6 (Language convergence)|Internal document corpora, email/Slack archives, template repositories         |Organizations with searchable knowledge bases            |Medium: requires text analysis pipeline                           |
|H7 (Lock-in accumulation)|Tool deprecation logs, hiring criteria evolution, architecture decision records|Organizations with ADR practices                         |Low-Medium: historical data often incomplete                      |

### Worked Example: Software Development Instrumentation (Illustrative)

To illustrate concrete measurement, consider a hypothetical software development organization with N developers over T months. The numbers below are illustrative, not empirical results.

**Computing θ_t (verification capacity):**

θ_t = (Review hours with substantive comments)_t / (Total production hours)_t

Operationally: extract from GitHub PR metadata. Count reviews where reviewer requested changes or left comments requiring code modification (excluding approvals, LGTMs, typo-only fixes). Divide by total hours logged to code production.

*Expected baseline (illustrative):* In pre-AI-assistance regimes, θ_t ≈ 0.15-0.25 (roughly 1 hour of substantive review per 4-6 hours of coding). Under H5, we predict θ_t declining toward 0.05-0.10.

**Computing correction burden proxy:**

Churn_t = (Lines reverted within 14 days)_t / (Lines committed)_t

*Expected relationship:* If H1 holds, Churn_t should increase as throughput (commits per developer) increases, even while measured productivity (commits/hour) rises.

**Illustrative calculation (hypothetical numbers):** Suppose a team of 10 developers produces 5,000 lines/month with Churn_t = 0.08 pre-AI. Post-AI, they produce 12,000 lines/month with Churn_t = 0.15. Measured productivity rose 140%. But correction burden (lines requiring rework) rose from 400 to 1,800 lines/month (350%). The wedge is opening.

*Data source note:* GitClear (2024) reports aggregate churn trends directionally consistent with this pattern across their 153M-line dataset, though they do not compute θ_t directly and the specific numbers above are illustrative rather than drawn from their report.

### 9.1 H1: Divergence Between Measured and Verification-Adjusted Productivity

**Hypothesis:**

d/dt(TFP_t^meas - TFP_t^adj) > 0

**Key proxies:**

- **Artifact throughput**: Reports produced, code committed, tickets closed, forecasts generated.
- **Validation lag**: Time from artifact creation to substantive review, audit completion rates, review queue depth.
- **Correction burden**: Rework hours per artifact hour, incident remediation costs, rollback frequency, post-deployment defect density.

**Falsification condition:** If correction burden grows slower than or equal to throughput gains, the hypothesis fails.

**Critical decomposition:** Time spent reading code vs. writing it typically follows a 10:1 ratio (Martin, 2008). Instrumentation should separately track: time-to-write (AI-accelerated), time-to-understand (potentially AI-degraded), and time-to-debug (lagging indicator of verification gaps).

### 9.2 H2: Cascade Fragility Increases with Coupling and Length

**Hypothesis:**

∂²Fragility / (∂NetworkDensity · ∂CascadeLength) > 0

**Instrumentation baseline:**

- **Handoff graph reconstruction**: Map artifact flow through organizations.
- **Error propagation distance**: When errors are detected, how many hops did they survive before detection?
- **Correlated failure rates**: Do errors cluster by position in the chain?

### 9.3 H3: Rising Endogeneity Share in Measurement Substrates

**Hypothesis:**

dα_t/dt > 0

**Concrete operationalization for α_t:** For a given data pipeline, implement provenance tagging at ingestion. Each data point receives a flag: `human`, `model`, or `sensor`. Then compute:

α_t = Σ_{i: tag_i = model} w_i · Var(X_i) / Σ_i w_i · Var(X_i)

where w_i is the importance weight of regressor X_i.

**Data feasibility:** GitHub PR descriptions and commit messages (classifier-detectable), financial research reports with AI-disclosure metadata, corporate forecast databases with generation method flags, news aggregators with source provenance.

### 9.4 H4: Learning Collapse in Feedback Loops

**Instrumentation baseline:**

- **Postmortem-to-process link rate**: How often do incidents result in policy or tooling changes?
- **Recurrence rate**: How often do similar errors recur after ostensible fixes?
- **Gate coverage**: What fraction of artifacts pass through validation checkpoints?

### 9.5 H5: Erosion of Verification Capacity and Capability

**Hypothesis:**

dθ_t/dt ≤ 0,  dκ_t/dt < 0

**Concrete operationalization for θ_t:** In a software development context, define:

θ_t = Review hours with substantive comments / Total production hours

where “substantive comment” requires code modification or design discussion (excluding approvals, typo fixes, and rubber-stamp LGTMs).

**Concrete operationalization for κ_t:** Seeded defect detection rate. Periodically inject known bugs into the review pipeline at random intervals. Measure detection rate over time. If κ_t declines while θ_t is stable, capability is eroding faster than capacity.

### 9.6 H6: Language and Abstraction Convergence

**Hypothesis:**

dγ_t/dt > 0  ⟹  ∂Fragility/∂γ > 0

where γ_t measures coupling between internal language and model-preferred distributions.

**Instrumentation baseline:**

- **Jargon overlap**: Phrase frequency drift between internal documents and model training proxies.
- **Template convergence**: Similarity between internal report structures and model-generated templates.
- **Acceptance friction**: Do model-generated artifacts receive lighter review than human-generated artifacts?

### 9.7 H7: Irreversibility and Lock-In

**Instrumentation baseline:**

- **Tool deprecation**: Track removal of manual verification tools and alternative pathways.
- **Skill pipeline**: Monitor hiring criteria, training investment, promotion patterns in verification functions.
- **Architectural commitments**: Count removal of validation gates, adoption of auto-approve workflows.

-----

## 10. Discussion and Implications

### 10.1 Implications for Measurement

Productivity statistics that ignore verification costs and epistemic debt do not measure what they claim to measure. When artifact volume can grow independently of verified value creation, TFP becomes a misleading indicator.

A verification-adjusted measurement framework would track verification capacity as an asset, epistemic debt as a liability, and correction burden as a cost.

### 10.2 Implications for Institutional Design

Verification capacity should be treated as critical infrastructure: maintained, invested in, protected from quarterly optimization pressures. The analogy to financial regulation is precise. We do not allow banks to optimize away capital reserves simply because the reserves are costly and crises are rare.

### 10.3 Implications for AI Development

Heterogeneity in models, training distributions, and verification methods reduces correlated failure risk. A monoculture of frontier models trained on similar data with similar objectives is a fragility multiplier.

### 10.4 Limitations and Scope Conditions

This framework applies when verification costs exceed production costs for a substantial class of artifacts. Several boundary conditions limit its scope:

**Domains with cheap automated verification.** In software with robust test suites, continuous integration pipelines, and type systems, verification can remain cheaper than production.

**High-stakes, low-volume decisions.** Domains where errors carry catastrophic consequences and artifact volume is low maintain verification-heavy regimes regardless of cost.

**Artifacts with immediate, unambiguous feedback.** When ground truth is revealed quickly and costlessly, verification occurs naturally through outcome observation.

**What would falsify this framework:** Evidence that verification costs scale sublinearly with artifact volume under AI assistance; demonstration that recursive AI verification achieves independent rejection signals (ρ → 0); or market evidence that high-verification strategies outcompete low-verification strategies pre-crisis.

### 10.5 Physical Constraints on Synthetic Productivity

Global data center electricity consumption is projected to double between 2022 and 2026, with AI workloads driving a substantial share of this growth (IEA, 2024). This creates a binding constraint: measured productivity gains from artifact generation are partially offset by rising energy costs and infrastructure requirements.

-----

## 11. Conclusion

Verification reversal changes equilibrium behavior and the meaning of measured output. When generation becomes cheaper than verification, the link between artifact volume and underlying cognitive work breaks. Organizations rationally cascade. Productivity metrics overstate welfare. Measurement systems consume contaminated inputs. Self-correction mechanisms fail.

This paper has provided:

1. **Proposition 1**: A sequential forwarding game with cascade formation under high verification costs, including both forward and verify cascade regions.
1. **Proposition 2**: Conditions under which the wedge between measured and verification-adjusted productivity grows over time.
1. **Propositions 3-4**: Endogeneity bias and recognition lag extension from measurement contamination.
1. **Proposition 5**: Structural failure of recursive verification under correlated error.
1. **Conjecture 1**: Adverse selection against verification capacity under market dynamics.
1. **H1-H7**: A falsifiable empirical agenda with instrumentation baselines.

The framework predicts that conventional productivity statistics will overstate welfare gains from generative AI by ignoring verification costs and epistemic debt accumulation. The measured miracle may be borrowed time.

-----

## Acknowledgments

The “Double Minsky” framework in this paper owes an obvious debt to both Marvin Minsky and Hyman Minsky, whose work on distributed intelligence and financial instability respectively illuminates the dynamics of epistemic leverage.

-----

## References

Acemoglu, D., Dahleh, M. A., Lobel, I., & Ozdaglar, A. (2011). Bayesian learning in social networks. *Review of Economic Studies*, 78(4), 1201-1236.

Banerjee, A. V. (1992). A simple model of herd behavior. *The Quarterly Journal of Economics*, 107(3), 797-817.

Bikhchandani, S., Hirshleifer, D., & Welch, I. (1992). A theory of fads, fashion, custom, and cultural change as informational cascades. *Journal of Political Economy*, 100(5), 992-1026.

Brynjolfsson, E., Li, D., & Raymond, L. R. (2023). Generative AI at work. *NBER Working Paper No. 31161*.

Gale, D., & Hellwig, M. (1985). Incentive-compatible debt contracts: The one-period problem. *Review of Economic Studies*, 52(4), 647-663.

GitClear. (2024). *Coding on Copilot: 2023 Data Suggests Downward Pressure on Code Quality (incl. 2024 projections)*. Technical report. Retrieved January 2025 from https://www.gitclear.com/coding_on_copilot_data_shows_ais_downward_pressure_on_code_quality

International Energy Agency. (2024). *Electricity 2024: Analysis and Forecast to 2026*. IEA, Paris. Retrieved January 2025 from https://www.iea.org/reports/electricity-2024. Licence: CC BY 4.0.

Martin, R. C. (2008). *Clean Code: A Handbook of Agile Software Craftsmanship*. Prentice Hall.

Minsky, H. P. (1986). *Stabilizing an Unstable Economy*. Yale University Press.

Minsky, M. (1986). *The Society of Mind*. Simon & Schuster.

Noy, S., & Zhang, W. (2023). Experimental evidence on the productivity effects of generative artificial intelligence. *Science*, 381(6654), 187-192.

Pearce, H., Ahmad, B., Tan, B., Dolan-Gavitt, B., & Karri, R. (2022). Asleep at the keyboard? Assessing the security of GitHub Copilot’s code contributions. *2022 IEEE Symposium on Security and Privacy (SP)*, 754-768.

Peng, S., Kalliamvakou, E., Cihon, P., & Demirer, M. (2023). The impact of AI on developer productivity: Evidence from GitHub Copilot. *arXiv preprint arXiv:2302.06590*.

Syverson, C. (2011). What determines productivity? *Journal of Economic Literature*, 49(2), 326-365.

Townsend, R. M. (1979). Optimal contracts and competitive markets with costly state verification. *Journal of Economic Theory*, 21(2), 265-293.

Verrecchia, R. E. (1982). Information acquisition in a noisy rational expectations economy. *Econometrica*, 50(6), 1415-1430.

Wooldridge, J. M. (2010). *Econometric Analysis of Cross Section and Panel Data* (2nd ed.). MIT Press.

-----

## Appendix A: Notation Summary

|Symbol      |Definition                                          |
|------------|----------------------------------------------------|
|Y_t         |Artifact volume at time t                           |
|C_prod(Y)   |Cost of producing Y artifacts                       |
|C_ver(Y)    |Cost of verifying Y artifacts                       |
|Δc          |Verification cost gap: c_V - c_F                    |
|ω ∈ {H, L}  |Artifact quality state (High/Low)                   |
|s_i ∈ {h, ℓ}|Agent i’s private signal                            |
|q           |Signal precision: P(s=h|ω=H) = P(s=ℓ|ω=L)           |
|π_i         |Agent i’s posterior belief that ω = H               |
|π^cut       |Indifference cutoff: 1 - Δc/(B - R + D_i)           |
|π^F         |Forward cascade threshold (depends on q and π^cut)  |
|π^V         |Verify cascade threshold (depends on q and π^cut)   |
|B           |Benefit of catching low-quality artifact            |
|R           |Reputational cost of blocking                       |
|D           |Damage from deployed low-quality artifact           |
|θ_t         |Verification capacity at time t                     |
|κ_t         |Verification skill (capability) at time t           |
|v(θ)        |Verification rate function                          |
|TFP_t^meas  |Measured total factor productivity                  |
|TFP_t^adj   |Verification-adjusted total factor productivity     |
|α_t         |Endogeneity share: model-generated variance fraction|
|τ           |Recognition lag                                     |
|D_e(T)      |Epistemic debt accumulated by time T                |
|ρ₁₂         |Cross-model error correlation                       |

-----

## Appendix B: Proofs

### B.1 Proof of Proposition 1 (Cascade Formation)

**Step 1: Indifference cutoff characterization.**

From Lemma 2, agent i verifies if and only if:

(1 - π_i(s_i)) > Δc/(B - R + D_i)

Rearranging: agent i verifies iff π_i(s_i) < 1 - Δc/(B - R + D_i) ≡ π^cut.

This defines the indifference cutoff π^cut: agent verifies when posterior is below π^cut, forwards when posterior is above π^cut.

**Step 2: Forward cascade threshold derivation.**

Suppose the prior entering agent i’s decision is π_{i-1}. Using the Bayesian update from Lemma 1:

With signal s_i = h:

π_i(h) = q·π_{i-1} / [q·π_{i-1} + (1-q)(1-π_{i-1})]

With signal s_i = ℓ:

π_i(ℓ) = (1-q)·π_{i-1} / [(1-q)·π_{i-1} + q(1-π_{i-1})]

A forward cascade occurs when even the low signal s_i = ℓ produces π_i(ℓ) ≥ π^cut. This occurs when π_{i-1} is sufficiently high that the bad signal cannot overcome the prior.

Solving π_i(ℓ) = π^cut for π_{i-1}:

π^F = q·π^cut / [q·π^cut + (1-q)(1-π^cut)]

For π_{i-1} ≥ π^F, even s_i = ℓ yields π_i(ℓ) ≥ π^cut, so the agent forwards regardless of signal.

**Step 3: Verify cascade threshold derivation.**

Symmetrically, a verify cascade occurs when even the high signal s_i = h produces π_i(h) ≤ π^cut. This occurs when π_{i-1} is sufficiently low that the good signal cannot overcome the prior.

Solving π_i(h) = π^cut for π_{i-1}:

π^V = (1-q)·π^cut / [(1-q)·π^cut + q(1-π^cut)]

For π_{i-1} ≤ π^V, even s_i = h yields π_i(h) ≤ π^cut, so the agent verifies regardless of signal.

**Step 4: Interior region verification.**

Note that π^V < π^cut < π^F when q > 0.5 (signals are informative). In the interior region π_{i-1} ∈ (π^V, π^F):

- If s_i = h, then π_i(h) > π^cut, so agent forwards
- If s_i = ℓ, then π_i(ℓ) < π^cut, so agent verifies

Actions depend on private signals, and beliefs update accordingly.

**Step 5: Information blockage.**

In the cascade regions, all agents take the same action regardless of signal. Therefore:

In forward cascade: P(a_i = F | ω = H) = P(a_i = F | ω = L) = 1

In verify cascade: P(a_i = V | ω = H) = P(a_i = V | ω = L) = 1

Observing a_i provides no information about ω. Beliefs do not update:

π_i = π_{i-1}

This is consistent with the cascade: once in the cascade region, the system remains there.

**Step 6: Equilibrium verification.**

*Sequential rationality:* In the interior region, agents play threshold strategies that are optimal given beliefs. In cascade regions, the dominant action (forward or verify) is optimal regardless of signal because posteriors cannot cross π^cut.

*Belief consistency:* In the interior region, beliefs update via Bayes’ rule from observed actions and signals. In cascade regions, actions are uninformative, so beliefs remain constant, which is Bayes-consistent. ∎

### B.2 Proof of Proposition 2 (Synthetic Productivity)

The measured-to-adjusted productivity gap is:

Gap_t = TFP_t^meas - TFP_t^adj = Y_t/F(K_t, L_t) - Y_t·v(θ_t)/F(K_t, L_t) = Y_t(1 - v(θ_t))/F(K_t, L_t)

Taking the time derivative:

d(Gap_t)/dt = (1/F(K_t, L_t))[Ẏ_t(1 - v(θ_t)) - Y_t·v’(θ_t)·θ̇_t] + (terms from Ḟ)

Under the assumptions:

- Ẏ_t > 0 (artifact volume grows)
- θ̇_t ≤ 0 (verification capacity bounded or declining)
- v’(θ) > 0 (verification rate increases with capacity)

The first term Ẏ_t(1 - v(θ_t)) > 0 since v(θ_t) < 1.

The second term -Y_t·v’(θ_t)·θ̇_t ≥ 0 since θ̇_t ≤ 0.

Both terms are non-negative, with at least one strictly positive. Therefore:

d(Gap_t)/dt > 0 ∎

### B.3 Proof of Proposition 4 (Recognition Lag)

Let η̂_t denote the observed problem signal at time t. Under the assumptions:

η̂_t = η_t + noise + smoothing(X_t^model)

where η_t is the true problem signal and the smoothing term captures how model-generated content reduces anomaly visibility.

Detection occurs when cumulative evidence exceeds threshold:

τ = min{t : Σ_{s=0}^t |η̂_s| > η̄}

With endogeneity share α, the effective signal magnitude is:

E[|η̂_t|] = (1 - α)E[|η_t|] + αE[|η_t^smoothed|]

Since model-generated content smooths anomalies: E[|η_t^smoothed|] < E[|η_t|].

Therefore:

∂E[|η̂_t|]/∂α = E[|η_t^smoothed|] - E[|η_t|] < 0

Higher α reduces expected signal magnitude per period. Since detection requires cumulative evidence to exceed a fixed threshold η̄, and per-period evidence is reduced, more periods are required:

dτ/dα > 0 ∎

-----

## Appendix C: Instrumentation Details

### C.1 H1: TFP Divergence - Detailed Measurement

**Artifact throughput measures:**

- Reports produced per analyst per week
- Code commits and lines changed per developer
- Ticket closure rate and time-to-close
- Forecast volume and update frequency

**Validation lag measures:**

- Time from artifact creation to first substantive review
- Time from artifact creation to validation sign-off
- Fraction of artifacts receiving deep review vs. light edit
- Review queue depth and wait times

**Correction burden measures:**

- Rework hours per initial artifact hour
- Incident remediation costs (labor + system downtime)
- Rollback frequency and scope
- Post-deployment bug density

**Implementation:** Pair production logs with review/correction logs. Track (Y_t, V_t, C_t) where Y_t is artifact volume, V_t is verification effort, and C_t is correction burden. Compute:

Gap_t = Y_t/F(K_t, L_t) - (Y_t - C_t)/F(K_t, L_t + V_t)

Test whether d(Gap_t)/dt > 0.

### C.2 H5: Verification Capacity - Seeded Defect Protocol

**Seeded defect injection:**

1. Create a library of known defects by category (security, logic, performance)
1. Inject defects at random intervals into the review pipeline
1. Track detection rate by defect type and reviewer
1. Compute κ_t as: Detected defects / Injected defects

**Control for difficulty:** Maintain constant defect difficulty distribution across time periods.

**Measurement frequency:** Monthly injection batches with quarterly aggregate analysis.

### C.3 H3: Endogeneity Share - Provenance Tracking

**Provenance tagging options:**

1. **Watermarking**: Embed model identifiers in generated text at generation time
1. **Classifier-based**: Train classifiers to detect model-generated content post-hoc
1. **Audit sampling**: Manually audit random samples for generation provenance

**α_t computation:**
For each measured series X_t, decompose:
X_t = X_human,t + X_model,t + X_sensor,t

Compute:
α_t = Var(X_model,t) / Var(X_t)

**Validation:** Cross-check classifier-based detection against known watermarked content to estimate classifier accuracy.
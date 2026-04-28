# DHITL, Democratic Humans In The Loop

## Why Infrastructure Is All You Need for AI Safety

**Jean Hugues Noël Robert, baron Mariani**

Institut Mariani, 1 cours Paoli, F-20250 Corte, Corsica

jhr@baronsmariani.org

*Draft — April 2026 — Open work. Published at `github.com/JeanHuguesRobert/marenostrum`. CC BY-SA 4.0. Not for citation without attribution.*

---

## Abstract

Current AI safety discourse focuses on model-level interventions: alignment techniques, constitutional AI, red-teaming, capability evaluations. We argue this focus is necessary but insufficient. The deeper problem is structural: no model-level safeguard can remain effective if the infrastructure on which AI systems run is itself concentrated, opaque, or captured by actors whose interests diverge from humanity's collective welfare. We propose a framework we call **Democratic Humans in the Loop (DHITL)**, which extends the technical notion of "human in the loop" to its political precondition: a structurally democratic governance of compute infrastructure. We formalize a five-layer architecture — physical, economic, political, cognitive, and technical — and argue that this architecture is both necessary and, if correctly instantiated, sufficient to maintain meaningful human sovereignty over AI systems at civilizational scale. A key contribution is the concept of **Compute Exergy** (Xc), a measurable unit that quantifies useful, certified, traceable compute as distinct from raw computational power, enabling democratic oversight of AI infrastructure the way energy accounting enables grid governance. We identify eleven structural failure modes of current approaches — including FM-11, the outer optimizer governance gap introduced by Decoupled DiLoCo (Douillard et al., 2026) — position DHITL relative to existing AI safety frameworks, and outline formal conditions under which democratic correction remains faster than algorithmic drift.

**Keywords**: AI safety, AI governance, human in the loop, democratic oversight, compute governance, infrastructure sovereignty, digital democracy, exergy, distributed training, outer optimizer governance

---

## 1. Introduction

### 1.1 The inadequacy of model-level safety

The dominant paradigm in AI safety concentrates on the artifact: the model weights, the training objective, the reward function, the constitutional principles embedded in fine-tuning. This paradigm has produced genuine progress — reinforcement learning from human feedback (RLHF), constitutional AI, scalable oversight, interpretability research — and we do not contest its value at the technical level.

We contest its sufficiency.

A perfectly aligned model running on infrastructure controlled by an unaccountable actor provides no safety guarantee at the systemic level. The safety of the artifact is decoupled from the safety of the system. A fully interpretable language model deployed at scale by a single entity with no democratic accountability is not safe in any sense that matters for civilizational risk — it is merely legible.

This paper makes a simple claim: **AI safety, properly understood, is an infrastructure problem before it is a model problem.** The question is not only "what does the model do?" but "who controls the conditions under which the model runs, and under what governance?" These are questions that model-level interventions cannot answer, because they belong to a different layer of the system.

### 1.2 The structural gap

In April 2026, five actors — Microsoft/OpenAI, Google, Amazon, Meta, and xAI — control approximately 85% of frontier AI compute capacity worldwide. The regulatory responses to date (California SB 53, New York RAISE Act, EU AI Act) address disclosure and incident reporting thresholds, but share a fundamental limitation: they measure raw compute (10²⁶ floating-point operations) rather than the quality, accountability, or democratic legitimacy of compute use. They create transparency obligations toward regulators, not democratic accountability toward the populations affected.

This is the structural gap DHITL addresses.

A significant recent development sharpens the argument. Decoupled DiLoCo (Douillard et al., 2026) has demonstrated that frontier-scale model training — a 12-billion-parameter model across four geographically separate regions — is achievable at internet-scale bandwidth (2–5 Gbps), without co-located custom interconnects. This result falsifies the long-standing assumption that compute concentration is technically required for frontier training. If concentration is not technically required, its persistence is a political and governance failure, not a physical necessity. The DHITL argument — that democratic distribution of compute infrastructure is both possible and necessary — is thereby strengthened on the technical dimension. However, DiLoCo simultaneously introduces a new governance challenge that DHITL must address: even when hardware is physically distributed, whoever controls the gradient aggregation mechanism (the "outer optimizer") retains effective control over what the model learns. This is Failure Mode 11, analyzed in Section 5.

### 1.3 The argument in outline

We proceed as follows. Section 2 surveys existing AI safety frameworks and identifies their shared blind spot: the absence of a theory of infrastructure governance. Section 3 introduces the DHITL framework, its five layers, and their interdependencies. Section 4 formalizes the concept of Compute Exergy (Xc) as the economic unit of the framework. Section 5 analyzes eleven structural failure modes. Section 6 addresses the political philosophy of the framework's foundational axiom — the "democratic faith" — and defends it as a safety heuristic under radical uncertainty. Section 7 specifies conditions for stability. Section 8 positions the contribution relative to existing literature. Section 9 concludes.

---

## 2. Related Work and the Shared Blind Spot

### 2.1 Model-level safety approaches

**Constitutional AI** (Bai et al., 2022) embeds normative principles into the training process via a constitutional document. It addresses alignment at the artifact level but leaves governance of the artifact's deployment unspecified.

**Scalable oversight** (Bowman et al., 2022; Irving & Askell, 2019) addresses the problem of supervising AI systems whose capabilities exceed human judgment in specific domains. It assumes the existence of humans capable of providing meaningful oversight but does not address the structural conditions under which such humans have the authority and independence to act on their judgments.

**Interpretability research** (Anthropic mechanistic interpretability work; EleutherAI; etc.) aims to make model internals legible. Legibility is necessary but not sufficient: a fully interpretable system controlled by a non-accountable actor can still be used in ways that harm collective interests.

**AI governance frameworks** (EU AI Act, NIST AI RMF, ISO/IEC 42001) address procedural compliance but do not constitute democratic governance. Compliance with a standard adopted by regulators is not equivalent to accountability to the populations affected by AI systems.

### 2.2 The shared blind spot

Across these approaches, a consistent gap appears: **none provides a theory of who legitimately controls the infrastructure on which AI systems run, and through what governance mechanism.** The implicit assumption is that infrastructure control is either: (a) a market question, settled by competition, or (b) a regulatory question, settled by technical standard-setting.

We argue both assumptions are mistaken. Infrastructure control is a political question, and political questions require political answers — specifically, democratic ones. Not because democracy is proven optimal, but because it is the only known mechanism that structurally prevents the irreversible concentration of power.

### 2.3 Compute governance as an emerging field

The closest existing work to our concerns is found in the "compute governance" literature (Sastry et al., 2024; Heim et al., 2024; Anderljung et al., 2023). This work argues that compute is a chokepoint for frontier AI development and proposes governance mechanisms (reporting requirements, export controls, know-your-customer obligations for chip sales). We build on this foundation but extend it in two directions: (1) we ask not just how to govern who *has* compute, but how to govern what compute *does* and under whose democratic authority; (2) we propose an economic unit — Compute Exergy — that makes this governance tractable.

Decoupled DiLoCo (Douillard et al., 2026) provides the first production-scale demonstration that frontier training can be distributed across geographically separate nodes at internet-scale bandwidth. This result is important for the compute governance literature: it demonstrates that hardware-level concentration is a policy variable, not a technical constant. It also introduces a new governance object — the outer optimizer — that is not addressed by existing compute governance frameworks, including the initial version of DHITL. FM-11 (Section 5) formalizes this gap.

---

## 3. The DHITL Framework

### 3.1 From technical to democratic HITL

The notion of "human in the loop" (HITL) in AI systems typically refers to the presence of a human decision point in an automated pipeline — a human who can review, correct, or veto system outputs. This is a technical design choice. Its value depends entirely on the political conditions of the human who is "in the loop": their independence, their capacity to act on their judgment, and their accountability to the people affected by the system's outputs.

**Democratic Humans in the Loop (DHITL)** extends HITL from a technical to a constitutional concept. The claim is:

> *A "human in the loop" provides a meaningful safety guarantee if and only if: (a) the human has the cognitive capacity to exercise genuine judgment; (b) the human has the political independence to act on that judgment without fear of reprisal; and (c) the human is accountable to the population affected by the AI system's outputs through a democratic mechanism.*

Condition (c) is the condition that existing HITL frameworks do not address and that DHITL makes central.

### 3.2 The five-layer architecture

DHITL requires a specific infrastructure to instantiate conditions (a), (b), and (c). We propose a five-layer model:

**Layer 1 — Physical (Energy Sovereignty)**
The material basis of AI computation is electrical energy. Democratic oversight of AI systems begins with democratic governance of the energy that powers them. Solar irradiation, wind, and other renewable sources offer, in principle, a distributed physical basis that resists monopolization. The key structural property required at this layer is: *no single actor controls a decisive fraction of the energy supply for AI computation*.

**Layer 2 — Economic (Universal Dividend)**
Cognitive participation in democratic governance requires material security. A population living under existential economic precarity cannot exercise genuine political sovereignty, including oversight of AI systems. Layer 2 provides the economic conditions for Layer 3 through a universal dividend funded by the economic rent of the physical infrastructure (energy production, compute capacity). The structural property required: *survival is decoupled from compliance with the decisions of compute-controlling actors*.

**Layer 3 — Political (Democratic Governance, 1p1v)**
The invariant of the framework: **one person, one vote**. Not as a moral axiom but as a safety mechanism — the only known structural barrier against the irreversible accumulation of control over AI infrastructure by any single actor or coalition. Democratic governance at this layer defines: (a) what compute uses are permitted; (b) what infrastructure configurations are required; (c) what emergency powers exist and under what conditions. The structural property required: *decisions affecting the AI infrastructure are made by processes accountable to all affected persons, with equal weight*.

**Layer 4 — Cognitive (Augmented Sovereignty)**
Democratic governance of complex technical systems requires cognitive augmentation. We introduce the concept of **Cogentia** — the dynamic cognitive identity of a person, distinct from any representation of it — and **personal digital twins**: AI systems that generate recommendations for their principals without ever holding sovereign authority. The invariant: *a digital twin cannot vote, cannot hold a mandate, cannot act as a legal agent*. Its only function is to augment its principal's capacity to exercise their own sovereign judgment. The structural property required: *cognitive augmentation does not transfer sovereignty from persons to their instruments*.

**Layer 5 — Technical (Open Core, Traceable Decisions)**
The technical substrate must be: (a) open source at the level of critical decisions (the "crucial core" — defined democratically, not technically); (b) fully traceable (every decision affecting Layer 3 is logged, auditable, and attributable); and (c) crypto-agile (resistant to known and foreseeable cryptographic attacks, including post-quantum). The structural property required: *technical opacity cannot be used to circumvent political accountability.*

**Extension for distributed training (v0.2):** Layer 5 now explicitly extends to the *algorithmic control layer* of distributed training, not only to inference and deployment. The outer optimizer in any distributed training run affecting the crucial core must satisfy the same openness, traceability, and accountability requirements as the compute infrastructure itself. An open-source outer optimizer implementation, with cryptographically auditable gradient aggregation logs, is a Layer 5 requirement for democratically governed training runs. See FM-11.

### 3.3 The causal chain

The five layers are not independent. They form a causal chain with a feedback loop:

```
Photons → Energy (L1)
        → Economic redistribution (L2)
        → Democratic capacity (L3)
        → Augmented cognitive judgment (L4)
        → Traceable technical decisions (L5)
        → Governance of compute infrastructure
        → Governance of which models run, at what scale,
          and under what outer optimizer
        → AI system behavior at civilizational scale
        → Feedback into the photon-to-inference chain
```

The key insight is directional: **the political layer (L3) governs the technical layer (L5), not the reverse.** The technical layer defines *what is possible*; the political layer defines *what is permitted and required*. Current AI governance frameworks invert this relationship, allowing technical actors to define the scope of their own regulation.

---

## 4. Compute Exergy: An Economic Unit for Democratic Oversight

### 4.1 The measurement problem

Democratic governance of AI infrastructure requires a common unit of account — a way to measure what is being governed that is: (a) physically grounded (not purely financial); (b) quality-adjusted (not just raw compute); (c) traceable (attributable to specific actors and decisions); and (d) democratic-safety-aware (incorporating a measure of the governance quality of the compute).

Raw computational metrics (FLOP counts, GPU-hours) fail conditions (b), (c), and (d). Financial metrics (dollar cost of training runs) fail conditions (a) and (c). We propose **Compute Exergy (Xc)** as a metric that satisfies all four conditions.

### 4.2 The thermodynamic analogy

In thermodynamics, *exergy* is the fraction of energy that can be converted into useful work in a given environment. Unlike energy, which is conserved, exergy is destroyed by irreversible processes — it measures not the quantity of energy but its *quality*, its capacity to do useful work in context.

The analogy to compute is precise: two identical energy inputs do not produce the same useful AI inference output if one is associated with optimized hardware, low overhead, guaranteed service levels, and verified governance, while the other is associated with inefficient hardware, high overhead, no service guarantees, and opaque control. The thermodynamic concept of exergy captures exactly this context-dependence of "useful work" production.

**Compute Exergy** is defined as:

```
Xc = E × η_hw × η_sys × η_sla × η_gov
```

where:

- **E** is available energy (kWh), contextualized by location, time, and source mix
- **η_hw** ∈ [0,1] is hardware efficiency (useful FLOP per joule, adjusted for model architecture and quantization)
- **η_sys** ∈ [0,1] is system efficiency (inverse PUE × network overhead × orchestration loss)
- **η_sla** ∈ [0,1] is service quality factor (latency guarantees, uptime, priority tier)
- **η_gov** ∈ [0,1] is governance quality factor (traceability, democratic accountability, third-party safety certification)

**The nullity condition**: Xc = 0 if η_gov = 0. Compute that is not traceable and not democratically accountable produces no Exergy in the DHITL framework, regardless of its raw quantity. This is the formal expression of the principle: *an unattributable act is legally void* (Charte du Soleil Méditerranéen, 2026).

### 4.3 The Compute eXergy Unit (CXU)

**1 CXU** is defined as the certified capacity to produce a standardized inference workload under a defined service level agreement, anchored in a verifiable physical measurement.

**Reference inference** (to be standardized): 1,000 output tokens from a reference open-weights model (e.g., Llama 3 70B, FP16 precision), at ≤ 200ms P95 latency.

**Governance certification levels** (discrete, for contractual clarity):

| Level | η_gov | Conditions |
|---|---|---|
| Uncertified | 0.00 | No audit |
| Self-declared | 0.25 | Declaration + ex-post random audit |
| Compliant | 0.50 | Annual third-party audit |
| Verified | 0.75 | Continuous audit + red-teaming |
| Frontier-certified | 1.00 | SB53/RAISE/EU AI Act + METR evaluation |

**The insurance layer**: Every CXU emission is associated with an explicit risk premium. The premium is not optional — it is constitutive of the CXU's validity. Uninsured compute (CXU-U) trades at a discount to insured compute (CXU-A). The spread between CXU-A and CXU-U is a market price for governance risk, functioning as an economic oracle of actual infrastructure quality.

### 4.4 What the CXU is not

The CXU is not a proof-of-work token: it certifies compute that would have occurred anyway, rather than consuming energy to generate itself. It is not a stablecoin: its value is anchored to the marginal cost of certified compute, not to a fiat currency. It is not a software license: it certifies infrastructure, not model weights. It is not a speculative instrument: its issuance requires physical measurement attestation.

**Extension for distributed training (v0.2):** A CXU associated with a training run certified under DHITL must additionally specify: (a) the outer optimizer implementation (open-source reference required); (b) the gradient aggregation log (cryptographically auditable); and (c) the ACCI (Algorithmic Control Concentration Index, defined in Appendix A) of the training run. A training run where a single actor controls the outer optimizer for the entire run receives η_gov ≤ 0.25 regardless of hardware distribution.

---

## 5. Structural Failure Modes

### 5.1 Failure modes of the framework

We identify eleven structural failure modes — conditions under which DHITL could fail to maintain meaningful democratic oversight of AI systems. Explicit failure mode analysis is, in our view, a necessary component of any credible safety framework.

**FM-1: Identity failure (Sybil attack on 1p1v)**
The "one person, one vote" invariant requires reliable human identity verification. No current solution fully satisfies this requirement: biometric systems are capturable by state actors; web-of-trust systems are vulnerable to Sybil attacks at scale; state-anchored identity systems risk political capture. This failure mode is open. We treat it as a fundamental unsolved problem that must be explicitly acknowledged, not hidden.

**FM-2: Formal democracy, operational oligarchy**
Equal formal votes do not imply equal political influence. Narrative power, technical expertise, coordination capacity, and time availability distribute unequally even in formally equal voting systems. A system that is procedurally democratic can be operationally oligarchic. DHITL mitigates but does not eliminate this failure mode through mandatory transparency, revocable mandates, and separation of powers across layers.

**FM-3: Complexity capture**
Even with full transparency, the system's complexity creates a comprehension filter: those who understand the system govern; others validate. This is a structural property of technically complex democratic systems. Mitigation requires strong abstraction layers (simple user-facing interfaces masking technical complexity) and explicit restrictions on the scope of decisions that require technical understanding.

**FM-4: Weaponized fork**
DHITL includes an explicit right to fork — to split the network in cases of fundamental governance failure. This right can be weaponized: a powerful actor can threaten fork to extract concessions. Constitutional constraints on fork conditions (supermajority threshold, mandatory consultation period, automatic sunset on emergency powers) mitigate but do not eliminate this risk.

**FM-5: Cascade failure (energy-politics coupling)**
The five-layer architecture creates systemic coupling: a major energy disruption (climate event, geopolitical crisis) can trigger economic instability, which undermines democratic participation, which degrades governance quality, which reduces Xc values, which causes financial losses in the CXU market, which further destabilizes the system. The framework requires explicit resilience design at each coupling point.

**FM-6: Cognitive sovereignty erosion**
Personal digital twins (Layer 4) are designed to augment sovereign judgment without replacing it. But the boundary between "recommendation" and "effective decision" is not technically enforceable — it is a social norm. If digital twins become the de facto decision-makers (because their recommendations are almost always followed), Layer 3 sovereignty becomes nominal. The anti-capture condition here is behavioral, not architectural, which makes it fragile.

**FM-7: Quantum cryptographic break (retroactive)**
Post-quantum cryptographic standards are implemented prospectively, but historical records signed under pre-quantum standards become contestable once quantum computers achieve sufficient capability. Periodic re-signing of historical states mitigates this risk but requires continuous governance attention.

**FM-8: Regulatory capture disguised as safety**
Safety certification processes (η_gov) can themselves be captured by actors who benefit from high certification barriers — creating an incumbent protection racket disguised as safety governance. The separation of audit authority from governance authority, and the availability of a low-barrier entry level (η_gov = 0.25, self-declared with random ex-post audit), are designed to mitigate this.

**FM-9: Compute laundering**
Actors who do not wish to participate in DHITL governance can route compute through uncertified jurisdictions, fragment training runs below certification thresholds, or use certified compute for benign tasks while performing sensitive work elsewhere. Complete prevention is impossible; making laundering economically unattractive (through CXU market premiums for certified compute) and politically visible (through the global compute registry) is the realistic goal.

**FM-10: Faith collapse**
The framework rests on a foundational normative commitment — the "democratic faith" discussed in Section 6. If this commitment is widely abandoned (through demonstrated failure of democratic institutions, epistemic crisis, or coordinated delegitimization campaigns), the political basis for Layer 3 collapses. This is not a technical failure mode; it is a civilizational one, and it cannot be addressed by technical means alone.

**FM-11: Algorithmic concentration despite hardware distribution (Outer Optimizer Capture)**
*Added in v0.2 following Douillard et al. (2026).*

Decoupled DiLoCo demonstrates that frontier model training can now be physically distributed across geographically separated nodes at internet-scale bandwidth, with near-parity ML performance and dramatically improved resilience. This is architecturally aligned with DHITL's Layer 1 and Layer 5 requirements, and constitutes strong empirical support for the claim that democratic distribution of training compute is technically feasible.

However, the DiLoCo architecture introduces a specific control point that DHITL v0.1 did not address: the **outer optimizer**. In Decoupled DiLoCo, each compute island performs local gradient steps independently, but a central outer optimizer periodically aggregates gradient updates from all islands and applies the global parameter update. The outer optimizer determines:

- The aggregation function (which islands' gradients are included, with what weighting)
- The global learning rate schedule
- Which parameter updates are applied and when

Whoever controls the outer optimizer effectively controls what the model learns — regardless of where the compute sits. A training run across 60 democratically governed Mediterranean solar nodes where a single private actor controls the outer optimizer is not a democratically governed training run. It is a training run with democratically owned hardware and privately controlled outcomes.

This failure mode is named **Outer Optimizer Capture**: *distributed compute, concentrated algorithmic control*.

**Severity**: High. It is structurally invisible to CECI (which measures hardware concentration, not control concentration) and to current compute governance frameworks, which track chip location, not gradient aggregation authority.

**Mitigation approaches** (all at varying technology-readiness levels):

| Approach | Mechanism | TRL |
|---|---|---|
| Democratic rotation | Outer optimizer operated by democratically elected and rotatable institution | Governance design — deployable now |
| Open-source mandate | DHITL Layer 5 requires open-source outer optimizer implementation for any certified training run | Policy — deployable now |
| Cryptographic audit | Gradient aggregation logs cryptographically signed by each island and auditable | Technical — TRL 6 |
| Secure multi-party computation | Outer optimizer computed without any single party seeing individual island gradients | Research — TRL 3–4 |
| Distributed outer optimization | Eliminate the central outer optimizer entirely; replace with consensus-based parameter updates | Open research — TRL 1–2 |

**Near-term requirement (v0.2 specification):** For any training run claiming DHITL certification (η_gov ≥ 0.50), the outer optimizer operator must be: (a) identified and publicly registered; (b) legally and institutionally independent of the majority of compute island operators; and (c) subject to the same democratic accountability requirements as Layer 3 governance institutions. Training runs where a single actor controls both a majority of compute islands *and* the outer optimizer are structurally uncertifiable at η_gov > 0.25.

**Open research question:** Is distributed outer optimization — eliminating the central aggregator through cryptographic or consensus-based mechanisms — achievable at frontier training scale without unacceptable performance degradation? This is the highest-priority technical open problem introduced by FM-11.

---

## 6. The Democratic Faith as a Safety Heuristic

### 6.1 An explicit normative commitment

We have argued that DHITL is not founded on a proof that democracy is the optimal governance system for AI infrastructure. It is founded on a choice — one that we make explicit rather than disguising as technical necessity.

The choice is this: **under radical uncertainty about the long-term behavior of powerful AI systems, we prefer a governance structure that distributes decision-making power as widely as possible over one that concentrates it, even if concentration would be locally more efficient.**

This preference cannot be demonstrated; it must be adopted. We call it, following the conceptual vocabulary of the conversations that generated this framework, the "democratic faith" — not a religious commitment but a Lakatosian hard core: an assumption treated as non-negotiable within the research program, not because it is proven, but because abandoning it would undermine the entire framework's safety-relevant properties.

### 6.2 Why this specific heuristic

The democratic heuristic is not arbitrary. It is chosen for a specific structural property:

**One-person-one-vote is the only known mechanism that structurally prevents the irreversible concentration of decision-making power.**

Markets concentrate power toward capital. Meritocracies concentrate power toward expertise. Technocracies concentrate power toward those who control the technical systems. All of these are vulnerable to the failure mode we most need to avoid in the context of AI: the emergence of an actor (human, institutional, or artificial) with sufficient accumulated power to render correction impossible.

The democratic heuristic does not prevent all bad outcomes. It prevents specifically the worst outcome: irreversible loss of human collective agency over the systems we build.

FM-11 (outer optimizer capture) shows that this heuristic must extend beyond hardware governance to algorithmic control governance. The principle is the same: no single actor should accumulate sufficient algorithmic control over training runs to render democratic correction impossible. The specific mechanism — distributed outer optimization or cryptographic audit — is secondary to the structural requirement.

### 6.3 The heuristic under stress

We acknowledge that the democratic heuristic is itself subject to failure modes (FM-1, FM-2, FM-3, FM-10). A democratic process can be manipulated, captured, or simply too slow to respond to rapidly evolving AI capabilities. The framework's response to this is not to abandon the heuristic but to design explicit stabilization mechanisms:

**Condition S1 (Speed)**: Democratic correction must remain faster than algorithmic drift. This requires: short mandate cycles, continuous audit, automatic sunset clauses on governance decisions affecting rapidly evolving domains, and constitutional provisions that trigger review when AI capability metrics cross predefined thresholds.

**Condition S2 (Scope)**: Democratic governance must cover the *crucial core* — those technical decisions whose consequences are irreversible or civilizationally significant. The definition of "crucial core" is itself democratically determined, not technically predetermined. This prevents technical actors from defining their own scope of accountability.

**Condition S3 (Independence)**: The humans exercising oversight must be materially independent of the actors they oversee. This is the function of Layer 2 (universal dividend): a population that is economically dependent on the decisions of compute-controlling actors cannot provide independent oversight of those actors.

---

## 7. Conditions for Stability

### 7.1 Formal stability conditions

We propose that DHITL maintains effective democratic oversight of AI systems if and only if the following conditions hold simultaneously:

**S1 (Democratic Speed)**: The rate of democratic governance adaptation exceeds the rate of consequential AI capability change in the crucial core.

Formally: let *d(t)* be the "democratic correction speed" (the rate at which Layer 3 can update governance decisions) and *a(t)* be the "algorithmic drift rate" (the rate at which AI system capabilities change in ways that affect governance). Stability requires d(t) > a(t) for all t in the crucial core domain.

**S2 (Scope Coverage)**: The democratically defined crucial core covers all AI capabilities with irreversible civilizational-scale consequences.

**S3 (Economic Independence)**: At least a majority of the population exercising Layer 3 governance is not economically dependent on actors whose interests diverge from the population's collective interest in AI safety.

**S4 (Cognitive Sovereignty)**: The cognitive augmentation tools (Layer 4) remain means and not ends — instruments that increase the quality of human judgment without displacing it.

**S5 (Physical and Algorithmic Distribution)**: No single actor controls a sufficient fraction of Layer 1 (energy) or Layer 5 (compute hardware) to unilaterally override Layer 3 decisions. *Extension (v0.2):* No single actor controls a sufficient fraction of Layer 5 (algorithmic control — outer optimizer authority for training runs in the crucial core) to unilaterally determine training outcomes. Both CECI (hardware concentration) and ACCI (algorithmic control concentration, defined in Appendix A) must remain below their respective thresholds. ACCI thresholds are set lower than CECI thresholds (0.15/0.25 vs 0.25/0.40) because outer optimizer capture is faster, less visible, and less reversible than hardware concentration at equal HHI. A system with low CECI and high ACCI is not S5-stable.

**S6 (Cryptographic Integrity)**: The technical substrate (Layer 5) maintains its integrity against known and foreseeable attacks, including post-quantum cryptographic breaks.

### 7.2 Instability signatures

The framework is approaching instability when any of the following are observed:

- Democratic decision cycles on AI governance exceed 18 months on crucial-core questions (S1 violation)
- Actors whose interests diverge from collective welfare control >30% of Layer 1 or Layer 5 hardware resources (S5-hardware violation)
- Any single actor controls the outer optimizer for >15% of global frontier training compute in the crucial core without democratic accountability (S5-algorithmic violation, ACCI warning — threshold lower than hardware equivalent due to irreversibility of weight encoding)
- The CXU market shows η_gov → 0 for the majority of compute in a given jurisdiction (indicating governance collapse)
- Digital twin recommendation acceptance rates exceed 95% without evidence of active deliberation (S4 violation)
- Any single actor accumulates >20% of global Compute Exergy capacity (S5 warning threshold)

---

## 8. Positioning the Contribution

### 8.1 Relative to Constitutional AI

Constitutional AI (Bai et al., 2022) embeds normative constraints into model training. DHITL is orthogonal: it does not specify what constraints should be embedded, but rather who should have the legitimate authority to specify them. Constitutional AI without DHITL is constitutional governance without constitutional democracy — a constitution written by the king.

### 8.2 Relative to Cooperative AI

Cooperative AI research (Dafoe, 2020; Dafoe et al., 2021) focuses on AI systems that facilitate human cooperation. DHITL uses cooperative infrastructure as a precondition for democratic governance, rather than relying on AI systems to generate cooperation spontaneously. The direction is reversed: in Cooperative AI, AI enables cooperation; in DHITL, cooperation (democratic governance of infrastructure) enables safe AI.

### 8.3 Relative to AI Governance (EU AI Act, SB53)

Existing AI governance frameworks measure and regulate AI systems through disclosure, impact assessment, and incident reporting. DHITL complements these frameworks by providing the political theory they lack: a specification of whose oversight is legitimate and through what governance mechanism. SB53 and the EU AI Act tell frontier AI developers what to disclose; DHITL specifies to whom they are accountable and through what democratic process.

### 8.4 Relative to Compute Governance

Compute governance literature (Sastry et al., 2024) treats compute as a chokepoint to be controlled through state-level export restrictions and reporting obligations. DHITL treats compute as an infrastructure to be governed democratically, not merely controlled administratively. The difference is normative: export controls are state sovereignty instruments; DHITL is a democratic accountability framework.

Decoupled DiLoCo (Douillard et al., 2026) provides significant new empirical support for the DHITL position on one point and introduces a significant new challenge on another. The support: DiLoCo demonstrates that hardware concentration at the frontier training level is a governance choice, not a physical necessity — which is exactly what DHITL requires to be true for its prescriptions to be actionable. The challenge: DiLoCo reveals that hardware distribution is necessary but not sufficient for democratic control of training outcomes, because algorithmic control (outer optimizer authority) can be concentrated independently of hardware. Existing compute governance frameworks — focused on chip location and count — do not address this. DHITL v0.2 does, through FM-11 and the ACCI metric.

### 8.5 The novel contribution

DHITL's specific contribution is the conjunction of three elements, each individually present in prior work but not previously combined:

1. The extension of "human in the loop" from a technical concept to a constitutional one, requiring democratic legitimacy as a condition of safety relevance.
2. The five-layer infrastructure model as a necessary precondition for democratic HITL, with explicit formal stability conditions — now extended to cover algorithmic control as well as hardware distribution.
3. Compute Exergy (Xc) as an economically tractable unit for democratic oversight, with governance certification levels that price the FM-11 risk through the η_gov factor for distributed training runs.

---

## 9. Conclusion

AI safety is not primarily a problem of model alignment. It is a problem of infrastructure governance. A perfectly aligned model controlled by an unaccountable actor is not safe; an imperfectly aligned model governed by a robust democratic process that can correct, constrain, or shut it down is safer than the alternative.

The DHITL framework makes this claim precise. It specifies the five infrastructure layers required for democratic governance of AI systems, the economic unit (Compute Exergy) that makes this governance tractable, the formal stability conditions under which democratic correction remains effective, and eleven structural failure modes that must be explicitly managed.

The eleventh failure mode — outer optimizer capture, introduced by the Decoupled DiLoCo result of April 2026 — is a reminder that the governance challenge evolves with the technology. When training moves from co-located pods to geographically distributed islands, the governance perimeter must move with it. Hardware distribution without algorithmic distribution governance is not safety; it is the appearance of safety.

The framework rests on a normative commitment that we make explicit: the democratic faith — the choice to prefer distributed decision-making power over concentrated efficiency, under radical uncertainty about the long-term behavior of powerful AI systems. This is not a proof. It is a bet. We believe it is the right bet, for a specific structural reason: it is the only known mechanism that prevents the irreversible concentration of power that would make all other safety work moot.

The infrastructure exists, or can be built. The Mediterranean basin — with its solar resources, its geographic distribution across multiple jurisdictions, and its history of federative political experiments — offers a concrete testbed for the physical and economic layers of DHITL. The Compute Exergy framework provides the economic unit. The political architecture remains to be constructed, one democratic institution at a time.

The sun does not belong to anyone. The compute it powers should not either. And the outer optimizer that determines what that compute learns must answer to the same democratic authority as everything else in the chain.

---

## References

Anderljung, M., Barnhart, J., Korinek, A., et al. (2023). Frontier AI regulation: Managing emerging risks to public safety. *arXiv preprint* arXiv:2307.03718.

Bai, Y., Jones, A., Ndousse, K., et al. (2022). Constitutional AI: Harmlessness from AI feedback. *arXiv preprint* arXiv:2212.08073.

Bowman, S., Hyun, J., Perez, E., et al. (2022). Measuring progress on scalable oversight for large language models. *arXiv preprint* arXiv:2211.03540.

California Legislature. (2025). Senate Bill 53 — Transparency in Frontier Artificial Intelligence Act. Signed September 29, 2025.

Dafoe, A. (2020). AI governance: A research agenda. Future of Humanity Institute, University of Oxford.

Dafoe, A., Hughes, E., Bachrach, Y., et al. (2021). Open problems in cooperative AI. *arXiv preprint* arXiv:2012.08630.

Douillard, A., Rush, K., Donchev, Y., Charles, Z., Dubey, A., Woodworth, B., Gog, I., Dean, J., Fallen, N., & Garrett, Z. (2026). Decoupled DiLoCo: A new frontier for resilient, distributed AI training. Google DeepMind Technical Report, arXiv:2604.21428. https://deepmind.google/blog/decoupled-diloco/

European Parliament and Council. (2024). Regulation (EU) 2024/1689 (EU AI Act). OJ L, 12 July 2024.

Heim, L., Koessler, L., Soder, L., et al. (2024). Training compute thresholds: Features and functions in AI governance. *arXiv preprint* arXiv:2405.10799.

Irving, G., & Askell, A. (2019). AI safety needs social scientists. *Distill*. https://distill.pub/2019/safety-needs-social-scientists/

Mariani, J. H. R. (2026). Infrastructure is all you need: A three-layer architecture for sovereign AI governance. Companion working paper, Institut Mariani R&D. `github.com/JeanHuguesRobert/marenostrum/blob/main/infrastructure_is_all_you_need.md`

New York Legislature. (2025). Senate Bill S6953B — Responsible AI Safety and Education Act (RAISE Act). Signed 2025.

Robert, J. H. N. (2026). Cogentia (KYS) — Know Your Self: Personal AI psychometric MVP. GitHub repository. `github.com/JeanHuguesRobert/cogentia`. Regulated by PrivAI.

Robert, J. H. N., & Valdes, G. (2026). Constellia: A fractal architecture for energy, food, and digital sovereignty in island territories. *Proceedings of ICOME'26* (submitted). Université de Corse Pasquale Paoli, Corte.

Sastry, G., Heim, L., Belfield, H., et al. (2024). Computing power and the governance of artificial intelligence. *arXiv preprint* arXiv:2402.08797.

---

## Appendix A: Formal Definitions — CECI and ACCI

### A.1 Compute Exergy Concentration Index (CECI)

Let Ω be the set of all AI compute operations in a given time period T and jurisdiction J.

For any element ω ∈ Ω:

```
Xc(ω) = E(ω) × η_hw(ω) × η_sys(ω) × η_sla(ω) × η_gov(ω)
```

Total Compute Exergy of jurisdiction J in period T:

```
XcJ,T = ∫_Ω Xc(ω) dω
```

**Compute Exergy Concentration Index (CECI)** for period T:

```
CECI_T = Σ_i (XcJ,T,i / XcJ,T)²
```

where XcJ,T,i is the Compute Exergy attributable to hardware actor i.

**Safety thresholds:** CECI_T > 0.25 is a warning threshold (S5-hardware violation warning). CECI_T > 0.40 constitutes a structural instability condition requiring emergency governance response.

### A.2 Algorithmic Control Concentration Index (ACCI)

*Added in v0.2 to address FM-11.*

Let Φ be the set of all frontier training runs (defined as training runs crossing the crucial-core threshold democratically determined under S2) in a given time period T and jurisdiction J.

For any training run φ ∈ Φ, define:

```
W(φ, i) = fraction of effective gradient aggregation authority
           held by actor i over training run φ
```

where "effective gradient aggregation authority" encompasses: control of the outer optimizer implementation; authority to set the outer learning rate schedule; authority to weight or exclude individual island gradients; and authority to determine when and whether global parameter updates are applied.

**Algorithmic Control Concentration Index (ACCI)** for period T:

```
ACCI_T = Σ_φ [Xc(φ) × Σ_i W(φ,i)²] / Σ_φ Xc(φ)
```

This is a compute-weighted average of per-run HHI over algorithmic control, where the weighting is by Compute Exergy of the training run.

**Safety thresholds:** ACCI_T > 0.15 is an S5-algorithmic violation warning. ACCI_T > 0.25 constitutes a structural instability condition requiring emergency governance response.

These thresholds are deliberately set lower than the corresponding CECI thresholds (0.25/0.40) for three compounding reasons:

*Invisibility:* Hardware concentration (CECI) is externally observable from datacenter locations, chip counts, and energy consumption. Outer optimizer control (ACCI) is invisible without active declaration by the training run operator — it cannot be audited from the outside without access to gradient aggregation logs.

*Speed:* Hardware concentration changes on the timescale of capital investment (months to years), allowing democratic governance to respond. Outer optimizer control can change at the timescale of a training run restart (hours), potentially outpacing governance cycles (S1 violation risk).

*Irreversibility:* Redistributing hardware after a CECI violation is costly but achievable. Redistributing the *model weights* that a captured outer optimizer has already shaped is not achievable — the trained values persist after the hardware is redistributed. This asymmetry in reversibility justifies asymmetry in thresholds: the governance intervention must arrive earlier because the harm arrives later and cannot be undone.

**Measurement:** ACCI requires attribution of outer optimizer control to specific legal entities — a new reporting requirement not covered by existing compute governance frameworks. DHITL v0.2 proposes that all training runs above the crucial-core threshold must register their outer optimizer operator with the democratic governance authority as a condition of CXU certification at η_gov ≥ 0.50.

**Relationship to CECI:** CECI and ACCI measure orthogonal dimensions of the same governance risk. A jurisdiction can have:
- Low CECI, Low ACCI: distributed hardware, distributed control — target state
- Low CECI, High ACCI: distributed hardware, concentrated control — FM-11 risk zone
- High CECI, Low ACCI: concentrated hardware, distributed control — FM-9/FM-5 risk zone
- High CECI, High ACCI: concentrated hardware, concentrated control — Dataist regime

S5 stability requires CECI < 0.25 **and** ACCI < 0.15. The asymmetry is intentional: the ACCI warning fires earlier because algorithmic concentration is faster, less visible, and less reversible than hardware concentration at equal HHI.

---

## Appendix B: The Cogentia Framework (Prior Work)

The conceptual architecture of Layer 4 in DHITL builds on the **Cogentia** framework, an independent prior work whose conceptual priority is claimed and timestamped by Jean Hugues Noël Robert, baron Mariani, and whose development is supervised by the non-profit **PrivAI**. The reference implementation is publicly available at `github.com/JeanHuguesRobert/cogentia`.

We summarize the Cogentia framework's key concepts as they bear on the DHITL architecture. The framework's central claim — which directly motivates Layer 4 of DHITL — is the following: AI systems already construct persistent structural representations of individuals; the question is not whether this modeling occurs, but whether it remains opaque and extractive, or becomes structured, measurable, privacy-preserving, and governable. The philosophical grounding draws on Spinoza's *natura naturans* (enduring structural expression), Buffon's thesis that style expresses intrinsic structure, and Wolfram's computational irreducibility as a property of complex systems.

**The three-level distinction**:

- **Cogentia**: the persistent structural signature of an entity as inferred through repeated AI-mediated interaction, capturing stable cognitive, behavioral, and stylistic tendencies. It is not biography, demographic metadata, or episodic memory — it is the persistent organizational structure of cognitive and behavioral expression inferred from interaction. It is a modeling framework, not a metaphysical claim of identity essence.
- **Cogentiscope**: the instrument of measurement — the person's own AI agent, which has learned their patterns through interaction.
- **Cogentigram**: a structured computational representation of the Cogentia at a given time, produced by the Cogentiscope — a JSON object scoring 73 psychocognitive indicators on a percentile scale (0–100, referenced against the general adult population).

**The 73 indicators** are organized in six categories: Cognitive Architecture (20), Social Interface (12), Semiotics & Language (8), Axiology & Arbitrage (7), Flux Dynamics (11), and Cogentia+ (8, including curiosity, creativity, risk tolerance). Derived scores (ICV, IRF, IVT, E-S Gap) are computed as WAIS-analogous aggregates.

**The anti-reification invariant**: The Cogentigram is not the Cogentia. The map is not the territory. An AI system that treats its representation of a person as equivalent to the person will systematically substitute its model of preferences for the person's actual preferences — a form of cognitive capture that directly violates the Layer 4 sovereignty condition of DHITL.

**The PrivAI regulatory layer**: The Cogentia framework is governed by a dedicated non-profit (PrivAI) responsible for ethical standards, data minimization, GDPR compliance (explicit exclusion of Article 9 sensitive categories from scoring), and quality certification.

**Operational constraints**:

- A digital twin may generate recommendations; it may not vote, hold a mandate, or act as a legal agent for its principal.
- Scores are presented with explicit confidence intervals and indicator-level justifications.
- The instrument is revocable by its principal at any time, without penalty.
- All scoring evidence is sanitized server-side before storage.

*Reference*: Robert, J. H. N. (2026). Cogentia (KYS) — Personal AI psychometric MVP. `github.com/JeanHuguesRobert/cogentia`. Regulated by PrivAI.

---

*"The sun does not belong to anyone. The compute it powers should not either. And the outer optimizer that determines what that compute learns must answer to the same democratic authority as everything else in the chain."*

*Working paper v0.2, Institut Mariani, Corte, Corsica — April 2026*
*Contact: jhr@baronsmariani.org*
*Published in the open: github.com/JeanHuguesRobert/marenostrum — CC BY-SA 4.0*

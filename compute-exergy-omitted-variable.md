# Compute Exergy as an Omitted Variable in AI Governance

## Extending Harari's Nexus Hypothesis Through Infrastructure Sovereignty

**Jean Hugues Noël Robert, baron Mariani**
Institut Mariani / C.O.R.S.I.C.A.
1 cours Paoli, F-20250 Corte, Corsica, France
jhr@baronsmariani.org

MareNostrum Working Paper Series
April 2026

---

## Working Status Note

This is a discussion draft intended for hostile review before publication in the GitHub repository `JeanHuguesRobert/marenostrum`. Published under CC BY-SA 4.0. Not for citation without attribution.

**Positioning discipline:** conceptual paper / research program proposal. Not an empirical proof claim.

**Novelty discipline:** this paper does **not** claim to originate compute governance or compute sovereignty as concepts. Those are established. It proposes a narrower contribution: engaging Harari's information-power framework as a specific interlocutor, and introducing exergy-grounded infrastructure as an omitted substrate variable within that framework.

**Companion papers** (all in `github.com/JeanHuguesRobert/marenostrum`):

| Paper | Primary question | Primary audience |
|-------|-----------------|-----------------|
| Robert & Valdes (2026) — *Constellia* | *What does it look like?* Physical + economic architecture, verified field data | Engineers, energy economists, policymakers |
| Robert (2026a) — *Infrastructure Is All You Need* | *What is the safety architecture?* Three-layer physical model, opacity elimination | AI safety researchers |
| Robert (2026b) — *DHITL* | *How do we govern it?* Five-layer model, Xc formula, CXU, CECI, failure modes | AI governance scholars, regulators |
| **This paper** | *Why does it matter politically?* Harari engagement, K/(T·G) conjecture, Dataism as phase regime | Political theorists, Harari readers, governance generalists |

The four papers form a pyramid converging on a single conceptual pivot: **compute exergy as a political substrate**. Constellia establishes what that substrate looks like in practice; IIAYN establishes the structural safety properties it must have; DHITL formalises the governance mechanisms; this paper explains why that substrate matters for theories of information power and democratic institutions.

---

## Abstract

Recent work by Yuval Harari — especially *Homo Deus* and *Nexus* — argues that political authority is increasingly mediated by information networks shaped by algorithmic systems, a tendency Harari calls Dataism in its strong form. This paper accepts that diagnosis but argues it remains causally incomplete unless the material and institutional substrate of computation is explicitly modelled.

We propose a structural extension in which **compute exergy** — the useful, quality-adjusted, governance-certified fraction of raw computational energy — becomes part of the relevant unit of political analysis. Information power, on this view, is not epiphenomenal with respect to data structures alone; it is doubly epiphenomenal — dependent on compute, which is in turn dependent on energy and its governance.

A minimal five-variable state model is introduced in which institutional sovereignty depends jointly on model capability (M), compute concentration (K), traceability (T), governance coupling (G), and exergy sovereignty (E). The central conjecture is that the ratio K/(T·G) — concentration relative to accountability — is a stronger predictor of algorithmic authority than capability growth alone. A possible threshold above which this ratio drives nonlinear institutional erosion is identified as a research priority.

The Mediterranean case grounds the argument in verified data. In Corsica, 30,000 ha of agrivoltaic deployment yields 10.8 GWp of installed capacity and a surplus of 13.8 TWh/year convertible into sovereign AI compute at a value multiplier of ×4 to ×31 over raw electricity — with the multiplier determined entirely by the governance properties of the compute, not by its technical specifications. This value gradient is the empirical expression of E in the state model: governance quality is a productive input, not merely a regulatory constraint.

This framing conditionalises Harari's stronger Dataist predictions: Dataism is not civilisational destiny, but a contingent phase regime that specific governance architectures can prevent.

**Keywords:** AI governance, compute governance, exergy, Harari, Nexus, Dataism, infrastructure sovereignty, algorithmic authority, compute concentration, democratic infrastructure, Mediterranean, agrivoltaics.

---

## 1. Introduction

Debates on advanced AI systems tend to bifurcate between two levels of analysis:

- **Model-level safety:** alignment techniques, interpretability research, constitutional AI, capability evaluations.
- **Institutional regulation:** disclosure requirements, incident reporting, antitrust, liability regimes.

Both are necessary. Both have generated real progress. But this paper argues they share a structural omission: neither addresses the **material and institutional substrate** of computation — who owns it, who governs it, under what constraints its outputs can be traced, audited, and disputed.

This omission may not be analytically neutral. If the substrate is causally prior to both model behaviour and institutional outcomes, then interventions that ignore it are operating on symptoms rather than causes.

The research question this paper poses is:

> *Under what infrastructural conditions does increasing computational capability translate into socially authoritative algorithmic systems?*

This question is partly Harari's. In *Nexus* (2024) and *Homo Deus* (2017), Harari argues that information-processing networks have historically defined the structure of power, and that AI systems represent a qualitative shift in the concentration and speed of that processing. We accept this diagnosis. We argue it requires one additional causal step: information networks are themselves a function of compute infrastructure, which is in turn a function of energy systems and their governance. Harari's "information architecture" does not float free of physical substrate.

The paper proceeds as follows. Section 2 formalises the causal extension. Section 3 defines key terms and maps them onto the companion papers. Section 4 introduces the minimal state model. Section 5 interprets the Dataist regime as a phase phenomenon. Section 6 positions the paper relative to the compute governance literature. Section 7 states testable propositions. Section 8 develops the reinterpretation of trust. Section 9 grounds the argument in the Mediterranean case study. Section 10 acknowledges limitations. Section 11 concludes.

---

## 2. From Information Networks to Substrate Dependence

### 2.1 Harari's Framework Stylised

Harari's core causal claim, across both books, can be written:

$$\text{Power} \sim \text{Information Architecture}$$

In *Nexus*, this relationship is instantiated historically: Sumerian grain ledgers, the printing press, the telegraph, and large language models all reorganise authority by reorganising information flows. The "Dataist" projection — that algorithmic systems may come to function as autonomous loci of institutional authority, displacing democratic deliberation — is Harari's most contested claim.

We accept the stylised causal framework. We argue it is causally underspecified.

### 2.2 The Proposed Extension

Information architecture is not substrate-neutral. Every information-processing system requires a physical instantiation: processors, power supply, cooling, interconnect, governance of access. We propose:

$$\text{Information Architecture} = f(\text{Compute},\; \text{Energy},\; \text{Institutions})$$

And further: "Compute" is not a homogeneous quantity. Two systems with identical raw computational throughput may differ drastically in their governance properties — one traceable, democratically accountable, auditable; the other concentrated and opaque. Those governance properties affect whether and how computational outputs translate into social authority.

The empirical signature of this claim is directly observable in the data that Constellia (Robert & Valdes, 2026) establishes for the Mediterranean case: identical solar energy, converted to compute, commands prices of €90/MWh (raw electricity), €350/MWh (batch AI, uncertified), €1,100/MWh (premium EU, 99.9% SLA), or €2,800/MWh (sovereign-critical, fully certified). The physical input is the same. The governance properties differ. The market prices the difference at a factor of ×31.

This is not a marginal correction to Harari's framework. It is a claim that the market already prices what political theory has not yet formalised: governance quality is a productive input, not merely a constraint.

**Working hypothesis:**

> *Information power may be partially epiphenomenal with respect to deeper infrastructural variables. Specifically: algorithmic authority may track not raw computational capability but the ratio of compute concentration to governance accountability.*

This is not a theorem. It is a structural conjecture developed in the sections that follow.

### 2.3 Why This Matters for Harari's Argument

If the substrate hypothesis is correct, it qualifies Harari's predictions in a consequential way. The Dataism-as-destiny reading implies that increasing AI capability is sufficient to drive increasing algorithmic authority — the trend is a function of M alone. But if algorithmic authority depends jointly on capability *and* infrastructure governance, then governance interventions at the substrate level can decouple the two. Dataism is not a law of historical motion; it is a contingent regime that requires specific governance failures to materialise, and can be prevented by specific governance successes.

This is not a refutation of Harari. It is a conditional: his framework correctly identifies the direction of the trend under *current* conditions. Current conditions are not fixed.

---

## 3. Definitions and Mapping to the Corpus

### 3.1 Compute Sovereignty (Definition 1)

*Compute sovereignty* denotes the capacity of a polity to impose enforceable structural constraints on computation affecting collective outcomes within its jurisdiction.

This concerns *governance capacity*, not mere hardware possession. A polity can own compute infrastructure without compute sovereignty (if effective control is held by private actors under weak governance), and can exercise compute sovereignty without owning hardware (if effective regulation reaches the substrate).

### 3.2 Exergy Sovereignty (Definition 2)

*Exergy sovereignty* denotes autonomous control over the energy inputs enabling computation, sufficient to define the governance terms under which that compute operates.

Unlike generic "energy sovereignty," the focus is energy as *conditioned computational capacity*. A distributed solar endowment provides raw energy. Exergy sovereignty requires additionally the governance capacity to determine who may use the resulting compute, under what accountability regime, and at what price tier.

**Connection to corpus.** The companion paper DHITL (Robert, 2026b) formalises Compute Exergy (Xc) as:

$$X_c = E \times \eta_{hw} \times \eta_{sys} \times \eta_{sla} \times \eta_{gov}$$

where $\eta_{gov} \in [0,1]$ is a governance quality factor capturing traceability and democratic accountability, with the nullity condition: $X_c = 0$ if $\eta_{gov} = 0$. Compute without democratic accountability produces zero governance-relevant exergy, regardless of its raw quantity.

Constellia (Robert & Valdes, 2026) provides the empirical anchor: the ×4-to-×31 value multiplier between raw electricity and sovereign-critical compute is the market expression of $\eta_{gov}$ across the four certification tiers defined in DHITL.

### 3.3 Algorithmic Authority (Definition 3)

*Algorithmic authority* denotes the degree to which computational outputs function as effective decision premises inside institutions — outputs that determine decisions without being themselves subject to meaningful democratic scrutiny.

Algorithmic authority is distinct from:
- *Algorithmic assistance:* outputs used as one input among many, under human judgment.
- *Algorithmic substitution:* outputs replacing human decision under explicit democratic mandate.

The dangerous case is authority that is neither fully substitutional nor fully advisory — operating in the shadow of formal human decision-making while functionally determining outcomes. This is Harari's core concern in *Nexus*, and the concept targeted by DHITL's Layer 4 (the Cogentia framework and the anti-reification invariant: a digital twin cannot vote, cannot hold a mandate, cannot function as a legal agent).

---

## 4. A Minimal Structural Model

### 4.1 State Variables

Let the state of an AI governance system be characterised by the vector:

$$S = (M,\; K,\; T,\; G,\; E)$$

where:

- **M** — *model capability:* a composite measure of task performance across relevant domains. Growing monotonically with research investment under current trajectories.

- **K** — *compute concentration:* a Herfindahl-Hirschman Index over the distribution of compute capacity. Formalised in DHITL as the Compute Exergy Concentration Index: $\text{CECI} = \sum_i (X_{c,i}/X_{c,\text{total}})^2$.

- **T** — *traceability:* the degree to which compute operations are attributable to specific actors, decisions, and energy sources. $T \in [0,1]$. Corresponds to Layer 5 of DHITL ("open core, traceable decisions") and Layer 3 of IIAYN ("auditable inference registry"). The limiting case $T = 0$ is what IIAYN calls "opacity" — identified as the primary vector of AI risk.

- **G** — *governance coupling:* the degree to which compute operations are subject to enforceable democratic accountability. $G \in [0,1]$. Corresponds to Layer 3 of DHITL (democratic governance, 1p1v) and maps onto $\eta_{gov}$ in the Xc formula. The four discrete certification levels in DHITL ($\eta_{gov} \in \{0, 0.25, 0.50, 0.75, 1.00\}$) are candidate operationalisations of G.

- **E** — *exergy sovereignty:* the degree to which energy inputs enabling computation are governed as a democratic commons. $E \in [0,1]$. Corresponds to Layer 1 of both DHITL and IIAYN (physical/solar exergy) and to the Galassia sovereign fund model in Constellia — the institutional mechanism preventing external capture of the energy substrate.

Institutional sovereignty $I$ — the capacity of a democratic polity to set binding terms on AI systems affecting it — is a function of this state:

$$I = f(M,\; K,\; T,\; G,\; E)$$

The claim of this paper is that this function has a specific structural form, and that the dominant term is not M.

### 4.2 Conjecture 1 — The Concentration-Accountability Ratio

**Conjecture 1:** Institutional erosion is driven more strongly by the ratio

$$\frac{K}{T \cdot G}$$

than by growth in M alone.

*Motivation:* A highly capable AI system operating under high traceability and strong democratic governance does not erode institutional sovereignty — it augments it. The dangerous case is a moderately capable system under high concentration and low accountability. The ratio K/(T·G) names this danger precisely: concentration in the numerator, the two accountability variables in the denominator.

*Connection to DHITL:* The companion paper identifies warning thresholds: CECI > 0.25 (concentration warning for K); $\eta_{gov} \rightarrow 0$ for the majority of compute in a jurisdiction (governance collapse, equivalent to T·G → 0). The ratio K/(T·G) provides a single scalar combining both signals.

*Operationalisation:* K is approximable from cloud provider market share or GPU cluster concentration indices (Sevilla et al., 2022; Epoch AI, 2024). T is approximable from audit registry coverage. G maps onto third-party certification coverage. The ratio K/(T·G) is in principle computable for major jurisdictions from existing data.

*Status:* Conjecture, not result.

### 4.3 Conjecture 2 — Phase Threshold

**Conjecture 2:** There exists a threshold $K^*$ above which increases in M generate nonlinear, possibly discontinuous, increases in algorithmic authority — independently of T and G.

*Motivation:* If K exceeds $K^*$, the actors controlling compute may acquire the capacity to shape the terms of governance itself — not merely to operate within governance constraints but to define them. At this point T and G become endogenous to K, and the stabilising denominator in Conjecture 1 collapses.

This is structurally analogous to antitrust phase transitions: below a concentration threshold, competitive dynamics constrain firm behaviour; above it, the dominant firm shapes the regulatory environment that is supposed to constrain it.

*Candidate value:* DHITL identifies a structural instability condition at CECI > 0.40, from Herfindahl-Hirschman antitrust thresholds. This is a candidate for $K^*$.

*Status:* Speculative. Stated explicitly rather than implied.

---

## 5. Dataism Reinterpreted as a Phase Regime

### 5.1 The Dataist Regime Defined

Define the Dataist regime as the set of system states:

$$\mathcal{D} = \{ S \mid K \text{ high},\; T \text{ low},\; G \text{ weak},\; E \text{ captured} \}$$

In this regime, algorithmic authority approaches a self-sustaining attractor: systems that generate authority generate resources that reproduce the conditions of their own authority. Harari's *Nexus* describes the trajectory toward $\mathcal{D}$ and warns of its consequences.

We interpret $\mathcal{D}$ not as a historical law but as a contingent phase in a multi-attractor system. Whether the trajectory toward $\mathcal{D}$ is attracting depends on the current values of K, T, G, and E — which are governed, and therefore governable.

### 5.2 Alternative Regimes

**Democratic Compute Regime** — High M, low K, high T, high G, high E. Capability growth without concentration, under full accountability. Institutional sovereignty is maintained or enhanced. This is the regime targeted by the MareNostrum framework. The physical instantiation is the Stella network in Constellia (Robert & Valdes, 2026): 60 independent energy-compute nodes across a Mediterranean territory, each autonomous, with ARPANET-inspired resilience — destruction of 30% of nodes reduces capacity by 30%, without cascade failure (Baran, 1964). No single actor controls a decisive fraction of the substrate. This is not a schematic; it is an engineered architecture with verified physical parameters.

**Captured-but-Traceable Regime** — High M, high K, high T, low G. Compute concentrated, but logging requirements and some audit obligations exist. Formally transparent but not democratically accountable. Approximately the regime produced by some current national AI strategies. Whether this regime is stable or unstable under increasing M is the most important near-term empirical question for the framework.

**Exergy-Sovereign Cooperative Regime** — Moderate M, low-to-medium K, high T, high G, high E. Lower capability growth, stronger governance. Targeted by the Corsica2038 and Cuba2038 cases in Constellia. The trade-off between M and (T, G, E) is the central political economy question: how much capability growth do democratic polities sacrifice in exchange for governance integrity?

### 5.3 Conditionalising Harari

The phase-regime reading has a concrete implication. *Nexus* warns that we are in or approaching $\mathcal{D}$. This paper accepts the warning and adds a conditional:

> *The Dataist attractor is only inevitable given current values of (K, T, G, E). Governing those variables directly — rather than attempting to constrain capability growth M — is the more effective and more tractable intervention point.*

This is not an optimistic claim. The governance interventions required are substantial. It is a redirection of analytical attention toward the variables that are both causally prior and more amenable to democratic governance than capability growth itself.

---

## 6. Relation to the Compute Governance Literature

### 6.1 What the Literature Has Established

This paper does not originate the claim that compute matters for AI governance. That claim is established (Sastry et al., 2024; Heim et al., 2024; Anderljung et al., 2023; Epoch AI, 2024). The existing literature has demonstrated: compute as the primary chokepoint for frontier AI capability; chip export controls as a governance lever; cloud-provider monitoring; training compute thresholds as regulatory triggers (currently at $10^{26}$ FLOP); hardware-level compliance concepts.

We build on this work.

### 6.2 The Causal Frame Difference

Existing compute governance literature treats compute as: a controllable input, a regulatory chokepoint, a strategic bottleneck.

This paper, with its companions, treats compute as: a political substrate — the material precondition for information power; an infrastructural condition of information power — in Harari's terms, what determines which information architectures are possible; a potentially exergy-grounded democratic commons — if energy inputs are governed democratically, the compute they enable is subject to principled democratic governance with a physically verifiable anchor.

The difference determines the type of intervention implied. Export controls and reporting requirements address who *has* compute. The substrate framing addresses under what governance terms compute is *used*, positioning democratic accountability rather than state control as the relevant variable.

### 6.3 Differentiation from Companion Papers

- DHITL (Robert, 2026b) answers *"how do we govern it?"* — five-layer model, Xc, CXU, CECI, failure modes, stability conditions.
- IIAYN (Robert, 2026a) answers *"what architecture?"* — three-layer model, opacity elimination, material traceability.
- Constellia (Robert & Valdes, 2026) answers *"what does it look like?"* — 10.8 GWp, ×31 multiplier, Stella topology, Cuba2038.
- **This paper answers "why does it matter politically?"** Its unique contribution is connecting Harari's information-power framework to the infrastructure substrate the companion papers develop. Without this bridge, the technical architecture risks being read as engineering rather than political philosophy.

### 6.4 Narrow Novelty Statement

> *The novelty of this paper is not the claim that compute matters for AI governance. The narrower contribution is to treat compute as an exergy-dependent political substrate and to use this framing to extend theories of information power one causal layer downward — connecting the political philosophy of Harari's framework to the engineering and governance reality developed in the companion papers.*

---

## 7. Testable Propositions

The framework generates three testable propositions. All three are empirical conjectures, not results.

### Proposition P1 — Concentration Dominates Capability

**P1:** Compute concentration (K) correlates more strongly with institutional asymmetry than model capability (M) alone.

*Operationalisation:*
- K: cloud market Herfindahl-Hirschman Index or CECI as defined in DHITL.
- M: standardised capability benchmarks (MMLU, BIG-Bench, LMSYS arena ratings).
- Institutional asymmetry: differential access to AI-generated decision inputs between powerful and marginal actors — large vs. small firms, central vs. peripheral governments, high-income vs. low-income polities.

*Expected finding if P1 holds:* regressions of institutional asymmetry on K alone explain more variance than regressions on M alone, controlling for GDP and connectivity.

### Proposition P2 — Traceability Reduces Authority Concentration

**P2:** Higher traceability (T) reduces effective concentration of algorithmic authority, holding K constant.

*Operationalisation:*
- T: fraction of AI operations subject to auditable registry, or binary (jurisdiction requires inference logging).
- Authority concentration: HHI over the distribution of consequential algorithmic decision outputs — judicial, medical, financial, administrative.

*Near-term testbed:* EU AI Act high-risk provider audit requirements vs. unregulated equivalents offer a natural quasi-experiment.

### Proposition P3 — Distributed Energy-Compute Exhibits Governance Resilience

**P3:** Distributed energy-compute architectures (low K, high E) exhibit higher institutional resilience under governance stress than concentrated alternatives.

*Operationalisation from Constellia:* A Galaxy architecture is technically viable when: solar resource ≥ 1,400 kWh/kWp/year; agrivoltaic-compatible land ≥ 5,000 ha; governance stability for 20-year contracts. These conditions define ~40–60 island states and autonomous regions globally, representing ~80 million people — a sufficient sample for cross-sectional analysis of P3.

*Measurement challenge:* "governance resilience" requires a time-series measure of oversight across governance stress events. No standardised instrument exists; developing one is a research priority.

---

## 8. Trust as Enforceable Infrastructure

### 8.1 Harari's Trust Framing

*Nexus* places trust at the centre of its political analysis. Harari argues that information networks generate inter-subjective realities — shared beliefs that become socially operative by virtue of being shared — and that AI systems threaten this trust not primarily because they lie, but because the structural conditions for disputing their outputs are absent: no one knows who ran what computation, on whose behalf, with what data, toward what end.

This diagnosis is precisely right. It identifies the *condition* that makes AI dangerous in Harari's framework: the absence of accountable disputation mechanisms. The question it leaves open is what the institutional equivalent of a solution looks like.

### 8.2 The Infrastructure Reframe

We propose:

> *Trust without enforceable infrastructure is normative aspiration. Infrastructure is trust made enforceable.*

Harari treats trust as a social-psychological phenomenon produced by shared information and narrative. We treat it as a *systems property* partially determined by the architecture of the information system generating the outputs being trusted.

Trust in an AI output is warranted — not just pragmatically adopted — only when the conditions of its production are such that errors can be detected, attributed, and corrected. These conditions are not cognitive (what the trustor believes about the trustee); they are structural (what the infrastructure makes possible). This parallels the transition in economic theory from "trust" as psychology to "credible commitment" as institutional mechanism. The credibility of a commitment is determined not by the sincerity of the committer but by the structural cost of deviation. Analogously: the trustworthiness of an AI system is determined not by the alignment of the model but by the structural conditions of accountability surrounding its deployment.

### 8.3 The Vault Analogy

Constellia (Robert & Valdes, 2026) provides the concrete economic expression of this principle:

> *Switzerland never extracted an ounce of gold. It built the vaults, the governance, and the trust infrastructure that made everyone else's gold worth more by being there. The AI token is the gold of the twenty-first century. Island territories with the right architecture — sovereign, resilient, physically certified — can become its custodians.*

This analogy is not decorative. It identifies the economic mechanism through which trust-as-infrastructure generates value. The ×31 premium between uncertified batch compute and sovereign-critical certified compute is the market price of governance quality — a trust premium, as real as Swiss settlement finality. The vault is not metaphorical: it is the infrastructure stack in which every inference is linked to an energy event, a physical location, a governance jurisdiction, and an accountability chain.

### 8.4 Operational Implication

The infrastructure-as-trust framing identifies interventions that Harari's framework does not foreground but that may be causally prior to the trust dynamics he analyses:

*The primary intervention is not to make AI systems more honest, but to make it architecturally impossible to deploy AI systems at scale without leaving an auditable trace of who is responsible for the outputs.*

This is the "opacity elimination" principle in IIAYN (Robert, 2026a): not content surveillance, but structural impossibility of unregistered, unattributable computation at scale. It does not require that AI systems be honest; it requires the infrastructure to be transparent in ways that make dishonesty visible. It shifts the policy question from "how do we align models?" to "how do we make the infrastructure such that misaligned outputs cannot propagate silently?" — a question that is upstream, and more tractable.

### 8.5 Implications for Harari's Argument

If trust is partially a systems property, the central question shifts from *"how do we maintain social trust in the face of AI?"* (Harari's framing) to *"what infrastructure produces the structural preconditions for warranted trust in AI outputs?"* This shift identifies a class of tractable governance interventions — democratic control of compute infrastructure — that Harari's framework does not foreground. The problem is not only cultural or psychological; it is architectural. Architectural problems, while difficult, are more tractable than cultural ones.

---

## 9. Mediterranean Meso-Scale Testability

### 9.1 The Empirical Framing

Unlike purely abstract governance proposals, the framework admits meso-scale empirical instantiation. We propose the Mediterranean quadrilateral — Corsica, Sardinia, Sicily, Tunisia — as a viable testbed for the propositions advanced in this paper, specifically for Proposition P3.

This claim is made cautiously. The testbed is a candidate site for controlled investigation, not a demonstration. What follows draws directly on verified field data in Constellia (Robert & Valdes, 2026).

### 9.2 The Physical Substrate — Verified Numbers

Mean horizontal irradiance in Corsica averages 1,700–1,850 kWh/m²/year (JRC PVGIS, 2023), among the highest in Europe. Vertical east-west bifacial agrivoltaic panels deployed across 21,000 ha of agrivoltaic-compatible friche yield, on PVGIS-validated parameters (CF 18.8%, system losses 10%, bifacial gain +18%):

| Parameter | Value | Source |
|-----------|-------|--------|
| Installed capacity | 10.8 GWp | PVGIS + field |
| Net annual production | 16.0 TWh/year | Calculated |
| Corsican local consumption | 2.2 TWh/year | OREGES (2023) |
| **Surplus for compute** | **13.8 TWh/year** | Net − local |
| Multiple of local consumption | 6.3× | — |
| GPU rack equivalent (40 kW, PUE 1.35) | ~230,000 racks | Calculated |

The 13.8 TWh/year surplus is not theoretical headroom — it is field-calibrated.

### 9.3 The Value Multiplier — E as Observable Variable

The conversion of surplus solar energy into AI compute at different governance tiers produces:

| Service tier | Price | Multiplier | Governance requirement |
|---|---|---|---|
| Raw electricity export | €90/MWh | ×1 | None |
| Batch AI compute, uncertified | €350/MWh | ×4 | Basic logging |
| Premium EU, SLA 99.9% | €1,100/MWh | ×12 | Annual third-party audit |
| Sovereign-critical | €2,800/MWh | ×31 | Continuous audit + SecNumCloud |

The multiplier structure is the empirical expression of E in the state model. Higher exergy sovereignty — more democratic control, more enforceable accountability — commands a higher market premium. The ×31 spread is not produced by superior hardware; it is produced by superior governance. This is the market pricing of $\eta_{gov}$, expressed in euros per megawatt-hour.

Annual gross revenue potential: €3–40 billion/year depending on tier mix. The target monthly basic income of €500/resident (Galassia sovereign fund model) is achievable at a blended average of approximately €530/MWh — a conservative mix of premium and batch tiers.

### 9.4 The Stella Network — Physical Instantiation of the Democratic Regime

Constellia introduces the Stella network: a decentralised energy-compute routing fabric of 60 independent nodes across the quadrilateral. The design is ARPANET-inspired (Baran, 1964): no node controls the others; routing is distributed; destruction of any 30% of nodes reduces capacity by 30%, without cascade failure. Each node comprises an autonomous agrivoltaic cluster, multi-layer storage (V2G fleet, STEP pumped hydro, Li-ion, e-diesel reserve), and compute capacity.

In terms of the state model:
- Stella implements **low K by construction**: no actor controls a decisive fraction of the substrate.
- Stella implements **high T** through the distributed append-only inference registry described in IIAYN.
- Stella implements **high G** through cooperative governance and the Galassia fund's anti-capture provisions (no external shareholder > 5% without parliamentary approval; board by civic lottery; disposals > €10M by local referendum).

The Stella network is not a metaphor for the democratic compute regime. It is one candidate physical instantiation of it, with verified engineering parameters.

### 9.5 Replicability — Cuba2038 and the Generalisation Conditions

The architecture generalises beyond the EU context. Cuba2038 — a second Constellia galaxy — demonstrates this: solar resource 1,900–2,100 kWh/kWp/year; pumped hydro potential in the Sierra Maestra; ~800,000 ha suitable for agrivoltaics; and a structural fossil-fuel import dependency whose disruption has repeatedly demonstrated systemic fragility. The Latin American sovereign cloud market, currently dominated by US hyperscalers, represents a significant opportunity for certified sovereign compute that no EU-based operator currently addresses.

Generalisation conditions for a viable galaxy (Robert & Valdes, 2026): solar resource ≥ 1,400 kWh/kWp/year; agrivoltaic-compatible land ≥ 5,000 ha; governance stability for 20-year contracts. These define ~40–60 island states and autonomous regions globally — a sample large enough for cross-sectional analysis of P3.

### 9.6 Historical Precedent — CECA 1951

The political logic of the testbed has a direct historical precedent: the European Coal and Steel Community (1951). The CECA pooled two strategic industrial substrates — coal and steel — across six national jurisdictions, making their weaponisation by any single member structurally impossible through shared governance. The MareNostrum analogy: solar exergy and compute are the coal and steel of the twenty-first century. Their pooling under democratic governance achieves the same structural result — monopolisation is made architecturally impossible.

The Charte du Soleil Méditerranéen (Robert, 2026a, 13 articles and Serment de Corte) is the constitutional document proposing this pooling arrangement.

---

## 10. Limitations

Explicit open liabilities:

1. **Variables are under-operationalised.** S = (M, K, T, G, E) identifies theoretically meaningful quantities; measurement methodologies are not fully specified. Operationalisation choices will affect empirical findings.

2. **Phase transition claims are speculative.** Conjecture 2 ($K^*$) extrapolates from the antitrust analogy. It is a hypothesis, not a result.

3. **Exergy sovereignty is not standardised.** The Xc formula in DHITL is a theoretical specification; empirical measurement of $\eta_{gov}$ requires independent validation.

4. **G is multi-dimensional.** The single variable G collapses revocability of mandates, audit independence, scope of democratic authority, and speed of governance response (the S1–S6 conditions in DHITL). This may obscure important interactions.

5. **No empirical validation is claimed.** Sections 7 and 9 describe how propositions could be tested; they do not present results.

6. **The Harari engagement carries a risk of parasitism.** The reviewer is invited to assess whether the extension genuinely develops Harari's framework or merely borrows its readership.

7. **The Mediterranean testbed section may weaken disciplinary coherence.** A political theory reviewer may read Section 9 as a funding pitch. An energy economics reviewer may read it as too abstract.

These liabilities are listed explicitly rather than buried in footnotes.

---

## 11. Discussion

If the substrate hypothesis is correct, a practical implication follows: current AI governance overweights downstream control variables (model alignment, output filtering, disclosure requirements) while underweighting upstream structural variables (compute concentration, traceability, governance coupling of the energy-to-compute chain).

The four-paper MareNostrum corpus proposes a specific structural intervention at the upstream level: democratic governance of compute infrastructure, grounded in physically distributed solar exergy, institutionalised through cooperative sovereign funds, expressed as a verifiable market premium in the compute pricing structure. This is not utopian. It has verified physical parameters (10.8 GWp, 13.8 TWh/year surplus), a concrete institutional precedent (CECA 1951), and a functioning economic model (the ×4-to-×31 value multiplier is a present-day market reality in certified cloud computing, not a projection).

If the substrate hypothesis is incorrect — if compute concentration and governance coupling turn out not to be causally prior to algorithmic authority — the framework still has diagnostic value: it specifies precisely where the theoretical disagreement lies. Is algorithmic authority primarily a function of M? Of information network architecture? Of compute substrate? Making these alternatives explicit is useful regardless of which proves empirically dominant.

Both outcomes advance the research program.

---

## 12. Conclusion

This paper proposes a limited but potentially consequential extension of Harari's information-power framework. The core claim:

*Algorithmic authority depends less on the growth of AI capability itself than on the institutional organisation of the compute substrate through which capability is deployed.*

If so, the variables that determine whether democratic institutions survive the AI transition are not primarily model properties but infrastructure properties: compute concentration K, traceability T, governance coupling G, and exergy sovereignty E.

This reformulates Harari's Dataism not as a historical law but as a contingent phase regime — one that requires specific governance failures to materialise and can be prevented by specific governance successes. The prevention mechanisms are architecturally specified in the companion papers and empirically grounded in the Mediterranean case.

The vault analogy from Constellia states the conclusion most precisely: Switzerland did not mine gold. It built governance infrastructure that made gold worth more by being there. The compute exergy of the Mediterranean basin is the gold. The governance architecture — democratic, distributed, traceable, antifragile — is the vault. The claim of the MareNostrum research program, taken as a whole, is that this vault can be built, and that building it is the most consequential AI safety intervention available to democratic polities in the current decade.

---

## Corpus Coherence Map

The four papers constitute a single research program operating at four levels of abstraction, each answering a different question about the same conceptual pivot:

```
PIVOT: Compute Exergy as Political Substrate

┌────────────────────────────────────────────────────────────────────┐
│  This paper (Robert 2026)                          WHY             │
│  Harari engagement · K/(T·G) conjecture                            │
│  Dataism as phase regime · Trust as infrastructure                 │
│  Political philosophy bridge to the other three                    │
├────────────────────────────────────────────────────────────────────┤
│  DHITL (Robert 2026b)                              HOW             │
│  Five-layer model (Physical/Economic/Political/Cognitive/Tech)     │
│  Xc = E·η_hw·η_sys·η_sla·η_gov · CXU · CECI                        │
│  10 failure modes · Stability conditions S1–S6                     │
├────────────────────────────────────────────────────────────────────┤
│  Infrastructure Is All You Need (Robert 2026a)     WHAT            │
│  Three-layer model (Substrate / Governance / Contracts)            │
│  Opacity elimination · Material traceability                       │
│  Charte du Soleil Méditerranéen (13 articles)                      │
├────────────────────────────────────────────────────────────────────┤
│  Constellia (Robert & Valdes 2026)                 HOW IT LOOKS    │
│  10.8 GWp · 13.8 TWh surplus · ×31 value multiplier                │
│  Stella/ARPANET topology · Cuba2038 · Galassia fund                │
│  Generalisation conditions · CAPEX €12.4B · €500/month dividend    │
└────────────────────────────────────────────────────────────────────┘

Causal flow: bottom → top (physical substrate → political authority)
Evidential flow: both directions (political argument requires physical
grounding; physical architecture requires political justification)
```

---

## Literature Relation Matrix

| Literature stream | Primary focus | This paper's extension |
|---|---|---|
| Harari / *Nexus* / *Homo Deus* | Information power and democratic erosion | Adds compute substrate as mediating layer; conditionalises Dataism |
| Compute governance (Sastry, Heim) | Compute as chokepoint, regulatory lever | Adds exergy-grounded democratic framing; moves from "who has it" to "under what governance" |
| Sovereign compute discourse | National capacity, strategic autonomy | Adds democratic (not merely national) infrastructure theory |
| Energy-AI nexus | Electricity demand of AI systems | Adds political exergy framing: governance quality as productive input |
| Commons theory (Ostrom) | Governance of shared natural resources | Extends to compute-exergy as democratic commons; CECA 1951 as precedent |
| AI safety frameworks | Model-level alignment and capability risk | Adds substrate-level antecedent conditions; upstream causal layer |
| Constellia / island sovereignty | Physical energy-compute architecture | Provides empirical anchor for E, the ×31 multiplier, and P3 testbed conditions |

---

## Figure 1 — Causal Stack

```
╔═══════════════════════════════════════════════════════════════╗
║  SOLAR ENERGY / EXERGY SOVEREIGNTY (E)                        ║
║  Distributed · Ungovernable at source · Democratic commons    ║
║  [Constellia: 10.8 GWp · 13.8 TWh/year surplus]               ║
╠═══════════════════════════════════════════════════════════════╣
║  COMPUTE INFRASTRUCTURE                                       ║
║  Concentration (K) · Traceability (T) · Governance (G)        ║
║  [DHITL: Xc, CXU, CECI · IIAYN: opacity elimination]          ║
╠═══════════════════════════════════════════════════════════════╣
║  INFORMATION NETWORKS / MODEL CAPABILITY (M)                  ║
║  Where Harari's framework operates                            ║
╠═══════════════════════════════════════════════════════════════╣
║  INSTITUTIONAL POWER / ALGORITHMIC AUTHORITY (I)              ║
║  I = f(M, K, T, G, E) · Dominant term: K/(T·G)                ║
╚═══════════════════════════════════════════════════════════════╝

↑  Democratic governance constrains all layers (DHITL Layer 3, 1p1v)
↓  Traceability and accountability flow downward (IIAYN Layer 3, audit)

Dataist regime D  : K high, T low,  G weak,   E captured → I collapses
Democratic regime : K low,  T high, G strong, E sovereign → I maintained
```

Canonical filename: `figures/infrastructure-stack.svg`

---

## Questions for External Reviewers

Stress-test requested specifically on:

1. **Is "exergy sovereignty" analytically useful or ornamental?** Does E do real work — does it differ from "energy governance capacity" in any way that matters for the political analysis?

2. **Is Conjecture 1 meaningful or vacuously schematic?** Does K/(T·G) identify a real causal mechanism, or is it a mathematical restatement of "governance matters"?

3. **Is the novelty claim sufficiently narrow and defensible?** Does the Harari extension add value beyond what the compute governance literature already provides?

4. **Does the Harari engagement read as genuine theoretical development or parasitic framing?** Does the paper earn its positioning relative to *Nexus*?

5. **Is the vault analogy (Section 8.3) a genuine contribution or rhetorical decoration?** Does it add to the political philosophy argument, or does it only serve as a memorable slogan?

6. **Does the Mediterranean testbed section (Section 9) strengthen or weaken the paper's disciplinary coherence?**

7. **Is the corpus coherence map accurate?** Do the four papers form a genuinely unified research program, or do they merely share vocabulary? Where are the internal tensions?

8. **Is the CECA 1951 analogy (Section 9.6) historically apt or misleading?** The CECA was designed to prevent Franco-German military competition through shared industrial governance. Does the compute-exergy analogy hold at the level of mechanism, or only at the level of rhetoric?

---

## References

Anderljung, M., Barnhart, J., Korinek, A., et al. (2023). Frontier AI regulation: Managing emerging risks to public safety. *arXiv preprint* arXiv:2307.03718.

Baran, P. (1964). On distributed communications networks. RAND Corporation Memorandum RM-3420-PR, Santa Monica, CA.

Dupraz, C., Marrou, H., Talbot, G., Dufour, L., Nogier, A., Ferard, Y. (2011). Combining solar photovoltaic panels and food crops for optimising land use: towards new agrivoltaic schemes. *Renewable Energy* 36(10), 2725–2732.

Epoch AI. (2024). *Trends in the dollar training cost of machine learning systems*. Epoch AI Research. https://epochai.org/

Fraunhofer ISE. (2023). *Agrivoltaics: Opportunities for Agriculture and the Energy Transition*. Fraunhofer Institute for Solar Energy Systems, Freiburg.

Harari, Y. N. (2017). *Homo Deus: A Brief History of Tomorrow*. Harper.

Harari, Y. N. (2024). *Nexus: A Brief History of Information Networks from the Stone Age to AI*. Random House.

Heim, L., Koessler, L., Soder, L., et al. (2024). Training compute thresholds: Features and functions in AI governance. *arXiv preprint* arXiv:2405.10799.

JRC PVGIS. (2023). *Photovoltaic Geographical Information System*. European Commission Joint Research Centre. https://re.jrc.ec.europa.eu/pvg_tools/

Marrou, H., Guilioni, L., Dufour, L., Dupraz, C., Wery, J. (2013). Microclimate under agrivoltaic systems: is crop growth rate affected in the partial shade of solar panels? *Agricultural and Forest Meteorology* 177, 117–132.

OREGES. (2023). *Bilan énergétique de la Corse 2022*. Observatoire Régional de l'Énergie, des Gaz à effet de serre et de l'Air de Corse, Ajaccio.

Ostrom, E. (1990). *Governing the Commons: The Evolution of Institutions for Collective Action*. Cambridge University Press.

Robert, J.-H. N. (2026a). Infrastructure is all you need: A three-layer architecture for structural AI safety grounded in compute sovereignty and democratic energy governance. MareNostrum Working Paper. `github.com/JeanHuguesRobert/marenostrum/blob/main/infrastructure_is_all_you_need.md`

Robert, J.-H. N. (2026b). Democratic Humans in the Loop (DHITL): Why infrastructure is all you need for AI safety. MareNostrum Working Paper. `github.com/JeanHuguesRobert/marenostrum/blob/main/DHITL.md`

Robert, J.-H. N., & Valdes, G. (2026). Constellia: A fractal architecture for energy, food, and digital sovereignty in island territories. *Proceedings of ICOME'26* (submitted, not accepted yet). Université de Corse Pasquale Paoli, Corte. `github.com/JeanHuguesRobert/marenostrum/blob/main/constellia.md`

Sastry, G., Heim, L., Belfield, H., et al. (2024). Computing power and the governance of artificial intelligence. *arXiv preprint* arXiv:2402.08797.

Sevilla, J., Heim, L., Ho, A., et al. (2022). Compute trends across three eras of machine learning. *arXiv preprint* arXiv:2202.05924.

Sternberg, A., & Bardow, A. (2015). Power-to-What? Environmental assessment of energy storage systems. *Energy and Environmental Science* 8(2), 389–400.

Taleb, N. N. (2012). *Antifragile: Things That Gain from Disorder*. Random House.

Weselek, A., Ehmann, A., Zikeli, S., Lewandowski, I., Schindele, S., Högy, P. (2019). Agrophotovoltaic systems: applications, challenges, and opportunities. *Agronomy for Sustainable Development* 39(4), 35.

*(Full BibTeX to be added before release. All MareNostrum working papers: https://github.com/JeanHuguesRobert/marenostrum — CC BY-SA 4.0.)*


*© 2026 Jean Hugues Noël Robert, baron Mariani — Institut Mariani / C.O.R.S.I.C.A.*
*Published under Creative Commons CC BY-SA 4.0.*
*Canonical repository: https://github.com/JeanHuguesRobert/marenostrum*
*Contact: jhr@baronsmariani.org*

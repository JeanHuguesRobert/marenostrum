---
canonical_url: https://github.com/JeanHuguesRobert/marenostrum/blob/main/ARCHITECTURE.md
last_stamped_at: 2026-05-15
---
# MareNostrum — System Architecture

*Institut Mariani / C.O.R.S.I.C.A. — Corte, Corsica*  
*Living document — CC BY-SA 4.0 — Priority by commit timestamp*

---

## What This Document Is

This document describes the MareNostrum system as a whole — how its layers connect, how information flows between them, what properties emerge from their combination, and what the system is ultimately for.

It does not replace the layer-specific documents (`MODEL.md`, `PRICING.md`, `CONTRACTS.md`, `GOVERNANCE.md`). It is the map that shows how those documents fit together, and the argument for why the combination produces something the parts alone do not.

---

## 1. The System in One Statement

MareNostrum is a **closed-loop transformation of physical solar energy into governed economic value**, in which every conversion step — from photon to kilowatt-hour, from kilowatt-hour to availability guarantee, from guarantee to compute token, from compute token to democratic accountability — is physically grounded, economically priced, contractually committed, and governably traceable.

The novelty is not in any single layer. It is in the closure of the loop: the fact that governance decisions feed back into physical allocation, that physical scarcity drives pricing, that pricing drives contract selection, that contract execution is governed, and that the entire chain is auditable end-to-end by anyone with access to the public register.

---

## 2. The Four Layers

### Physical Layer — `MODEL.md`

**Input**: solar irradiance, local demand, storage state.  
**Output**: P(t), D(t), S(t), R(t), U(t), E.  
**Role**: ground truth. Every other layer is constrained by this one.

The physical layer cannot be negotiated with. R(t) is what it is. A governance decision that ignores R(t) will produce a physical outcome that contradicts it — brownout, breach, or storage exhaustion. The architecture enforces this: automated systems at L₀ execute against measured physical state, not against assumed or projected state.

### Economic Layer — `PRICING.md`

**Input**: R(t), α, p₀.  
**Output**: p(t), risk_premium(t).  
**Role**: translate physical scarcity into price signal.

The economic layer makes the physical state legible to market actors. R(t) is a technical measurement; p(t) is an economic signal that drives storage investment, demand shifting, and contract selection. The mapping between them — the scarcity function f and the calibration of α — is a technical choice validated against observed behavior, not an administrative decision.

### Contractual Layer — `CONTRACTS.md`

**Input**: p(t), risk_premium(t), G (guarantee level).  
**Output**: delivery commitments, compensation obligations, collateral requirements.  
**Role**: translate price signals into binding obligations.

The contractual layer converts the economic signal into durable commitments. A user who needs guaranteed availability buys a Security or Sovereign contract; they pay the guarantee premium and receive a legally and technically enforceable commitment. The contract register (Fractavolta L₂) records every commitment and its execution, creating the audit trail that makes the commitment credible.

### Governance Layer — `GOVERNANCE.md`

**Input**: contract execution records, scarcity events, political decisions from L₃.  
**Output**: allocation rules, benchmark updates, emergency activations, accountability events.  
**Role**: arbitrate the distributional rules within physical constraints.

The governance layer does not override the physical layer — it cannot. What it controls is the political question of *who gets served first* when the physical system cannot satisfy all demand simultaneously. This is a question that must be answered democratically, because the answer determines who bears the burden of scarcity and who does not.

---

## 3. The Feedback Loop

The system operates as a closed loop:

```
Physical state (R(t), U(t))
    ↓
Price signal (p(t))
    ↓
Contract activation and allocation hierarchy
    ↓
Governance oversight and rule enforcement
    ↓
Storage investment, demand flexibility, infrastructure decisions
    ↓
Physical state (R(t), U(t)) [updated]
```

The loop is not instantaneous. Physical state changes in real time; prices adjust continuously; contract allocation activates within seconds; governance responds on timescales of days to months; infrastructure decisions play out over years. Each layer operates at its appropriate timescale, and the system is stable when the feedback between them is correctly designed.

The key stability condition: the governance layer must not attempt to override the physical layer on timescales faster than physical adjustment can occur. A governance decision to "lower prices during scarcity" does not change R(t) — it simply decouples price from physical reality, destroying the investment signal for storage and guaranteeing worse scarcity in the future.

---

## 4. The Central Variable

Every layer is a transformation of one underlying variable: **R(t)**, the instantaneous imbalance between production and demand.

- Physical layer: R(t) is measured.
- Economic layer: R(t) is priced through f(R(t)).
- Contractual layer: R(t) determines which contracts activate and in what order.
- Governance layer: R(t) > 0 triggers the allocation hierarchy and may trigger emergency governance events.

This is not a coincidence of notation. It reflects a design principle: a system in which different layers respond to different variables will produce inconsistent behavior under stress. By grounding every layer in the same observable physical quantity, the system maintains coherence when its layers are under simultaneous pressure.

---

## 5. The Stack in Context

MareNostrum is one layer in a larger ecosystem. Its position:

```
Mediterranean solar radiation (physical commons)
    ↓
MareNostrum energy governance stack
    (MODEL → PRICING → CONTRACTS → GOVERNANCE)
    ↓
Safe Compute Exergy (SCE) — compute certification layer
    (safe_compute_exergy.md)
    ↓
Fractal traceability register
    (traceable_governance.md / Fractavolta)
    ↓
CXU market — sovereign compute tokens
    ↓
Democratic AI infrastructure
```

The MareNostrum stack converts solar energy into governed energy availability. The SCE layer converts governed energy availability into certified compute. The Fractavolta register makes both certifications verifiable. The CXU market converts certification into economic value. The democratic AI infrastructure converts economic value into political sovereignty.

Each step adds something the previous step does not provide: governance, certification, verifiability, market liquidity, political accountability. The full value chain requires all steps; none is redundant.

---

## 6. Storage as the Transversal Element

Storage S(t) appears in every layer:

- **Physical**: absorbs surplus production, covers deficit demand.
- **Economic**: stabilizes price volatility by damping R(t) spikes.
- **Contractual**: provides the physical backing for guarantee commitments.
- **Governance**: determines the depth of reserves available during emergency allocation.

This is why storage investment is the central strategic decision in a MareNostrum deployment. Undersizing storage creates brittleness in every layer simultaneously: physical breaches, price volatility, contract failures, and governance crises all become more frequent and more severe. Oversizing storage wastes capital but reduces system risk.

The optimal sizing is a function of local demand patterns, solar irradiance variability, contract mix (higher G_average requires more storage), and risk tolerance. It can be calculated from the model in `MODEL.md` once local parameters are characterized.

---

## 7. Traceability as the Unifying Property

The one property that makes the closed loop governable is traceability. Without it:

- Physical measurements are taken on trust — which is broken the moment an operator has an incentive to misreport.
- Pricing is based on stated rather than measured R(t) — which creates an obvious manipulation opportunity.
- Contracts are executed according to self-reported delivery records — which cannot be independently verified.
- Governance decisions are made without reliable data about what the physical system is actually doing.

With append-only, cryptographically signed traces at every layer, independently aggregated up the Fractavolta scale tower, none of these failure modes is possible. The physical state is independently measured at L₀ and attested at L₁. Price calculations are derived from the attested measurements. Contract execution is recorded by the cluster, not the operator. Governance deliberations are publicly recorded.

Traceability does not make the system perfect. It makes its imperfections visible — which is the precondition for correcting them.

---

## 8. What the System Is For

This architecture is not a technical project looking for a use case. It is a response to a specific political problem: the Mediterranean's solar resources are being systematically undervalued, exported, and captured by actors outside the territory, because no governance infrastructure exists to assert territorial sovereignty over their use.

The technical stack is the governance infrastructure. CXU certification is not a product feature — it is the mechanism by which a Corsican solar farm can demonstrate, cryptographically, that its energy was produced locally, governed democratically, and converted into compute under conditions that no external actor can unilaterally alter. The Exergy Lock Protocol is not a security feature — it is the technical expression of the foundational axiom: the territory's resources belong to the territory's inhabitants, and that claim can be enforced.

The economic premium (×10–×31 for Sovereign-tier CXU) is not a market arbitrage opportunity. It is the economic recognition that a compute infrastructure under democratic, territorial governance is worth more than one that is not — because it provides something that no commercially optimized, externally governed alternative can provide: credible sovereignty.

---

## 9. Open Problems at the System Level

**Multi-zone consistency**: the model in `MODEL.md` describes a single site. A Mediterranean network of interconnected sites must coordinate R(t) across zones — energy that is scarce in Corsica may be surplus in Tunisia. The inter-zone allocation rules require extension of the governance model to handle cross-border scarcity events without creating dependency hierarchies that violate the foundational axiom. Partially addressed in `infrastructure_topologies_for_compute_sovereignty.md`; not yet formalized.

**Simulation before deployment**: the feedback loop between layers should be tested computationally before physical deployment. A multi-agent simulation of the full stack under realistic Mediterranean demand and solar profiles would validate the stability of the pricing and contract mechanisms and identify calibration requirements for α and C. Not yet built.

**Legal recognition**: the CXU is economically meaningful only if it is legally recognizable — as a contract instrument, as a carbon credit proxy, as a regulatory compliance tool. Legal recognition in EU jurisdictions requires engagement with DG ENER, the EU AI Act governance framework, and potentially the ETS (Emissions Trading System). Not yet initiated.

---

*This document synthesizes: `MODEL.md`, `PRICING.md`, `CONTRACTS.md`, `GOVERNANCE.md`.*  
*Related ecosystem: `safe_compute_exergy.md`, `traceable_governance.md` (FractaVolta), `infrastructure_topologies_for_compute_sovereignty.md`, `DHITL.md`.*  
*License: CC BY-SA 4.0 — Priority by commit timestamp.*

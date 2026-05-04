# MareNostrum — Operational Exergy Model

*Institut Mariani / C.O.R.S.I.C.A. — Corte, Corsica*  
*Living document — CC BY-SA 4.0 — Priority by commit timestamp*

---

## What This Document Is

This document defines the physical model underlying the MareNostrum system. It is the ground floor: every pricing formula, every contract commitment, every governance decision in the stack above is ultimately constrained by what this model says about physical reality.

The model is deliberately minimal. It captures the one variable that matters — the instantaneous balance between production and demand — and derives from it a measure of *useful* energy rather than raw energy. This distinction is the foundation of everything else.

---

## 1. The Core Distinction: Energy vs. Useful Energy

A kilowatt-hour produced at 3am when demand is zero is not the same product as a kilowatt-hour delivered during a grid stress event at 7pm. Standard energy accounting treats them identically. This model does not.

The value of energy is not in its production. It is in its capacity to satisfy demand at the moment demand exists. An energy system optimized on average production is optimized on the wrong variable. The correct optimization target is **availability under scarcity** — which is a function of the timing and reliability of delivery, not of total output.

This reframing has a name in thermodynamics: exergy. The MareNostrum model applies the exergy concept to operational energy systems, yielding a measure of *useful, available energy under real constraints*.

---

## 2. Fundamental Variables

The system is described by four time-varying quantities:

- **P(t)**: instantaneous power produced (kW) — solar, wind, hydro, or other local sources
- **D(t)**: instantaneous demand (kW) — consumption at time t
- **S(t)**: energy currently in storage (kWh), bounded by 0 ≤ S(t) ≤ C
- **C**: maximum storage capacity (kWh) — a physical constant of the installation

All four are observable and measurable. The model is built on measured quantities, not proxies.

---

## 3. Useful Energy

The energy the system can actually deliver at time t is:

```
U(t) = min(P(t) + S(t), D(t))
```

This is the energy that does useful work — that meets actual demand. When production plus storage exceeds demand, U(t) is demand-limited. When demand exceeds production plus storage, U(t) is supply-limited: the system is in deficit.

U(t) is the variable that matters for users. Everything else — pricing, contracts, governance — is derived from it.

---

## 4. Scarcity

Instantaneous scarcity is defined as:

```
R(t) = max(0, D(t) − P(t))
```

R(t) = 0 means the system is in surplus: production meets or exceeds demand without touching storage. R(t) > 0 means production alone is insufficient; the deficit must be covered by storage, or demand goes unmet.

R(t) is the stress signal of the system. It is observable in real time and drives pricing, contract activation, and governance priority decisions. Every layer of the stack is, in one sense, a transformation of R(t) into an appropriate response.

---

## 5. Temporal Value Function

Not all time periods are equal. Energy delivered during high-scarcity periods is worth more than energy delivered during surplus. This is not a pricing choice — it is a physical fact about the system's operational state.

A temporal weight function captures this:

```
w(t) = f(R(t))
```

where f is increasing in R(t). Two canonical forms:

- Linear: `w(t) = 1 + α · R(t)` — suitable for moderate scarcity regimes
- Exponential: `w(t) = exp(α · R(t))` — suitable for systems where extreme scarcity events dominate value

The parameter α > 0 represents the system's sensitivity to scarcity. Its calibration is empirical: it should be estimated from observed demand patterns in the specific territory, not assumed.

---

## 6. Operational Exergy

The total value of service the system delivers over a period τ is:

```
E = ∫₀^τ w(t) · U(t) dt
```

This is the operational exergy of the system: the time-integral of useful energy, weighted by the scarcity context in which it was delivered.

E is the fundamental quantity that the economic and contractual layers are built on. A system that delivers 100 MWh during periods of high scarcity has higher operational exergy than one that delivers 120 MWh uniformly — and commands a corresponding premium.

---

## 7. System Regimes

The model exhibits three qualitatively different operating regimes:

**Surplus** (P(t) > D(t)): production exceeds demand. U(t) = D(t). R(t) = 0. w(t) = 1. Excess production charges storage up to capacity C; beyond C, it is wasted or exported. The marginal value of additional production in this regime is low.

**Balance** (P(t) ≈ D(t)): production matches demand. The system operates at maximum efficiency. Storage is used minimally. This is the target steady-state.

**Scarcity** (P(t) < D(t)): production is insufficient. R(t) > 0. w(t) > 1. Storage is discharged to cover the deficit. If S(t) = 0 and R(t) > 0, the system cannot meet demand — a breach event occurs. The marginal value of storage in this regime is very high.

**Key structural property**: the value of the system is dominated by its behavior during scarcity events, not by its average output. A system that rarely fails under stress is worth more than one with higher average production but frequent stress failures. This is the core argument for sizing storage generously and for the scarcity-weighted pricing model in `PRICING.md`.

---

## 8. The Role of Storage

Storage S(t) is not an add-on. It is the mechanism that decouples production timing from demand timing — which is the entire problem in a solar-dominated system.

Without storage, a solar system is perfectly available at midday and entirely unavailable at night. With storage, production at midday is shifted to availability at night. The value created by this shift is exactly the difference in w(t) between the two periods: the energy is the same, but its operational exergy is higher when delivered during the high-demand evening hours.

This is why the model treats storage capacity C as a first-class parameter. Optimizing a MareNostrum deployment means choosing C to minimize the frequency and depth of breach events, given the local distribution of P(t) and D(t). The optimal C is not the one that maximizes total storage — it is the one that minimizes scarcity exposure at minimum cost.

---

## 9. Relation to Safe Compute Exergy

The MareNostrum energy model is the physical substrate of the Safe Compute Exergy (SCE) framework defined in `safe_compute_exergy.md`. The CXU (Compute eXergy Unit) is denominated in terms of the operational exergy E defined here, adjusted for hardware efficiency, system losses, SLA compliance, and provenance traceability.

Concretely: a compute job that runs during a high-R(t) period consumes energy with higher operational exergy than one running during surplus. The CXU cost of the job reflects this — not as a penalty, but as an accurate accounting of the value of the resource consumed.

This creates the correct incentive: compute operators who schedule jobs during surplus periods (charging storage, running batch workloads at night) pay less per CXU and make more efficient use of the system. Operators who require real-time delivery during peak demand pay the scarcity premium — and receive the corresponding Sovereign-tier certification in return.

---

## 10. What This Model Does Not Claim

This model does not claim to be complete. It is a minimal formalization of the variables and relationships that drive the system's core behavior. Several important aspects are outside its scope:

- **Multi-zone dynamics**: the model describes a single site. Mediterranean-scale interconnection between multiple sites requires a multi-node extension, which is partially addressed in `infrastructure_topologies_for_compute_sovereignty.md`.
- **Demand forecasting**: D(t) is treated as an input. Forecasting it requires separate modeling.
- **Production forecasting**: P(t) is treated as an input. Solar irradiance forecasting is a mature field; its integration is left to deployment-specific implementations.
- **Storage degradation**: C is treated as constant. Battery capacity degrades over time; the model requires periodic recalibration.

These are not objections to the model. They are boundaries that make it precise.

---

*Upstream: this document is the physical foundation for `PRICING.md`, `CONTRACTS.md`, `GOVERNANCE.md`, and `ARCHITECTURE.md`.*  
*Related: `safe_compute_exergy.md` (compute exergy layer), `infrastructure_topologies_for_compute_sovereignty.md` (multi-site extension).*

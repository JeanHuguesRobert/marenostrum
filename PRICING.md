---
canonical_url: https://github.com/JeanHuguesRobert/marenostrum/blob/main/PRICING.md
last_stamped_at: 2026-05-16
---
# MareNostrum — Energy Availability Pricing Model

*Institut Mariani / C.O.R.S.I.C.A. — Corte, Corsica*  
*Living document — CC BY-SA 4.0 — Priority by commit timestamp*

---

## What This Document Is

This document defines how the physical model in `MODEL.md` translates into economic value. The central argument is simple: the product being sold is not a kilowatt-hour. It is a guarantee of availability under scarcity. Pricing a kilowatt-hour as a commodity ignores the only variable that determines its actual value to the user — whether it is there when needed.

The pricing model is derived from the physics, not imposed on it. Every formula here follows directly from the scarcity variable R(t) defined in `MODEL.md`.

---

## 1. Why Standard Energy Pricing Fails Here

Spot electricity markets price energy on marginal cost of production. This works reasonably well for fossil fuel systems where the marginal cost of producing another unit of energy is relatively stable and production can be throttled on demand.

It fails for solar-dominated island systems for two reasons.

First, the marginal cost of solar production is effectively zero during surplus — but the system still has capital costs that must be recovered. A pure spot price collapses to zero at the worst possible time for cost recovery.

Second, and more importantly, the thing users actually need is not energy in the abstract — it is energy at the moment they need it. A pricing model that does not reflect availability-under-scarcity gives no economic signal to invest in storage, no signal to shift deferrable demand to surplus periods, and no signal to reward operators who maintain availability commitments during stress events.

The MareNostrum pricing model is designed to give all three signals correctly.

---

## 2. The Product Being Priced

Before defining the price formula, the product must be defined precisely.

The product is **a unit of energy availability under system constraint**: energy that is delivered at time t, in a system state characterized by scarcity R(t), with a delivery guarantee G ∈ [0,1].

This is not a kilowatt-hour. A kilowatt-hour is a physical quantity. What is being sold here is a kilowatt-hour *plus* the commitment to deliver it *plus* the infrastructure that makes that commitment credible *plus* the governance that enforces it.

The pricing model must reflect all four components.

---

## 3. Base Price and Scarcity Function

The unit price at time t is:

```
p(t) = p₀ · f(R(t))
```

where:
- `p₀` is the base price — the price during surplus conditions (R(t) = 0)
- `f` is a scarcity function, strictly increasing in R(t), with f(0) = 1

Two canonical forms for f, appropriate for different market contexts:

**Linear** — `f(R) = 1 + α·R`  
Appropriate when scarcity events are moderate and relatively frequent. The price increases proportionally to the deficit. Simple to communicate, easy to audit.

**Exponential** — `f(R) = exp(α·R)`  
Appropriate when the system is dominated by rare, high-severity scarcity events. The price increases steeply as scarcity deepens, creating strong incentives for storage investment and demand flexibility. Better reflects the actual risk structure of island solar systems.

The parameter α is the scarcity sensitivity coefficient. It must be calibrated empirically from observed demand patterns and storage dynamics in each deployment context. A single Mediterranean-wide α is not appropriate: Tunisia's high-solar, high-demand profile calls for a different calibration than Corsica's more moderate and seasonal profile.

---

## 4. Three Operating Regimes

**Surplus regime** (R(t) = 0, S(t) approaching C)  
f(R) = 1. Price equals p₀. Energy is abundant; the system signal is: consume now, charge storage, defer nothing. Marginal value of additional production is low. This is the period during which deferrable compute workloads should run — batch inference, model training, data processing.

**Balance regime** (R(t) ≈ 0, S(t) partially charged)  
f(R) ≈ 1. Price near p₀. Normal operating conditions. The system is meeting demand from production with storage as buffer. No special pricing signals needed.

**Scarcity regime** (R(t) > 0, S(t) being discharged)  
f(R) > 1, increasing rapidly. Price rises above p₀. The system is under stress. Every unit of energy delivered is worth more than in surplus. This is the period during which Sovereign-tier CXU commands its premium: the inference was produced using energy delivered under scarcity conditions, with full provenance traceability, and carries the corresponding certification.

---

## 5. The Guarantee Premium

The scarcity function captures time-varying value. But some users need more than real-time pricing — they need a forward commitment: a guarantee that energy will be available regardless of system state. This guarantee has a price.

The guarantee premium adds to the spot price:

```
p_guaranteed(t, G) = p(t) + G · risk_premium(t)
```

where:
- G ∈ [0,1] is the guarantee level (defined in `CONTRACTS.md`)
- `risk_premium(t)` is the cost of holding the storage reserves required to honor the guarantee at time t

A G = 0 contract is pure spot: no guarantee, price equals p(t). A G = 1 contract is full guarantee: the operator commits to delivery regardless of R(t), and prices in the full cost of the storage reserves required to make that commitment credible.

The guarantee premium is not profit margin. It is the economic representation of the physical cost of maintaining reserves. A system that prices guarantees too cheaply will under-invest in storage and fail to honor commitments during stress events — destroying the value of the guarantee product.

---

## 6. Storage as Price Stabilizer

Storage S(t) dampens price volatility by absorbing the impact of production variability on R(t). When S(t) is high, the system can cover demand during production shortfalls without R(t) rising sharply — keeping prices near p₀ and protecting users from volatility.

This creates a clear economic role for storage investment: it reduces the variance of the price distribution. Users who value price predictability should be willing to pay a premium for it — which is exactly what guaranteed contracts formalize.

The relationship between storage capacity C, scarcity frequency, and price volatility can be derived from the model in `MODEL.md`. Optimal C minimizes the expected cost of scarcity events (price spikes times their probability and depth) net of storage capital cost. This is a standard optimization problem once the local distribution of P(t) and D(t) is characterized.

---

## 7. Distribution Properties

The price distribution in this model is not normal. It is right-skewed, with a heavy tail driven by rare but severe scarcity events.

This has two implications:

**For operators**: average price is not the right planning metric. Expected worst-case price — the price during the top 5% of scarcity events — determines the economic case for storage investment. A system sized for average conditions will fail under stress; the price spike during that failure will be large.

**For users**: standard energy contracts that average over time obscure the actual risk structure. A user whose operations are sensitive to energy availability should pay for a guaranteed contract priced on the tail distribution, not a spot contract priced on the mean.

This is the same logic that makes insurance valuable: the expected payout is not the point. The point is protection against the tail event.

---

## 8. Connection to CXU Pricing

The energy pricing model defined here is the physical layer beneath the CXU pricing structure in `safe_compute_exergy.md`.

A compute job that runs at time t consumes energy priced at p(t). Its CXU cost reflects:

- p(t) — the scarcity-adjusted energy cost
- η_hw, η_sys, η_sla — hardware and operational efficiency factors
- η_traceability — provenance completeness (the key differentiator for premium tiers)

The Sovereign-tier CXU premium (×10–×31 over spot) corresponds to compute produced during scarcity conditions with full provenance traceability — energy that is both scarce and certified. The pricing model makes this premium structurally coherent: it is not marketing, it reflects the actual cost and value of the physical and governance infrastructure required to produce it.

---

## 9. What Remains to Be Calibrated

The model structure is specified. Three parameters require empirical calibration for each deployment:

**p₀** — the base price. Determined by the capital cost of the installation divided by the expected surplus-period energy volume. Deployment-specific.

**α** — the scarcity sensitivity coefficient. Determined by fitting the price function to historical demand and production data, targeting a price distribution that creates correct incentives for the specific use-case mix of the territory.

**The form of f** — linear vs. exponential. Determined by the severity distribution of scarcity events. If the 95th-percentile scarcity event is less than 2× the median, linear is appropriate. If it is 5× or more, exponential better captures the incentive structure.

These are not weaknesses of the model. They are the parameters that make it accurate for a specific territory rather than generically wrong everywhere.

---

*Upstream: `MODEL.md` (physical definitions of R(t), U(t), E).*  
*Downstream: `CONTRACTS.md` (formalization of the guarantee commitment), `GOVERNANCE.md` (arbitration of allocation under scarcity).*  
*Related: `safe_compute_exergy.md` (CXU pricing layer built on this model).*


<!-- BEGIN_AUTO: backlinks -->
### Backlinks

*These documents link to this file:*
- [Corpus Status — marenostrum](research/corpus-status.md)
- [Research Index — MareNostrum](research/index.md)

<!-- END_AUTO: backlinks -->

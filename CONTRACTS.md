---
canonical_url: https://github.com/JeanHuguesRobert/marenostrum/blob/main/CONTRACTS.md
last_stamped_at: 2026-05-16
---
# MareNostrum — Energy Availability Contracts

*Institut Mariani / C.O.R.S.I.C.A. — Corte, Corsica*  
*Living document — CC BY-SA 4.0 — Priority by commit timestamp*

---

## What This Document Is

This document defines the contractual layer of the MareNostrum system. Contracts are the mechanism by which the physical model (`MODEL.md`) and the pricing model (`PRICING.md`) become binding commitments between parties.

The key distinction: a contract in this system is not an agreement to deliver a quantity of energy. It is an agreement to deliver a level of availability — a guarantee that energy will be there when needed, with explicit consequences if it is not. This distinction is not semantic. It changes what operators must invest in (storage reserves, not just generation capacity) and what users are actually buying (reliability, not commodity).

---

## 1. What Is Being Contracted

Standard energy contracts are delivery contracts: the seller commits to delivering X kilowatt-hours in a period, and the buyer pays for them. The timing of delivery within the period is typically the seller's choice.

MareNostrum contracts are **availability contracts**: the seller commits to maintaining a specified availability level G throughout a period, regardless of system state. If demand arises and R(t) > 0, the contract holder is served before non-contracted demand. The storage reserves required to honor this commitment are the seller's responsibility to maintain.

This is structurally closer to an insurance contract than a commodity contract. The user is buying protection against the tail event — the moment when energy is scarce and operations would otherwise be disrupted.

---

## 2. Contract Types

### 2.1 Spot Contract (G = 0)

No advance commitment. Energy is available at the current market price p(t) when the buyer requests it. During surplus conditions, this is cheap and plentiful. During scarcity events, it is expensive and potentially unavailable — demand is served in order of contract priority, and spot buyers are last.

Appropriate for: deferrable workloads, opportunistic compute, batch operations that can be scheduled during predicted surplus windows.

### 2.2 Standard Contract (G ∈ (0, 0.8))

A partial guarantee. The seller commits to serving the contracted demand with probability G over the contract period. During moderate scarcity events, standard contract holders are served before spot buyers. During severe scarcity events, service may be curtailed proportionally.

Price: `p₀ · f(R̄) + G · risk_premium(R̄)` where R̄ is the expected scarcity level over the contract period.

Appropriate for: general-purpose operations with some tolerance for occasional disruption, agentic AI workloads, commercial services.

### 2.3 Security Contract (G ∈ [0.8, 1.0))

High guarantee. The seller commits to serving contracted demand through all but the most severe system stress events. This requires the seller to maintain dedicated storage reserves sized for the contracted demand level across the expected distribution of scarcity events.

Price reflects the full cost of those reserves plus the scarcity premium. Significantly higher than spot or standard.

Appropriate for: critical infrastructure, medical systems, regulated financial operations, legal and judicial AI support, industrial processes where interruption causes cascading costs.

### 2.4 Sovereign Contract (G = 1.0)

Full guarantee. The seller commits to uninterrupted service under all system conditions, including the activation of the Exergy Lock Protocol (see `safe_compute_exergy.md`). This requires not only local storage reserves but redundant supply pathways and priority access to federation-level reserves.

Sovereign contracts are the basis for Sovereign-tier CXU certification. A compute job run under a Sovereign contract, with full provenance traceability, earns the maximum η_traceability score and the corresponding market premium (×10–×31 over spot).

Appropriate for: public infrastructure, democratic decision systems, safety-critical AI inference, sovereignty-sensitive government operations.

---

## 3. The Guarantee Coefficient G

G is defined operationally, not aspirationally. G = 0.95 means the operator commits to serving contracted demand in 95% of scarcity-hours over the contract period, measured ex post against observed system data.

This makes G auditable. The contract register (implemented via the Fractavolta governance layer, see `traceable_governance.md`) records:
- every scarcity event during the contract period
- the system's delivery performance for each contract holder during each event
- cumulative G delivered vs. G committed

A contract holder who received G_delivered < G_committed is automatically entitled to compensation at the rate specified in §5.

G is not a probability — it is a service-level commitment backed by physical infrastructure and financial collateral.

---

## 4. Activation Hierarchy Under Scarcity

When R(t) > 0 and storage S(t) is being discharged, the system must allocate available energy across competing demands. The allocation hierarchy is:

1. **Sovereign contracts (G = 1.0)**: served first, always. Reserve drawdown is authorized unconditionally.
2. **Security contracts (G ≥ 0.8)**: served from dedicated reserves. If reserves are insufficient, partial curtailment applies proportionally within this tier.
3. **Standard contracts (G < 0.8)**: served from shared reserves after Sovereign and Security demands are met. Curtailment probability = 1 − G per scarcity-hour.
4. **Spot buyers**: served from whatever remains after contracted demand is met. No guarantee; curtailment is possible at any scarcity level.
5. **Export**: served last, only after all contracted and spot demand is fully met.

This hierarchy is not discretionary. It is encoded in the governance layer and executed automatically based on real-time R(t) measurements. No operator has the authority to override the hierarchy for individual transactions — doing so would generate a governance escalation event (a cross-level trace in the Fractavolta register).

---

## 5. Non-Delivery and Compensation

When a contracted delivery fails — G_delivered falls below G_committed for a given period — compensation is automatic:

```
Compensation = (G_committed − G_delivered) · E_contracted · p_scarcity
```

where `p_scarcity` is the scarcity-weighted price during the shortfall period, and `E_contracted` is the contracted energy volume.

Compensation is paid in one of two forms:
- **Financial credit**: immediate credit against future invoices, calculated at the scarcity price
- **Energy credit**: future delivery of equivalent energy at guaranteed availability, credited to the contract holder's reserve account

The choice between forms is specified in the contract. Compensation is calculated automatically from the audit log and does not require the contract holder to file a claim.

---

## 6. Collateral Requirements

Operators offering Security and Sovereign contracts must post collateral proportional to their commitment. Collateral serves two functions: it backs the compensation mechanism if delivery fails, and it creates a financial incentive for operators to maintain the storage reserves required to honor their commitments.

Minimum collateral by tier:
- Standard: 10% of contract value
- Security: 30% of contract value
- Sovereign: 50% of contract value, plus membership in the mutual insurance pool (see §7)

Collateral is held in the system's insurance layer and released at contract expiry, minus any compensation payments made during the period.

---

## 7. Mutual Insurance Pool

No individual operator's storage reserves can guarantee immunity against prolonged regional scarcity events — multi-day cloud cover, sustained heatwaves driving demand above all forecasts, or coordinated infrastructure failure. Events at this scale require mutual insurance across the federation.

The mutual pool is funded by a levy on Security and Sovereign contract premiums (provisionally: 5% of the guarantee premium component). It is governed by the federation governance layer (L₃ in the Fractavolta scale tower) and activated only for events that exceed individual operator reserve capacity by a defined threshold.

Activation conditions are predefined, multi-party verifiable, and publicly auditable — a governance escalation event in the Fractavolta register, not a discretionary decision.

---

## 8. Traceability of Contract Execution

Every contract event — issuance, activation, delivery measurement, compensation calculation, collateral adjustment — is recorded as a signed trace tuple in the Fractavolta register:

```
τ = (contract_id, event_type, timestamp, R(t), G_delivered, compensation, sig)
```

This creates a complete, append-only audit trail of every contract's lifecycle. A regulator at L₃ can verify that all contracts were honored according to their terms without accessing the content of individual compute jobs. A contract holder can verify their own delivery record without trusting the operator's self-reporting.

Contract execution is not self-reported. It is computed automatically from the metered energy data and recorded by the cluster (L₁), not by the operator node (L₀). The operator cannot selectively omit unfavorable delivery events.

---

## 9. Relation to CXU Issuance

CXU issuance in the MareNostrum system is conditional on contract tier. A compute job run under a Sovereign contract, with full provenance traceability, generates a Sovereign-tier CXU. The same job run under a Spot contract generates a Spot-tier CXU, regardless of the energy source.

This coupling is intentional. The CXU tier reflects not just the energy source but the governance infrastructure that makes the provenance claim credible. A Sovereign-tier claim requires a Sovereign contract because the guarantee is what makes the claim verifiable and defensible — not just at the moment of issuance but indefinitely, through the audit trail in the contract register.

---

*Upstream: `MODEL.md` (physical constraints), `PRICING.md` (price formulas for G and risk_premium).*  
*Downstream: `GOVERNANCE.md` (arbitration of allocation hierarchy under contested scarcity).*  
*Related: `traceable_governance.md` (register infrastructure), `safe_compute_exergy.md` (CXU tier coupling).*


<!-- BEGIN_AUTO: backlinks -->
### Backlinks

*These documents link to this file:*
- [Corpus Status — marenostrum](research/corpus-status.md)
- [Research Index — MareNostrum](research/index.md)

<!-- END_AUTO: backlinks -->

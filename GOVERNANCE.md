---
canonical_url: https://github.com/JeanHuguesRobert/marenostrum/blob/main/GOVERNANCE.md
last_stamped_at: 2026-05-15
---
# MareNostrum — Governance of the Energy System

*Institut Mariani / C.O.R.S.I.C.A. — Corte, Corsica*  
*Living document — CC BY-SA 4.0 — Priority by commit timestamp*

---

## What This Document Is

This document defines how decisions are made in the MareNostrum system. It sits above the physical, pricing, and contractual layers — but it does not override them. Physical constraints cannot be governed away; the model in `MODEL.md` sets hard limits that no governance decision can breach. Within those limits, governance determines how available resources are allocated, by whom, according to what principles.

The central design choice: governance is not a management layer added for regulatory compliance. It is the mechanism that prevents the technical system from being captured by any single actor — operator, regulator, or state. The architecture of the governance layer is designed so that capture is architecturally visible and therefore preventable.

---

## 1. The Foundational Axiom

> The solar and hydraulic resources of the Mediterranean belong, first, to the people who live under them.

This is not a political slogan. It is the architectural starting point. Every rule in this document follows from it. Any technical or economic arrangement that systematically extracts value from a territory's energy resources without proportional benefit to the territory's inhabitants is a violation of the axiom — and the governance layer must make such violations detectable and correctable.

The axiom has a corollary: energy governance is not a technical optimization problem. It is a political problem with technical constraints. The governance layer must combine both — computational enforcement of physical rules and democratic determination of distributional rules.

---

## 2. Separation of Concerns

The system separates three distinct types of decision, which must not be conflated:

**Operational decisions** are executed automatically at L₀–L₁ (node and cluster level). They implement pre-agreed rules without human intervention: enforcing the contract hierarchy under scarcity, activating storage drawdown, computing compensation. No operator has discretionary authority over these decisions once the rules are set. Discretion at the operational level is a capture risk.

**Technical mediation decisions** arise when operational rules produce ambiguous or contested outcomes — a dispute over measured R(t), a disagreement about whether an outage was voluntary or involuntary, a question about whether a new hardware configuration meets the SLA requirements for Sovereign-tier certification. These decisions are made at L₂ (regional federation level) by auditable expert panels whose deliberations are recorded in the governance register.

**Political decisions** concern the rules themselves: what are the allocation priorities, how should α be calibrated, when should the mutual insurance pool be activated, how should the reference inference be updated as hardware evolves. These decisions are made at L₃ (Mediterranean network level) by democratic governance, where every permanent resident of the territory has one vote and one voice.

Mixing these three types generates dysfunction in both directions: automating political decisions removes democratic legitimacy; democratizing operational decisions introduces unacceptable latency; making technical decisions by majority vote produces technically incoherent outcomes.

---

## 3. Scale Tower

The governance structure maps to the Fractavolta scale tower:

**L₀ — Compute node**: executes rules, produces traces. No governance authority.

**L₁ — Cluster**: audits execution, detects anomalies, produces aggregate measurements. No rule-setting authority; authority to flag technical disputes for L₂.

**L₂ — Island/regional federation**: resolves technical disputes, issues CXUs, manages the regional contract register, proposes rule changes to L₃. Authority over technical mediation decisions.

**L₃ — Mediterranean network**: sets the rules — allocation priorities, α calibration, benchmark governance, mutual insurance activation thresholds, cross-border policy. Authority over political decisions. One person, one voice.

A higher level cannot act on behalf of a lower level without generating a cross-level trace event — a visible, attributed record of the intervention. This makes governance capture architecturally observable: any attempt by L₃ to override L₁ operational rules, or by L₂ to pre-empt L₀ execution, leaves a trace that any participant can audit.

---

## 4. Democratic Governance at L₃

The foundational axiom requires that rule-setting authority reside with the people who inhabit the territory. At L₃, this means:

**One person, one voice**: every permanent resident of a MareNostrum territory has equal voting weight in rule-setting decisions. Voting weight is not proportional to energy consumption, capital contribution, or technical expertise.

**Imperative mandates**: delegates to the L₃ governance body are bound by the positions voted by their constituency. They cannot exercise personal discretion on contested questions. A delegate who votes contrary to their mandate generates an accountability event in the governance register.

**Revocable mandates**: constituencies can recall their delegates at any time through a defined procedure. Recall generates a governance event and triggers a by-election within a specified timeframe.

**Transparency**: all L₃ deliberations, voting records, and mandate compliance reports are publicly accessible in the governance register. Opacity at L₃ is a protocol violation, not just a policy failure.

This is the same governance interface that operates at L₁ and L₂, scaled to the Mediterranean network. The fractal property holds: a local community that understands how their village assembly governs the cluster also understands how the Mediterranean assembly governs the network, because the mechanism is identical.

---

## 5. Allocation Priorities

The allocation hierarchy under scarcity is a political decision, set at L₃. The current default hierarchy, which can be revised by supermajority vote, is:

1. **Vital local needs**: drinking water, heating, medical equipment, emergency communication. Served unconditionally, regardless of contract status.
2. **Critical infrastructure**: water treatment, hospitals, emergency services. Served under Sovereign contract rules.
3. **Essential economic activity**: activities whose interruption causes disproportionate harm to the local community. Served under Security contract rules.
4. **General contracted demand**: served according to contract tier hierarchy (Sovereign > Security > Standard > Spot).
5. **Export**: served only after all internal demand is met.

This hierarchy is not about rewarding contract holders. It is about protecting the population that the foundational axiom identifies as the primary beneficiary of the resource. A Sovereign contract that takes priority over a hospital's vital needs would violate the axiom — and such a contract cannot be issued under the current rules.

---

## 6. Anti-Capture Design

The governance layer is explicitly designed to prevent four capture scenarios:

**Operator capture**: an operator controlling a majority of generation or storage capacity gaining de facto control over allocation. Counter-mechanism: allocation is automated at L₀–L₁ under rules set at L₃, not discretionary at the operator level. An operator who attempts to override automated allocation generates a detectable trace.

**State capture**: a government exercising emergency powers to redirect energy flows for political rather than operational purposes. Counter-mechanism: emergency activation of the Exergy Lock Protocol requires multi-party verification at L₂ and generates a public L₃ governance event. Unilateral state override is architecturally impossible without detection.

**Regulatory capture**: a regulatory body controlled by incumbent operators shaping the rules to entrench their position. Counter-mechanism: rule-setting authority at L₃ is democratic, not regulatory. Regulators participate as technical advisors, not as decision-makers. Their recommendations are visible in the governance register; the democratic vote is independent.

**Benchmark capture**: hardware manufacturers who benefit from reference inference inflation influencing the I_ref update process to inflate CXU supply. Counter-mechanism: reference inference updates require L₃ supermajority vote, and the voting record is public. Manufacturers can propose updates but cannot vote on them.

---

## 7. Governance of the Benchmark

The reference inference I_ref (defined in `safe_compute_exergy.md`) is a governed convention that determines the CXU denomination. As hardware efficiency improves, a fixed I_ref becomes easier to achieve, creating inflationary pressure on CXU supply.

The L₃ governance body manages this through a defined update process:

1. Any participant can propose an I_ref update, citing hardware efficiency data.
2. The proposal is published in the governance register, open for comment for 60 days.
3. L₂ technical panels assess the proposal and publish a recommendation.
4. L₃ votes on adoption by supermajority (two-thirds of participating voters).
5. If adopted, existing CXUs denominated in the old I_ref remain valid under their issuance terms. New CXUs are denominated in the new I_ref.

The transition period — during which both old and new denominations coexist — must be specified in the adoption vote. Ambiguity in the transition is a governance failure.

---

## 8. Governance Register

All governance events are recorded in the Fractavolta register as signed, append-only traces:

```
τ = (event_type, level, actors, decision, timestamp, vote_record, sig)
```

This applies to: L₃ votes, L₂ technical dispute resolutions, L₁ anomaly flags, mandate compliance reports, recall events, emergency activations, benchmark update proposals and adoptions.

The register is the memory of the governance system. A governance decision that is not in the register did not happen in a form that can be held accountable. Governance events that disappear from the record — which is impossible in a properly implemented append-only system — indicate a fundamental breach of the architecture.

---

## 9. Subsidiarity as Protocol

The EU principle of subsidiarity — decisions belong at the lowest capable level — is not a guideline here. It is enforced by the architecture.

A higher level can only act on behalf of a lower level by generating a cross-level trace escalation event. This event is visible to all participants at the lower level. A lower level that believes a higher-level intervention was inappropriate can challenge it through the L₂ technical dispute process, which generates its own governance record.

The practical implication: L₃ cannot quietly override a L₁ operational rule. The override is recorded, attributed, and challengeable. Subsidiarity is not violated silently.

---

## 10. Limitations

**Sybil resistance**: democratic governance at L₃ requires unique identity — one person, one voice — without a centralized identity registry. Zero-knowledge proofs of unique humanity are a candidate solution; their governance is unresolved. Until this is specified, L₃ voting is vulnerable to Sybil attacks at scale.

**Cross-jurisdiction legitimacy**: a Mediterranean governance body spanning Corsica, Sardinia, Sicily, and Tunisia operates across four legal jurisdictions with different constitutional frameworks. The legal basis for L₃ decisions to have binding effect in each jurisdiction requires legal design that this document does not attempt.

**Speed under crisis**: democratic deliberation is slow. A fast-moving crisis — a grid failure, an extreme weather event — may require operational responses faster than L₃ can convene. The Exergy Lock Protocol provides pre-agreed automated responses; L₃ authority is reserved for situations where the pre-agreed rules are themselves contested.

These are open problems, not objections to the model. They are the next iteration.

---

*Upstream: `MODEL.md`, `PRICING.md`, `CONTRACTS.md`.*  
*Downstream: `ARCHITECTURE.md` (unified system description).*  
*Related: `traceable_governance.md` (register infrastructure and fractal governance formalism), `safe_compute_exergy.md` (CXU governance layer).*

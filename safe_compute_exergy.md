---
canonical_url: https://github.com/JeanHuguesRobert/marenostrum/blob/main/safe_compute_exergy.md
last_stamped_at: 2026-05-16
---
# Safe Compute Exergy (SCE)

**Author:** Institut Mariani / C.O.R.S.I.C.A. · Corte, Corse, France  
**Jean Hugues Noël Robert, baron Mariani**

**Repository:** https://github.com/JeanHuguesRobert/marenostrum  
**License:** CC BY-SA 4.0  
**Related:** [Fractavolta](https://github.com/JeanHuguesRobert/fractavolta) — the architectural substrate for η_traceability

---

## TL;DR

AI constraints have shifted from model scale to **contextualized, infrastructure-bound compute**. Safe Compute Exergy (SCE) defines a measurable and auditable abstraction layer for useful compute through the CXU (Compute eXergy Unit), which integrates energy origin, hardware efficiency, system losses, SLA compliance, and provenance traceability into a single verifiable quantity.

**The central claim:** an inference whose entire energy provenance chain is cryptographically attested — from photon to token — is a qualitatively distinct product from an unattested inference of identical raw performance. The attestation chain *is* the premium. The register is not compliance infrastructure; it is the product itself.

SCE is not a system optimized for epistemic truth. It is a **socio-technical infrastructure for democratic arbitration of computational scarcity under irreversible uncertainty**.

Its foundational axiom is normative: **sovereign democratic governance (1 person = 1 voice) is the final arbitrator of compute infrastructure, even under partial or imperfect technical knowledge.**

---

## Reader's Note

This document formalizes an intuition emerging from the dialogue "Photons to Inferences" (April 2026) and extends the Mediterranean Exergy Charter and `infrastructure_is_all_you_need.md`.

It is a living design artifact. Traceability is structural, not optional — and the same applies to this document's own revision history. Priority of ideas is established by commit timestamp.

The architectural substrate for the traceability layer is specified in [Fractavolta](https://github.com/JeanHuguesRobert/fractavolta): fractal, federated, append-only logs with Merkle aggregation across scale levels. SCE specifies *what* to trace. Fractavolta specifies *how* the register works.

---

## 1. The Problem

### 1.1 Shift of the Bottleneck

The AI bottleneck is no longer primarily model size but:

- localized electrical availability
- temporal energy distribution (solar intermittency)
- infrastructure latency constraints
- system-level efficiency variance across hardware generations

AI has become an **electro-infrastructural industry**. The core constraint is no longer silicon; it is **contextualized, usable energy at the point of inference**.

### 1.2 The Missing Certification Layer

Current approaches to "green AI" or "responsible compute" share a structural defect: they certify at the organizational level, not at the inference level. A datacenter can hold a renewable energy certificate (REC) while running a specific job on grid power during a solar trough. The certificate and the actual energy consumed are decoupled in time and space.

This is equivalent to an AOC wine designation that applies to a château's annual production but cannot be verified for a specific bottle. The market accepts this because cryptographic per-bottle attestation did not previously exist.

It now does. The combination of Trusted Execution Environments (TEE), sub-second energy metering, append-only logs, and Merkle proofs enables **per-inference energy provenance certification**. SCE defines the standard for this certification.

### 1.3 Limits of Current Regulatory Frameworks

Current frameworks (EU AI Act, US compute thresholds) rely on fixed FLOP counts, model-centric risk definitions, and static compliance snapshots. They:

- ignore inference economics and energy locality
- ignore system efficiency variance
- create arbitrage via relocation or hardware optimization
- cannot distinguish a "clean" inference from a "dirty" one of identical capability

SCE defines the missing layer: **verified, provenance-attested compute**.

---

## 2. Foundational Concept: From Energy to Exergy

### 2.1 The Photon-to-Inference Chain

Every inference has a physical history: solar radiation → photovoltaic conversion → storage or direct use → power delivery → chip operation → inference execution → token output.

Each conversion step has a measurable efficiency and an attributable actor. The chain is:

```
τ_solar → τ_conversion → τ_storage → τ_delivery → τ_compute → τ_inference
```

where each τᵢ is a signed trace tuple (see §3.2). The **chain as a whole** is the certificate of origin. A broken link anywhere in the chain collapses provenance to zero, regardless of the validity of the remaining links.

This is the key insight: **provenance is conjunctive, not additive**. A single unattested step invalidates the premium claim for the entire inference, exactly as a single unverifiable step in a wine provenance chain removes the AOC designation.

### 2.2 Compute Exergy: Definition

Compute exergy is the fraction of available energy convertible into *useful, verifiable* inference under real operational constraints. It extends thermodynamic exergy into computational systems.

**Operational formulation:**

```
Xc = E × η_hw × η_sys × η_sla × η_traceability
```

Where:

| Factor | Definition |
|--------|-----------|
| **E** | Contextualized energy: location, timestamp, carbon mix, renewable fraction |
| **η_hw** | Hardware efficiency: FLOP/W for the specific chip and runtime |
| **η_sys** | System-level losses: cooling PUE, networking, orchestration overhead |
| **η_sla** | Service quality: latency compliance, uptime, priority class |
| **η_traceability** | Provenance completeness: fraction of the photon-to-inference chain that is cryptographically attested |

**Key property:**

> η_traceability ∈ [0, 1]. Opaque or non-auditable compute collapses toward zero exergy by design. An inference with no provenance chain has Xc → 0 regardless of physical efficiency.

This is not a penalty applied after the fact. It is a *definitional* property: unattested compute is not SCE-compliant compute. They are different products.

### 2.3 Formal Definition of η_traceability

η_traceability is not a black box. It is computed as:

```
η_traceability = (number of attested links in τ-chain) / (total links in τ-chain)
                × validity_score(Merkle_proof)
```

Where:
- **Merkle_proof** is the cross-level verification proof from the Fractavolta register
- **validity_score** ∈ {0, 1} — binary: proof either validates or does not

This formulation is specified using the Fractavolta scale tower: each link in the τ-chain corresponds to a level Lᵢ in the governance tower. η_traceability = 1 requires valid attestation at every level, from L₀ (compute node) to L₂ (regional federation). Attestation at L₃ (Mediterranean network) enables cross-border premium certification.

### 2.4 Continuous Flow Attestation

The τ-chain is produced **continuously and automatically**, not on demand. The metering layer emits a trace for every measurement interval — including intervals where energy is drawn from the grid rather than from the renewable source. There is no operator-controlled selection of what to attest.

This design eliminates the retroactive cherry-picking attack (attesting only favorable energy windows after the fact) at the architectural level, not through a timing constraint. An operator cannot certify Sovereign-tier compute from a 100% solar window if the preceding and following windows are unattested: the gap itself is a trace event, produced by the cluster (L₁) observing the absence of L₀ output.

The practical consequence: **η_traceability is computed over the full operational history of a node, not over a selected subset of inferences**. A node that produces complete traces for 95% of its operating time has η_traceability = 0.95, and all its inferences — including those produced during fully solar windows — are certified at the corresponding tier, not Sovereign.

### 2.5 Degraded Mode

Infrastructure components fail. The attestation pipeline must specify behavior under partial failure, and that behavior must not create exploitable gaps.

Three failure cases and their handling:

**Short outage** (seconds to minutes — TEE restart, transient network loss)  
The cluster (L₁) observes the gap in the L₀ trace stream. Inferences produced during the gap are automatically reclassified to the tier below their normal certification, not rejected. The operator loses premium on the affected window; operations continue.

**Long outage** (hours — hardware failure, connectivity loss)  
Tier descends progressively to Opportunistic for the duration. Certification resumes automatically when the trace stream resumes. No manual intervention required; no operator decision point that could be exploited.

**Hardware attestation unavailable** (TEE component failed or absent)  
Software-only fallback attestation is permitted, but η_traceability is hard-capped below the Sovereign threshold regardless of energy provenance. Sovereign certification requires hardware-rooted attestation by definition.

**Anti-gaming requirement:** a voluntary outage (operator deliberately disabling the measurement layer to avoid attesting an unfavorable energy window) must be indistinguishable from an involuntary one from the operator's perspective — both result in the same automatic tier reclassification. The cluster detects the gap; it does not need to determine its cause. The mechanism for distinguishing voluntary from involuntary outages is not yet specified and is flagged as an open problem (see §9).

### 2.4 Two-Layer Interpretation

- **Xc_phys**: physical corrected energy representation — a measurement
- **CXU**: functional unit of verified useful inference capacity — a governed convention

CXU is not energy. It is **conventionalized usable compute under governance rules**. The distinction matters: Xc_phys can be measured; CXU can only be *issued* by an authorized governance layer. This is analogous to the distinction between gold purity (measurable) and a gold coin's legal tender value (governed convention).

---

## 3. CXU (Compute eXergy Unit)

### 3.1 Definition

1 CXU corresponds to a standardized ability to produce a defined number of reference inferences under a fixed SLA and execution environment, with a complete and verified provenance chain from energy source to output token.

The CXU denomination is:

```
CXU = Xc / reference_inference_cost
    = (E × η_hw × η_sys × η_sla × η_traceability) / I_ref
```

where I_ref is the cost of one reference inference (see §3.2).

### 3.2 Reference Inference (v1)

Standardized in `reference_inference_v1.md` (forthcoming):

- **Model**: frozen open-weight reference model (versioned, hash-pinned)
- **Output**: 1,000 tokens
- **Latency constraint**: P95 ≤ 200 ms
- **Execution**: canonical runtime specification (hardware class, batch size, precision)
- **Attestation**: TEE-verified execution with signed output hash

This reference is a **governed convention**, not a physical constant. It will drift as hardware improves. Governance of benchmark updates is specified in §6.

### 3.3 Market Tiers and Premium Structure

The provenance chain enables a premium market that does not currently exist:

| Tier | Use Case | η_traceability requirement | Premium over spot |
|------|----------|---------------------------|-------------------|
| **Sovereign** | Public infrastructure, democratic decision systems | = 1.00 (complete chain) | ×10–×31 |
| **Certified** | Medical, legal, regulated industries | ≥ 0.95 | ×4–×10 |
| **Standard** | General-purpose agentic workloads | ≥ 0.80 | ×1.5–×4 |
| **Opportunistic** | Surplus energy, batch, uncertified | < 0.80 | Spot price |

The premium multipliers are not arbitrary. They reflect:
1. **Legal liability reduction**: certified provenance limits dispute surface
2. **Regulatory compliance**: pre-audit-ready documentation
3. **Carbon credit integration**: verifiable renewable fraction unlocks carbon markets
4. **Sovereignty premium**: compute not subject to foreign jurisdiction interruption

The Sovereign tier (×10–×31 multiplier) is the MareNostrum value proposition. Converting Corsican solar into Sovereign-tier CXU bypasses the SARCO electrical interconnection bottleneck entirely: the value remains on the island in certified token form rather than being exported as undifferentiated electrons.

---

## 4. System Architecture

### 4.1 Pipeline

```
MEASUREMENT → AUDIT → INSURANCE → REGISTER → GOVERNANCE
```

This pipeline maps directly to the Fractavolta scale tower:

| Pipeline Stage | Fractavolta Level | Function |
|---------------|------------------|----------|
| Measurement | L₀ — Compute node | TEE attestation, energy metering, model hash |
| Audit | L₁ — Cluster | Multi-node verification, cross-check |
| Insurance | L₁–L₂ boundary | Collateralization, SLA commitment |
| Register | L₂ — Regional federation | CXU issuance, Merkle root publication |
| Governance | L₃ — Mediterranean network | Democratic arbitration, policy updates |

### 4.2 Components

**Measurement layer**
- Trusted Execution Environment (TEE): Intel TDX or AMD SEV-SNP
- Certified sub-second energy metering at PDU level
- Model hash pinning (prevents substitution after attestation)
- Timestamp anchoring to external time authority

**Audit layer**
- Multi-level verification score ∈ [0.00, 1.00]
- Cross-node consistency checks within cluster
- Anomaly detection (efficiency outliers suggest tampering)

**Insurance layer**
- Collateralization pools: operators post CXU bonds against SLA commitments
- Mutual insurance for regional force majeure (grid failure, extreme weather)
- Parametric triggers: automatic payout on verifiable SLA breach

**Register layer**
- DAG-based distributed ledger with post-quantum cryptography (CRYSTALS-Dilithium)
- Merkle aggregation: L₀ logs → L₁ roots → L₂ roots → L₃ global root
- Immutable: append-only, no erasure
- Public root publication at L₂ and above; private content at L₀

**Governance layer**
- Democratic arbitration: 1 person = 1 voice (see §6)
- Benchmark governance: reference inference updates by supermajority
- Policy revision: upgrade paths for η_traceability formula

### 4.3 Architecture Diagram

```
┌─────────────────────────────────────────────────────────┐
│  L₃  Mediterranean Governance                           │
│       Public root · Democratic arbitration · Policy     │
└───────────────────┬─────────────────────────────────────┘
                    │ Merkle root aggregation
┌───────────────────┴─────────────────────────────────────┐
│  L₂  Island Federation Register                         │
│       CXU issuance · Carbon accounting · PQ signatures  │
└───────────────────┬─────────────────────────────────────┘
                    │ Merkle root aggregation
┌───────────────────┴─────────────────────────────────────┐
│  L₁  Cluster Audit                                      │
│       Multi-node verification · Insurance · SLA check   │
└───────────────────┬─────────────────────────────────────┘
                    │ Signed trace tuples
┌───────────────────┴─────────────────────────────────────┐
│  L₀  Compute Node Measurement                           │
│       TEE · Energy meter · Model hash · Timestamp       │
└─────────────────────────────────────────────────────────┘
```

Privacy property: each level can verify the integrity of the level below via Merkle proof without reading its content. A regulator at L₃ audits energy allocation at L₂ without accessing individual job records at L₀.

---

## 5. The Provenance Chain as Product

This section formalizes the central commercial claim.

### 5.1 What Makes an Inference "Premium"

An inference I is **SCE-certified at tier T** if and only if:
1. A complete τ-chain exists from the energy source to I's output hash
2. Every link τᵢ is validly signed by an authorized actor at the corresponding level Lᵢ
3. The Merkle proof of the τ-chain is verifiable against the published L₂ root
4. η_traceability ≥ threshold(T)

The certification is not a document issued after the fact. It is a **cryptographic property of the inference itself**, derivable from the register at any time by any verifier with access to the public root.

### 5.2 The AOC Analogy — and Its Limits

An Appellation d'Origine Contrôlée (AOC) wine carries provenance guarantees — region, grape variety, production method — certified by a public authority. The analogy holds in structure:

| Wine AOC | SCE Certification |
|----------|-----------------|
| Region of origin | Energy source location and type |
| Grape variety | Hardware class and model version |
| Production method | Runtime specification |
| Certification authority | L₂ governance layer |
| Bottle label | Merkle proof + inference hash |

The limit of the analogy: an AOC label can be forged. A Merkle proof against a public root cannot be forged without computational infeasibility under current cryptography (and post-quantum infeasibility under CRYSTALS-Dilithium). **SCE certification is stronger than any paper certification scheme.**

### 5.3 The Register as Infrastructure for Democratic AI

A certified inference is not merely a premium product. It is a **political artifact**: it proves that a democratic governance layer had visibility into the compute that produced it, at the time it was produced.

This matters for AI systems operating in public decision contexts (benefits allocation, judicial support, medical triage). Unattested AI inference in these contexts is structurally unaccountable — no causal chain from decision to infrastructure exists. SCE-certified inference restores the chain.

The register is therefore not infrastructure *for* democratic governance. It *is* democratic governance, applied to compute.

---

## 6. Governance Layer

### 6.1 Foundational Axiom

> **One person = one voice is the final arbitration mechanism of the system.**

This is not derived from efficiency considerations. It is a normative postulate of sovereignty. The system is designed around this axiom, not despite it.

### 6.2 Separation of Layers

The system explicitly separates three registers of action:

- **Operational layer** (L₀–L₁): automatic execution under pre-defined rules
- **Technical mediation layer** (L₂): auditable expert arbitration
- **Political layer** (L₃): democratic arbitration of contested decisions

Higher layers do not override lower layers in routine operation. They activate only on escalation events — which are themselves traced and attributed.

### 6.3 Governance of the Benchmark

The reference inference I_ref is a governed convention. As hardware improves, a fixed I_ref becomes easier to achieve, inflating CXU supply. The governance layer must:

1. Track the reference inference cost over time
2. Decide by supermajority when to update I_ref
3. Manage the transition (existing CXU denominated in old I_ref remain valid under their issuance rules)

This is structurally identical to a central bank managing a monetary standard. The democratic axiom prevents capture by hardware manufacturers who benefit from benchmark inflation.

### 6.4 Epistemic Humility (Explicitly Accepted)

The system assumes:
- Technical measurements may be incomplete
- Representations may be imperfect
- Governance decisions may diverge from physical optima

This divergence is not a failure condition. It is an accepted property of **democratic closure under uncertainty**. The system guarantees legitimacy of arbitrated outcomes and their revisability — not their technical optimality.

This is **Possibilism** applied to governance — the author's epistemological stance (introduced in [Fractavolta](https://github.com/JeanHuguesRobert/fractavolta)): exploring what is achievable under real constraints, not optimizing toward an idealized but unreachable target.

---

## 7. Sovereign Risk: Exergy Lock Protocol

The Exergy Lock Protocol enables graduated enforcement of sovereignty over compute flows.

Three levels of activation:

1. **Cryptographic suspension**: execution rights are revoked at L₀ — no new jobs can be admitted
2. **Efficiency degradation**: η_sla is administratively reduced — existing jobs complete at lower priority
3. **Workload migration**: jobs are redirected to alternative certified zones within the federation

Activation conditions:
- Predefined (specified at issuance, not decided ad hoc)
- Multi-party verifiable (requires quorum at governance layer)
- Publicly auditable (the activation event is itself a trace)

The protocol prevents both unilateral operator capture and unilateral regulatory capture. Neither side can act without generating a traceable, attributed event visible to all parties.

---

## 8. Integration into MareNostrum

SCE is the compute governance layer of the MareNostrum energy infrastructure.

**Energy infrastructure** (Mediterranean Exergy Charter): 30,000 ha agrivoltaic on Corsican friches viticoles → ~10.8 GWp → ~16 TWh/year net.

**Compute governance** (SCE): surplus energy → CXU issuance at L₂ → Sovereign-tier certified inference.

**Value chain**: instead of exporting undifferentiated electrons via SARCO interconnection (which eliminates location premium), Corsican solar becomes Sovereign-tier CXU — a product worth ×10–×31 more per unit of physical energy than grid electricity export.

The MareNostrum scale tower:

| Level | Territory | CXU Issuance Authority |
|-------|-----------|----------------------|
| L₀ | Individual datacenter node | None (measurement only) |
| L₁ | Cluster (per datacenter) | None (audit only) |
| L₂ | Island federation (Corsica, Sardinia, Sicily) | Yes — regional CXU issuance |
| L₃ | Mediterranean network | Cross-border certification, regulatory interface |

---

## 9. Open Problems

Acknowledged as structural, not blocking:

**Identity and Sybil resistance**: democratic voting requires unique identity without centralized identity registry. Zero-knowledge proofs of unique humanity are a candidate solution; their governance is unresolved.

**Benchmark governance and drift**: I_ref must be updated as hardware evolves. The update mechanism must be resistant to capture by hardware manufacturers. Formal specification pending.

**Oracle problem in inference equivalence**: verifying that a job executed the specified model on the specified input is non-trivial. TEE attestation addresses this partially; full input-output verification requires cryptographic commitments not yet standardized.

**Voluntary outage detection**: the continuous flow model eliminates retroactive cherry-picking but introduces a different attack surface — an operator deliberately disabling the measurement layer during an unfavorable energy window. Both voluntary and involuntary outages result in the same automatic tier reclassification, which limits the financial incentive. A mechanism to distinguish them would strengthen the integrity guarantee. Candidate approaches: cross-node consistency checks within the cluster (genuine infrastructure failures should show correlated patterns across neighboring nodes), and bonded uptime commitments (operators post collateral against measurement continuity, not just SLA). Not yet specified.

**GDPR tension**: append-only logs conflict with the right to erasure. Pseudonymization at L₀ after retention period is a partial mitigation that weakens non-repudiation. Legal design required in parallel with technical design.

**Sybil-resistant democratic governance at L₃**: a Mediterranean network spanning multiple jurisdictions cannot rely on any single state's identity infrastructure. This is the hardest open problem.

---

## 10. What Would Falsify the Core Claim

The claim that "the attestation chain is the product" fails if:

- A market for unattested inference develops that captures the premium (requires regulatory capture or persistent greenwashing tolerance — possible but not inevitable)
- TEE attestation is broken (known research direction; post-quantum migration is the hedge)
- η_traceability can be gamed by selective attestation of favorable steps while omitting unfavorable ones (the conjunctive property prevents this by design; an attacker must forge a complete chain, not just favorable links)
- Democratic governance of the benchmark is captured, allowing systematic CXU inflation (the Sybil resistance problem — unresolved)

---

## Appendix A — Glossary

| Term | Definition |
|------|-----------|
| **CXU** | Compute eXergy Unit: conventionalized unit of verified useful compute under SLA and governance |
| **Xc** | Compute exergy: efficiency- and provenance-adjusted physical compute potential |
| **η_traceability** | Provenance completeness coefficient: fraction of τ-chain that is cryptographically attested; collapses CXU to 0 if 0 |
| **τ-chain** | Ordered sequence of signed trace tuples from energy source to inference output |
| **I_ref** | Reference inference: governed standard unit for CXU denomination |
| **Exergy Lock Protocol** | Graduated cryptographic enforcement of compute sovereignty |
| **SCE** | Safe Compute Exergy: the socio-technical system as a whole |
| **Sovereign tier** | Highest certification tier: complete τ-chain, η_traceability = 1.00 |

---

## Appendix B — Relation to Fractavolta

Fractavolta defines the architectural principle; SCE defines the application.

| Fractavolta concept | SCE instantiation |
|--------------------|------------------|
| Scale tower (L₀–Lₙ) | Node → Cluster → Island → Mediterranean |
| Governance function G | CXU issuance rules + I_ref governance |
| φ-invariance | Same audit interface at every level |
| Trace tuple τ | Energy metering event → compute event → inference event |
| Merkle aggregation | L₀ logs → L₂ public root |
| η_traceability | Computed from Merkle proof completeness across levels |
| Democratic dividend | Same audit tools for local community (L₁) and Brussels regulator (L₃) |

The dependency is explicit: **SCE requires Fractavolta**. A CXU without a Fractavolta-compliant register is a claim without a proof.

---

*Living document — iterative public versions maintained in the MareNostrum repository.*  
*Priority established by first commit timestamp. Challenge via issues.*  
*License: CC BY-SA 4.0*


<!-- BEGIN_AUTO: backlinks -->
### Backlinks

*These documents link to this file:*
- [Corpus Status — marenostrum](research/corpus-status.md)
- [Research Index — MareNostrum](research/index.md)

<!-- END_AUTO: backlinks -->

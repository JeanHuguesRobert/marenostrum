---
canonical_url: https://github.com/JeanHuguesRobert/marenostrum/blob/main/CXU_SPEC.md
last_stamped_at: 2026-05-15
---
# CXU_SPEC — Compute eXergy Unit Specification

**Version**: 0.1 (Draft)

**Status**: Open for comment

**Repository**: `github.com/JeanHuguesRobert/marenostrum`

**License**: CC BY-SA 4.0

**Contact**: jhr@baronsmariani.org

**Last revised**: May 2026

> *Companion specification to DHITL.md — "Democratic Humans in the Loop:*
> *Why Infrastructure Is All You Need for AI Safety"*

---

## 1. Purpose

This document specifies the **Compute eXergy Unit (CXU)** as a standalone,
referenceable artifact. It is intended for use by:

- **Regulators** seeking a physically grounded unit of account for AI compute
  governance (alternative or complement to raw FLOP-count thresholds)
- **Insurers and auditors** pricing governance risk in AI infrastructure
- **Compute providers** seeking a certification pathway that produces market
  premiums
- **Democratic governance bodies** needing a measurable quantity to oversee
- **Researchers** extending or critiquing the Compute Exergy framework

The CXU is defined in DHITL.md (Section 4); this document expands that
definition into an operationalizable specification. In case of conflict,
DHITL.md governs.

---

## 2. Background: Why a New Unit?

Existing metrics for AI compute governance are inadequate in one or more of the
following respects:

| Metric | Physically grounded | Quality-adjusted | Traceable | Governance-aware |
|---|---|---|---|---|
| FLOP count | ✓ | ✗ | ✗ | ✗ |
| GPU-hour | Partial | ✗ | ✗ | ✗ |
| Dollar cost | ✗ | Partial | ✗ | ✗ |
| kWh | ✓ | ✗ | ✗ | ✗ |
| **CXU** | **✓** | **✓** | **✓** | **✓** |

Legislative thresholds (EU AI Act Article 51: 10²⁵ FLOP; California SB 53:
10²⁶ FLOP) measure raw compute. They create disclosure obligations toward
regulators but not democratic accountability toward affected populations. The
CXU is designed to make the latter tractable.

---

## 3. Core Formula

```
Xc = E × η_hw × η_sys × η_sla × η_gov
```

where all η factors ∈ [0, 1].

| Symbol | Name | Unit | Description |
|---|---|---|---|
| `E` | Available energy | kWh | Electrical energy consumed, contextualized by location, time, and source mix |
| `η_hw` | Hardware efficiency | dimensionless | Useful FLOP per joule, adjusted for model architecture, precision, and quantization |
| `η_sys` | System efficiency | dimensionless | Inverse PUE × network overhead × orchestration loss |
| `η_sla` | Service quality factor | dimensionless | Latency guarantees, uptime, priority tier |
| `η_gov` | Governance quality factor | dimensionless | Traceability, democratic accountability, third-party safety certification |

### 3.1 The Nullity Condition

> **If η_gov = 0, then Xc = 0, regardless of the values of all other factors.**

Compute that is not traceable and not democratically accountable produces zero
Exergy in the DHITL framework. This is the formal expression of:

> *"An unattributable act is legally void."*
> — Charte du Soleil Méditerranéen, 2026, Article 7

This condition is the principal structural difference between Compute Exergy and
all purely physical or financial compute metrics.

---

## 4. Reference Workload

**1 CXU** is defined as the certified capacity to produce the following
standardized inference workload:

> **1,000 output tokens** from a reference open-weights model
> (baseline: Llama 3 70B, FP16 precision),
> at **≤ 200 ms P95 latency**,
> under a defined and audited service level agreement.

### 4.1 Rationale for this reference

- Open-weights model: reproducible by any third-party auditor without licensing
  constraints
- 70B parameter scale: representative of frontier-adjacent inference cost as of
  2025–2026; intended to be revised as hardware and model efficiency evolve
- FP16 precision: widely supported, well-characterized energy profile
- 200 ms P95: conservative interactive-grade latency; excludes batch-only or
  asynchronous workloads from the reference

### 4.2 Revision cadence

The reference workload is subject to revision by the governance body (see
Section 8) no more frequently than once every 6 months. Revision proposals
require 30 days of open comment before ratification. Adjustment factors bridging
old and new reference workloads are published simultaneously with any revision,
so that existing CXU-denominated contracts remain denominated in the version
at time of issuance.

---

## 5. Factor Measurement Guidance

### 5.1 Hardware Efficiency (η_hw)

η_hw is normalized against the reference workload on reference hardware:

```
η_hw = (FLOP_useful / FLOP_total) × (FLOP_ref / energy_ref) / (FLOP_actual / energy_actual)
```

Self-reported η_hw values require third-party attestation at certification
levels ≥ Compliant. The table below covers common configurations; unlisted
hardware requires a benchmarked measurement submission to the governance body.

| Hardware class | Model config | η_hw | Notes |
|---|---|---|---|
| Legacy datacenter GPU (V100, A100 pre-opt) | FP16, no quantization | 0.30 – 0.40 | Baseline; common in co-lo |
| A100 / H100, standard config | FP16, standard batching | 0.50 – 0.60 | Widely deployed frontier config |
| H100 / H200, optimized | FP8, flash-attention, continuous batching | 0.70 – 0.80 | Current best-practice deployment |
| TPU v4 / v5, Google Cloud | bfloat16, XLA-optimized | 0.75 – 0.85 | Vendor-specific; requires Google attestation |
| Custom silicon (Trainium 2, Gaudi 3, MI300X) | Vendor-optimized | 0.65 – 0.85 | Benchmark submission required |
| Edge / mobile inference (NPU, embedded) | INT8 / INT4 | 0.40 – 0.60 | High variability; model-dependent |
| Sovereign / community hardware (open-source accelerator designs) | FP16 reference | 0.35 – 0.55 | Auditable by design; η_gov uplift eligible |

This table is maintained in-spec and revised on the 6-month cadence (Section
4.2). Hardware generation changes causing >15% drift in any row trigger an
off-cycle revision proposal.

### 5.2 System Efficiency (η_sys)

```
η_sys = (1 / PUE) × (1 - network_overhead) × (1 - orchestration_loss)
```

- **PUE** (Power Usage Effectiveness): measured at the datacenter level,
  trailing 12-month average. Green Datacenter standard: PUE ≤ 1.2.
- **Network overhead**: fraction of total energy attributable to data transport
  not directly serving the inference workload
- **Orchestration loss**: scheduling inefficiency, idle GPU cycles, failed jobs

**Typical range**: 0.40 (legacy co-lo, poor scheduling) to 0.85 (purpose-built
green datacenter, optimized orchestration)

### 5.3 Service Quality Factor (η_sla)

η_sla reflects the contractual and empirical quality of the service level
agreement under which compute is delivered.

| SLA Tier | η_sla | Conditions |
|---|---|---|
| No SLA | 0.10 | Best-effort, no uptime guarantee |
| Basic | 0.40 | 95% uptime, no latency guarantee |
| Standard | 0.65 | 99% uptime, P95 latency target defined |
| Enhanced | 0.80 | 99.5% uptime, P95 ≤ 200 ms, SLA penalties enforced |
| Sovereign | 1.00 | 99.9% uptime, P99 ≤ 200 ms, full SLA enforcement + priority recovery |

### 5.4 Governance Quality Factor (η_gov)

η_gov is the factor that makes Compute Exergy a governance instrument rather
than merely a physical metric.

| Level | η_gov | Label | Conditions |
|---|---|---|---|
| 0 | 0.00 | Uncertified | No audit, no traceability, no declaration |
| 1 | 0.25 | Self-declared | Public declaration + ex-post random audit (≥10% of CXU issuances per quarter) |
| 2 | 0.50 | Compliant | Annual third-party audit; compliance with applicable AI regulation (EU AI Act, SB53, or equivalent) |
| 3 | 0.75 | Verified | Continuous audit + red-teaming; mandatory incident reporting within 72 hours |
| 4 | 1.00 | Frontier-certified | Level 3 + independent safety evaluation (METR or equivalent); full public compute registry participation |

**Certification is additive downward**: a Verified (Level 3) provider meets all
conditions of Compliant (Level 2) and Self-declared (Level 1). A gap in any
lower-level condition degrades the certification to the level below.

**Certification is jurisdictional**: η_gov is assessed per jurisdiction. A
provider certified at Level 4 in the EU but operating uncertified infrastructure
in a third country issues CXU at Level 0 for the uncertified fraction.

### 5.5 Audit Frequency Model

Audit frequency is tiered by workload temperature and randomized to resist
gaming:

| Workload class | Definition | Base audit frequency | Random uplift |
|---|---|---|---|
| **Hot** | Active inference serving; η_sla ≥ Enhanced; issuance > 1,000 CXU/day | Continuous (automated telemetry) | +spot audit, random daily draw, p=0.05 |
| **Warm** | Batch / training workloads; issuance 100–1,000 CXU/day | Weekly automated check | +full audit, random weekly draw, p=0.10 |
| **Cold** | Idle / reserved capacity; issuance < 100 CXU/day | Monthly summary report | +deep audit, random monthly draw, p=0.20 |

**Automation principle**: continuous telemetry (hot) and weekly checks (warm)
are fully automated — latency, uptime, energy metering, and governance flags are
pulled from provider APIs without human intervention. Full and deep audits
require a human auditor to review flagged anomalies. The random uplift
probability is intentionally higher for cold workloads: lower base frequency
creates a larger gaming surface.

**Anomaly triggers** (any class): an automatic full audit is triggered when:
- Energy consumption deviates > 20% from declared profile for > 6 hours
- Latency P95 exceeds SLA threshold for > 1% of requests in any 24-hour window
- Governance flag raised by any registered observer in the compute registry

---

## 6. CXU Variants

| Variant | Symbol | Description |
|---|---|---|
| Uncertified | CXU-U | η_gov = 0.00; Xc = 0 by nullity condition; issued for accounting purposes only, not for democratic oversight purposes |
| Assured | CXU-A | η_gov ≥ 0.50 (Compliant or above) |
| Verified | CXU-V | η_gov ≥ 0.75 |
| Frontier | CXU-F | η_gov = 1.00 |

**The CXU-A/CXU-U spread** is a market price for governance risk. A wide spread
signals high demand for accountability assurance. A narrow spread signals either
regulatory capture (no premium for governance) or near-universal certification
(governance saturation). Both extremes warrant governance body review.

---

## 7. Compute Exergy Concentration Index (CECI)

The CECI measures structural concentration of certified compute in a given
jurisdiction and period. It is the Herfindahl-Hirschman Index (HHI) applied to
the distribution of CXU-A issuances:

```
CECI_T = Σ_i ( Xc_i / Xc_total )²
```

where `Xc_i` is the Compute Exergy (Assured or above) attributable to actor `i`
in period `T`.

| CECI Value | Status | Required Response |
|---|---|---|
| < 0.10 | Unconcentrated | No governance action required |
| 0.10 – 0.25 | Moderately concentrated | Monitoring; disclosure of top-5 actors |
| 0.25 – 0.40 | Concentrated (warning) | Mandatory review by governance body within 90 days |
| > 0.40 | Highly concentrated (instability) | Emergency governance response; automatic review of largest actor's certification |

These thresholds are analogous to antitrust HHI thresholds (DOJ/FTC merger
guidelines: 0.15 moderate, 0.25 highly concentrated), adapted for the specific
risk profile of AI infrastructure concentration.

**Single-actor cap**: any actor holding > 20% of total CXU-A in a jurisdiction
triggers a S5 warning condition (DHITL Section 7.2) regardless of the CECI
value.

---

## 8. Governance of This Specification

### 8.1 Current status

This specification is in draft (v0.1). It is published in the open to invite
comment, critique, and parallel implementation proposals.

### 8.2 Intended governance body

The CXU specification is intended to be governed by a body with the following
properties:
- **Open membership**: any affected party may participate in revision processes
- **1p1v decision-making**: revisions approved by one-person-one-vote among
  registered participants, not by stake-weighted voting
- **Public record**: all revision discussions and votes are publicly archived
- **Conflict of interest disclosure**: participants must disclose economic
  interests in CXU markets before voting on specification changes

The Institut Mariani (Corte, Corsica) serves as provisional custodian pending
establishment of the formal governance body.

### 8.3 How to comment

Open an issue at `github.com/JeanHuguesRobert/marenostrum` with the label
`CXU-SPEC`. Pull requests against this file are welcome. Substantive objections
to the framework — especially to the nullity condition, the reference workload
definition, or the η_gov level thresholds — are particularly invited.

---

## 9. What the CXU Is Not

| It is not… | Because… |
|---|---|
| A proof-of-work token | It certifies compute that would have occurred anyway; it does not consume energy to generate itself |
| A stablecoin | Its value is anchored to the marginal cost of certified compute, not to a fiat currency |
| A software license | It certifies infrastructure, not model weights |
| A speculative instrument | Issuance requires physical measurement attestation |
| A replacement for regulation | It is a unit of account for democratic oversight, not a substitute for legislative authority |
| A proprietary standard | It is published under CC BY-SA 4.0 and governed by open processes |

---

## 10. Relationship to Existing Frameworks

| Framework | Relationship to CXU |
|---|---|
| EU AI Act (Article 51, 10²⁵ FLOP threshold) | CXU complements: FLOP thresholds measure quantity; CXU measures quality + governance. A CXU-denominated threshold captures more of what matters for safety. |
| California SB 53 (10²⁶ FLOP) | Same as EU AI Act. CXU thresholds could be expressed as CECI bounds rather than absolute FLOP counts. |
| NIST AI RMF | CXU provides a physical-economic grounding for the "Govern" function of the RMF. |
| ISO/IEC 42001 | η_gov Level 2 (Compliant) is compatible with 42001 certification as a necessary but not sufficient condition. |
| GreenAlgorithms / ML CO₂ Impact | CXU's η_sys and η_hw factors capture similar concerns; CXU adds the governance dimension and the democratic accountability layer. |

---

## 11. Open Problems

The following are explicitly unresolved in this specification. Contributions are
invited.

1. **η_gov audit protocol**: a detailed audit checklist for each certification
   level, specifying what evidence is required and how it is assessed
2. **Reference workload versioning**: a mechanism for updating the reference
   workload without breaking existing CXU-denominated contracts (conversion
   factors between versions)
3. **Multi-jurisdictional compute**: how to assign η_gov when a single inference
   workload crosses jurisdictional boundaries (e.g., training in the EU,
   inference in the US)
4. **Small provider pathway**: a lightweight certification track for compute
   providers below a materiality threshold, to avoid regulatory moat effects
5. **CXU and energy certificates**: relationship between CXU issuances and
   existing renewable energy certificate (REC/REGO) frameworks
6. **Audit API standard**: a common provider API schema for automated telemetry
   ingestion (hot/warm workloads), so that continuous auditing does not require
   bespoke integrations per provider

---

## Appendix: Worked Example

**Scenario**: A Mediterranean solar datacenter in Corte, Corsica, running
sovereign AI inference for a federated democratic governance platform.

| Factor | Value | Notes |
|---|---|---|
| E | 1,000 kWh | Measured at the meter; 100% solar PV, on-site |
| η_hw | 0.75 | Modern GPU cluster, FP16, optimized for reference model |
| η_sys | 0.80 | PUE = 1.15 (Mediterranean passive cooling), low network overhead |
| η_sla | 0.80 | Enhanced tier: 99.5% uptime, P95 ≤ 200 ms |
| η_gov | 0.75 | Verified (Level 3): continuous audit, 72-hour incident reporting |

```
Xc = 1,000 × 0.75 × 0.80 × 0.80 × 0.75
   = 1,000 × 0.360
   = 360 CXU-V
```

This 360 CXU-V production from 1,000 kWh represents approximately 360,000
reference inference calls (1,000 tokens at P95 ≤ 200 ms), fully traceable,
democratically accountable, and insurable at the Verified tier premium.

**Counterfactual** (same hardware, same energy, η_gov = 0):
```
Xc = 1,000 × 0.75 × 0.80 × 0.80 × 0.00 = 0 CXU
```
The compute occurs physically but produces no Exergy in the DHITL framework.
It is not counted toward democratic oversight capacity.

---

---

## Appendix: Audit API — Very Early Draft

> **Status**: Exploratory sketch. Not normative. Shared to invite critique and
> parallel proposals. Everything here may change.

The hot/warm audit tiers (Section 5.5) require automated telemetry ingestion.
Without a common schema, "continuous audit" means trusting each provider's own
dashboard — which defeats the purpose. This appendix sketches the minimum
surface a provider would need to expose.

### A.1 Design principles

- **Pull, not push**: the audit system polls providers; providers do not push to
  a central authority. Reduces single point of capture.
- **Minimal surface**: only the fields required to compute Xc and detect
  anomalies. No operational data that could constitute competitive intelligence.
- **Signed responses**: every response is signed by the provider's registered
  keypair. Unsigned or unverifiable responses are treated as η_gov = 0.
- **Open implementation**: a reference implementation will be maintained in
  this repository. Providers may use it or implement the schema independently.

### A.2 Endpoints (sketch)

```
GET /cxu/identity
GET /cxu/telemetry?from=<ISO8601>&to=<ISO8601>
GET /cxu/sla/current
GET /cxu/governance/attestation
```

#### `/cxu/identity`

```json
{
  "provider_id": "<registered UUID in compute registry>",
  "jurisdiction": "FR-COR",
  "certification_level": 3,
  "pubkey": "<ed25519 public key, base64>",
  "spec_version": "0.1"
}
```

#### `/cxu/telemetry`

Covers a requested time window. Granularity: 1-hour buckets for warm, 5-minute
for hot.

```json
{
  "provider_id": "...",
  "period": { "from": "2026-05-01T00:00Z", "to": "2026-05-01T01:00Z" },
  "buckets": [
    {
      "t": "2026-05-01T00:00Z",
      "energy_kwh": 12.4,
      "eta_hw": 0.75,
      "eta_sys": 0.81,
      "pue": 1.15,
      "tokens_served": 842000,
      "p95_latency_ms": 187,
      "uptime_fraction": 1.0
    }
  ],
  "signature": "<base64 signature over canonical JSON of buckets>"
}
```

#### `/cxu/sla/current`

```json
{
  "tier": "enhanced",
  "eta_sla": 0.80,
  "uptime_target": 0.995,
  "p95_latency_ms_target": 200,
  "valid_until": "2026-12-31"
}
```

#### `/cxu/governance/attestation`

```json
{
  "certification_level": 3,
  "last_audit_date": "2026-03-15",
  "next_audit_due": "2026-09-15",
  "auditor": "TÜV SÜD / CXU-accredited",
  "incidents_last_90d": 0,
  "registry_url": "https://cxu-registry.example/providers/<uuid>",
  "signature": "..."
}
```

### A.3 Anomaly detection (sketch)

The audit client computes expected Xc from telemetry and compares to declared
issuances. Triggers a full audit if:

```
| Xc_measured - Xc_declared | / Xc_declared > 0.20
```

over any 24-hour window. The 20% threshold is provisional — tighter for
Frontier-certified providers (suggested: 10%), looser for Self-declared (30%).

### A.4 What is deliberately out of scope here

- Authentication and provider registration flow
- The compute registry schema
- Dispute resolution when a provider contests an anomaly flag
- Privacy-preserving audit techniques (for providers handling sensitive workloads)

These belong in subsequent drafts, after the basic telemetry schema stabilises.

---

*Compute eXergy Unit Specification v0.1*

*Institut Mariani R&D — 1 cours Paoli, F-20250 Corte, Corsica*

*Published under CC BY-SA 4.0*

*`github.com/JeanHuguesRobert/marenostrum`*

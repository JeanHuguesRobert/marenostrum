**Title:** From Photons to Inferences: Why AI Safety Needs Compute Exergy and Deliberate Topology Choices

**TL;DR:**  
The deepest AI safety problem is not inside the models — it is the physical infrastructure that runs them. I propose **Safe Compute Exergy (SCE)**, a traceable unit that measures *useful* compute (energy contextualized by efficiency, SLA and governance). I also compare **orbital** vs **terrestrial** compute topologies and argue that we should consciously choose (and hybridize) them. This is the practical implementation of the conjecture that “AI Safety Is Primarily an Infrastructure Problem.”

---

### The Core Claim

Most AI safety research focuses on models, evaluations, or international treaties. These are necessary but increasingly insufficient. As frontier training and inference become extremely energy-intensive, the **physical substrate and its governance** will dominate long-term safety outcomes.

Energy is now the real bottleneck. Orbital compute proposals are gaining traction. We need to think seriously about *how* we build the infrastructure, not just *how much* we build.

### Safe Compute Exergy (SCE) — A New Primitive

**Compute exergy** is the thermodynamic-inspired concept of measuring not raw joules or raw FLOP, but the fraction of resources that can actually be converted into useful inferences under real constraints.

Operational formula:
\[
X_c = E \times \eta_{hw} \times \eta_{sys} \times \eta_{sla} \times \eta_{traceability}
\]

The atomic unit is the **CXU** (Compute eXergy Unit): a guaranteed, auditable, insurable capacity to deliver standardized inferences with explicit SLA tiers (Critical / Standard / Spot).

Key mechanisms:
- Physical anchoring (TEE + certified power metering + attestation)
- Exergy Lock Protocol (graduated cryptographic and performance degradation under coercion)
- Democratic governance layer (1 person = 1 voice with imperative mandates)
- Built-in funding for independent AI safety research (0.1% of issuance)

Full specification: [safe-compute-exergy-cdc.md](https://github.com/JeanHuguesRobert/marenostrum/blob/main/safe-compute-exergy-cdc.md)

### Compute Topologies Matter More Than We Admit

I recently wrote a comparative analysis of two emerging paradigms:

- **Orbital topology** (SpaceX / Starship-enabled data centers, massive solar access, low gravity cooling)
- **Terrestrial / Mediterranean topology** (localized renewable energy + fiber interconnects + regional governance)

Full paper: [infrastructure_topologies_for_compute_sovereignty.md](https://github.com/JeanHuguesRobert/marenostrum/blob/main/infrastructure_topologies_for_compute_sovereignty.md)

**Summary of trade-offs**:
- Orbital wins heavily on raw scale, solar abundance, and potentially lower marginal energy cost.
- Terrestrial wins on exergy measurability, lower latency for many use cases, democratic accountability, and credible resistance mechanisms (Exergy Lock is far more practical on the ground).
- Both have serious sovereignty risks: orbital creates extreme dependency on launch providers and space jurisdiction; terrestrial risks fragmentation and slower scaling.

We should not let one topology win by default. Deliberate design and hybridization are possible and necessary.

### Democratic Humans in the Loop (DHIL)

Technical alignment alone cannot solve infrastructure-level power concentration. DHIL proposes keeping real humans meaningfully involved in the **governance** of the physical compute layer.

Full document: [DHIL.md](https://github.com/JeanHuguesRobert/marenostrum/blob/main/DHIL.md)

### Current State of the Project

We now have a coherent triptych:
- Foundational conjecture (`infrastructure_is_all_you_need.md`)
- Operational mechanism (`safe-compute-exergy-cdc.md`)
- Comparative topology analysis (`infrastructure_topologies_for_compute_sovereignty.md`)

Open discussion thread: [Issue #1](https://github.com/JeanHuguesRobert/marenostrum/issues/1)

### Seeking Sharp Feedback

I am especially looking for critique on:
- Is the SCE model (exergy + CXU + Exergy Lock) technically and economically credible, or does it introduce too much overhead?
- Does the orbital vs terrestrial comparison miss critical factors (economics, geopolitics, timelines)?
- Is “1 person = 1 voice” at the infrastructure governance level a viable safety mechanism, or does it create unacceptable friction in a fast-moving arms race?
- How should we think about hybrid orbital-terrestrial architectures?

### Why This Matters Now

The energy/compute discussion is reaching a fever pitch. Major players are making multi-hundred-billion-dollar bets on infrastructure. The choices we make (or fail to make) in the next 12–24 months will be very hard to reverse.

If infrastructure is indeed the dominant safety lever, then we should treat it with the same seriousness we treat alignment techniques.

---

**Repository**: https://github.com/JeanHuguesRobert/marenostrum  
All documents are living and open for contribution.

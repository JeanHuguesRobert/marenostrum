# AI Safety Is Primarily an Infrastructure Problem (Conjecture)

*Cross-posted from the MareNostrum working paper series. Full paper: [github.com/JeanHuguesRobert/marenostrum](https://github.com/JeanHuguesRobert/marenostrum)*

---

## 1. The Claim

Model-level alignment work is necessary but insufficient. The binding constraint on AI safety at deployment scale is not the model — it is the **opacity of the infrastructure through which models run**.

A perfectly aligned model on opaque infrastructure is less safe than a moderately aligned model on transparent, auditable, democratically governed infrastructure. This is because the primary vector of AI harm in deployed systems is not misalignment *per se*, but **undetectable computation at scale**.

Corollary: infrastructure governance is a necessary precondition for alignment governance to be meaningful. Without it, all alignment policies are contingent on the goodwill of compute owners.

---

## 2. The Model

Three layers, each necessary, none sufficient:

**Layer 1 — Physical substrate**: computation is grounded in territorial energy production (solar exergy). Every inference is linked to an energy event, a physical location, a governance jurisdiction. This makes "who is running what, on what resources" answerable by construction.

**Layer 2 — Democratic governance**: nested assemblies with imperative, revocable mandates govern the infrastructure. Open-source software is a non-negotiable structural invariant — not a policy that can be overridden, but a constitutional constraint. This makes capture costly and visible.

**Layer 3 — Auditable inference registry**: every inference request is logged to a tamper-evident ledger. Not content surveillance — structural impossibility of *unregistered* computation at scale. Harmful outputs cannot be deployed undetectably.

The proposed safety property: **opacity elimination**. Not alignment by intent, but unobservability made architecturally impossible.

---

## 3. What This Predicts

If the conjecture is correct, the following should be observable:

- **P1**: Systems with mandatory inference registries will exhibit measurably lower rates of large-scale harmful deployment than equivalent systems without registries, controlling for model capability.
- **P2**: Governance capture attempts in systems with imperative/revocable mandates will be detectably slower and more visible than in systems with representative delegation, measurable as time-to-detection of policy deviation.
- **P3**: The marginal safety return of model-level alignment work decreases as infrastructure opacity increases — i.e., alignment improvements on opaque infrastructure produce smaller observed safety gains than the same improvements on transparent infrastructure.

These are testable. I do not currently have the data to test them. That is part of why I am posting this.

---

## 4. Failure Modes (Explicit)

I expect this architecture to fail or underperform under the following conditions:

**F1 — Shadow compute**: actors route inference through unregistered infrastructure in non-participating jurisdictions. The registry is only as complete as its territorial coverage. Partial adoption may produce a false sense of security worse than no registry at all.

**F2 — Oracle capture**: IoT sensors and energy metering hardware (the physical grounding of Layer 1) are themselves vulnerable to compromise. A corrupted energy certificate breaks material traceability at the root.

**F3 — Delegate collusion**: imperative mandate systems assume constituents can evaluate delegate behavior. If the subject matter (AI infrastructure governance) is sufficiently technical, informed revocation becomes practically impossible — reproducing the expert capture problem in a democratic wrapper.

**F4 — GPU dependency**: the physical substrate layer assumes territorial renewable energy, but the compute layer currently depends on GPU supply chains that are globally concentrated (TSMC, NVIDIA). Energy sovereignty without semiconductor sovereignty is partial sovereignty.

**F5 — Fragmentation cost**: a federated system of democratic compute cooperatives may be too slow and too fragmented to respond to rapidly evolving model capabilities. The antifragility argument addresses this partially — structural constraints don't require deliberative response — but I am not confident this fully resolves the speed asymmetry.

**F6 — Economic non-viability**: the model assumes compute token export (via fiber) generates sufficient surplus to sustain governance infrastructure. This is modeled but not empirically validated.

---

## 5. Open Questions

- What is the minimum viable territorial scale for an inference registry to be meaningful rather than trivially circumventable?
- Can formal game-theoretic analysis bound the capture resistance of imperative mandate governance under adversarial conditions?
- Is there a metric for "governance opacity" of AI inference that could ground P1 empirically?
- How does this interact with the EU AI Act's conformity assessment regime? Does mandatory registration complement or duplicate existing obligations?

---

## 6. Call for Critique

I am specifically looking for:

- **Steelmanned versions of F1–F6** that I have underestimated
- **Additional failure modes** I have not considered
- **Prior work** on compute governance as a safety variable — I am aware of GovAI (Oxford) and CSET (Georgetown) outputs; pointers to closer work welcome
- **Objections to the falsifiability** of P1–P3 — if these predictions are not actually testable, I want to know before I invest further in this direction

A prototype deployment (100–1000 participants, single cooperative, simplified registry, Mediterranean solar territory) is under consideration as an empirical testbed. Methodological input on experimental design would be particularly valuable.

---

*Jean Hugues Noël Robert, baron Mariani — Institut Mariani R&D / C.O.R.S.I.C.A.*  
*Full working paper and MareNostrum governance documents: [github.com/JeanHuguesRobert/marenostrum](https://github.com/JeanHuguesRobert/marenostrum)*

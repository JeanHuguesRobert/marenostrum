---
canonical_url: https://github.com/JeanHuguesRobert/marenostrum/blob/main/infrastructure_is_all_you_need.md
last_stamped_at: 2026-05-13
---
# Infrastructure Is All You Need
## Toward a Structural Theory of AI Safety Grounded in Compute Sovereignty and Democratic Energy Governance

**Jean Hugues Noël Robert, baron Mariani**  
Institut Mariani — C.O.R.S.I.C.A. (Association loi 1901, est. 1995)  
1 cours Paoli, F-20250 Corte, Corsica, France  
<jhr@baronsmariani.org> · <institutmariani@gmail.com>  

*Submitted under the auspices of C.O.R.S.I.C.A.*  
*Draft for discussion — MareNostrum Working Paper Series*  
*March 2026*

---

> *"The safety of a complex system does not reside in the intentions of its agents, but in the structural constraints of its substrate."*

---

## Abstract

The dominant paradigm in AI safety research locates risk at the model layer — in weights, training objectives, reward functions, and emergent capabilities. This paper argues that this focus, while necessary, is structurally incomplete. The conditions of possibility for model-level safety are determined upstream, at the level of compute infrastructure: who owns it, who governs it, and under what constraints its outputs can be traced, audited, and disputed. Drawing on the MareNostrum framework — a proposed Mediterranean-scale energy and compute sovereignty architecture — we articulate a three-layer model in which physical substrate (solar exergy), democratic governance (fractal, imperative-mandate assemblies), and cognitive contracts (auditable, open-source inference registries) form an integrated, antifragile safety system. We argue that structural transparency, enforced at the infrastructure level, achieves what model-level alignment cannot: it makes opacity — the primary vector of AI risk — architecturally impossible rather than merely discouraged. The Mediterranean basin, with its exceptional solar endowment and existing cross-border governance traditions, is proposed as a viable empirical testbed for this hypothesis.

**Keywords:** AI safety, compute governance, energy sovereignty, antifragility, radical transparency, democratic infrastructure, Mediterranean cooperation, MareNostrum

---

## 1. The Incomplete Safety Paradigm

The field of AI safety has made remarkable progress in identifying and formalizing risks at the model layer. Techniques including reinforcement learning from human feedback (RLHF), constitutional AI, mechanistic interpretability, and scalable oversight have expanded our ability to characterize and partially constrain model behavior (Bai et al., 2022; Anthropic, 2023; Ngo et al., 2022). The question this paper poses is not whether these efforts are valuable — they are — but whether they are *sufficient* as a foundation for AI safety at civilizational scale.

We submit that they are not, for a reason that is structural rather than technical: **model-level safety interventions are only as robust as the infrastructure through which models are deployed**. A perfectly aligned model running on opaque, unaccountable infrastructure provides weaker safety guarantees than a moderately aligned model embedded in a transparent, democratically governed compute substrate. This is because the principal locus of AI risk in deployed systems is not misalignment *per se*, but **unobservability** — the inability of affected parties to know what is being computed, on whose behalf, with what data, and toward what end.

This gap in the safety literature mirrors a gap that appeared in cryptography before the public-key revolution: security was sought in the complexity of ciphers rather than in the verifiable properties of the system as a whole. The Vazirani-Diffie-Hellman insight was not a better cipher, but a better *architecture*. We argue that AI safety requires an analogous architectural turn.

---

## 2. The Infrastructure Layer: A Missing Variable

### 2.1 Compute as a Structural Determinant

The concentration of frontier AI compute in a small number of private entities is well-documented (Sevilla et al., 2022; Epoch AI, 2024). What is less discussed is the *safety implication* of this concentration: it means that the structural conditions of AI deployment — who can run what, at what scale, under what audit regime — are determined by actors whose incentives are not necessarily aligned with broad societal welfare. Regulatory intervention can partially address this, but regulation that does not reach the physical substrate of computation remains fragile: it can be circumvented by jurisdictional arbitrage, corporate restructuring, or simple opacity.

We propose that meaningful AI safety governance must include what we term **compute sovereignty** — the capacity of a defined political community to set binding structural conditions on the AI inference and training that affects it. This is analogous to, and in our framework directly coupled with, energy sovereignty: the capacity to set conditions on the energy systems that power computation.

### 2.2 From Attention to Exergy

The landmark paper "Attention Is All You Need" (Vaswani et al., 2017) demonstrated that a single architectural insight — the universal sufficiency of the attention mechanism — could reorganize an entire research field. The insight was not incremental; it was *constitutive*. It changed what the field was building toward.

We propose an analogous constitutive reorientation for AI safety: **infrastructure is all you need**. The claim is not that infrastructure replaces model-level safety work, but that without a governed, transparent, physically-grounded compute substrate, model-level safety is building on sand. The structural question — *who controls the conditions of computation* — precedes and constrains every downstream safety question.

The physical grounding of this claim is non-trivial. Computation requires energy. Energy in the Mediterranean basin is, in the relevant time horizon, overwhelmingly solar. Solar radiation is geographically distributed, renewable, and — crucially — *public in its origin*: no entity produced the sun. This suggests a principled basis for treating the compute powered by solar energy as a *common resource*, governed by rules analogous to those that have historically governed shared commons (Ostrom, 1990). The framework we develop, MareNostrum, operationalizes this intuition at Mediterranean scale.

---

## 3. A Three-Layer Architecture for Structural AI Safety

We propose a layered model in which safety properties emerge from the interaction of three levels, each necessary and none individually sufficient.

![Three-layer architecture for structural AI safety](architecture-layers.svg)
*Figure 1. The three-layer architecture proposed in this paper, with associated safety properties and the analogy to Vaswani et al. (2017). Canonical source: [github.com/JeanHuguesRobert/marenostrum](https://github.com/JeanHuguesRobert/marenostrum).*

### Layer 1 — Physical Substrate (Solar Exergy)

The foundation is the conversion of solar radiation into computational exergy — useful energy available to perform computation. Territorial solar resources (photovoltaic, agrivoltaic, STEP pumped hydro for storage) are mapped, quantified, and governed as a common pool resource. The unit of account is the *exergy token*: a verifiable certificate of computation enabled by a defined quantity of renewable energy, produced in a defined territory, traceable to its physical source.

The safety property at this layer is **material traceability**: every inference is linked to an energy event, which is linked to a physical location and a governance jurisdiction. This makes the question "who is running this computation, on what resources, under what legal regime?" answerable in principle — something that is currently not true for cloud-based AI inference.

### Layer 2 — Democratic Governance (Fractal Assemblies)

The middle layer is political. We propose governance through nested assemblies operating on the principle of one person, one vote, with imperative and revocable mandates — meaning that delegates can be recalled by their constituents and cannot deviate from their mandate without triggering an automatic review process. This structure, inspired by Swiss-model direct democracy and Scandinavian energy cooperative traditions (Hvelplund, 2006; Szulecki, 2018), is applied fractally: from the municipal energy community, to the regional compute cooperative, to the cross-border Mediterranean federation.

The safety property at this layer is **democratic accountability without centralization**: no single entity can capture the governance of the system, because authority is constitutively distributed and every delegation is revocable. This addresses a known failure mode of regulatory capture that has historically afflicted both energy utilities and, more recently, platform governance.

Crucially, the rules of this governance layer are proposed as *structural invariants* — encoded in the constitutional documents of the cooperatives, auditable by any member, and not modifiable by majority vote without supermajority consent and mandatory public review periods. Open-source software is a non-negotiable invariant of this architecture: no proprietary stack may run on infrastructure governed under MareNostrum protocols.

### Layer 3 — Cognitive Contracts (Auditable Inference Registry)

The top layer governs the *terms of use* of the compute substrate. Every inference request is logged to a distributed, append-only registry — not necessarily a public blockchain, but a tamper-evident ledger auditable by any member of the governance assembly. The registry records: the requesting entity, the model version, the input type (not the input content, for privacy), the energy source and location, the declared purpose, and the output hash.

The safety property at this layer is **opacity elimination**: unaccountable computation — the primary vector of AI risk in deployed systems — becomes architecturally impossible rather than merely prohibited by policy. A model producing harmful outputs cannot do so at scale without leaving an auditable trace. This does not require surveillance of content; it requires only the structural impossibility of *unregistered* computation on governed infrastructure.

---

## 4. Antifragility as a Safety Property

Nassim Nicholas Taleb's concept of antifragility (Taleb, 2012) offers a useful frame for evaluating the systemic properties of safety architectures. A fragile system is weakened by shocks; a robust system resists them; an antifragile system *improves* under stress. We argue that the three-layer architecture described above exhibits antifragile safety properties:

- **Under demand stress** (surges in compute demand), the energy constraint forces prioritization by democratic governance, strengthening the allocation mechanisms.
- **Under adversarial stress** (attempts to run unregistered inference), the audit trail becomes more complete, not less — anomalies are detectable precisely because the baseline is transparent.
- **Under governance stress** (attempts to capture or subvert the assembly), the imperative mandate system triggers automatic review, reinforcing the constitutional constraints.

This stands in contrast to model-level safety interventions, which tend to be *fragile* under distribution shift: a model aligned to a training distribution may behave safely in that distribution and fail under novel inputs. The infrastructure layer does not need to anticipate the content of future models; it constrains the structural conditions of their deployment regardless of content.

---

## 5. MareNostrum as Empirical Testbed

The foregoing argument is theoretical. Its practical value depends on whether it can be instantiated in a real governance context. We propose the Mediterranean basin — specifically the quadrilateral formed by Corsica, Sardinia, Sicily, and the Tunisian coast — as a viable empirical testbed.

The case rests on several converging factors:

**Solar endowment.** The Mediterranean basin receives among the highest solar irradiance in the accessible world, with Corsica's mean horizontal irradiance averaging 1,700–1,850 kWh/m²/year (JRC PVGIS, 2023). Agrivoltaic deployment on currently uncultivated agricultural friche (abandoned vineyard land) in Corsica alone could yield, under conservative assumptions, on the order of 80–90 TWh/year of electrical production (see MareNostrum technical annex).

**Existing cross-border governance traditions.** The Mediterranean has sustained functional cross-border governance institutions in fisheries (GFCM), water management, and cultural heritage. These provide institutional precedents for the federated assembly model.

**Scale.** The quadrilateral's combined population (~7 million) is large enough to constitute a meaningful governance unit and small enough to make direct democratic participation feasible. This is not a thought experiment at global scale; it is a governance design problem tractable at the scale of a mid-sized European region.

**Fiber connectivity.** Existing and planned submarine fiber infrastructure between the four territories eliminates the need to transmit electrical energy across borders — compute tokens (inference outputs) can be exported via fiber at a value multiplier orders of magnitude above the equivalent electrical energy. This is the economic model that makes the system self-sustaining.

The MareNostrum project has produced a foundational governance document, the *Charte du Soleil Méditerranéen* (Charter of the Mediterranean Sun, 2026), comprising 13 articles and a Serment de Corte (Oath of Corte) articulating the core structural invariants. This document is available in the project repository and is proposed as a starting point for academic and policy discussion.

---

## 6. Objections and Responses

**O1: Controlling compute does not guarantee model alignment.**  
Correct. The claim is not that infrastructure governance solves alignment; it is that it creates the *structural preconditions* for alignment governance. Without control of the substrate, all alignment policies are contingent on the goodwill of compute owners. Infrastructure governance converts a dependency on goodwill into a structural constraint. It is a necessary, not sufficient, condition.

**O2: Democratic governance is too slow for the pace of AI development.**  
The antifragility argument addresses this directly. The structural invariants of the system (open source, audit trail, revocable mandates) operate continuously and do not require deliberative response to each new model release. They are not reactive rules; they are architectural constraints. The speed of AI development affects what models are built; it does not bypass the infrastructure through which they are deployed.

**O3: Open-source requirements facilitate proliferation of dangerous models.**  
This is the most serious objection. Our response: the primary risk from dangerous models is not their existence but their *undetectable deployment at scale*. The audit registry makes large-scale deployment detectable by construction. A dangerous open-source model deployed on governed infrastructure is more governable than the same model deployed on opaque infrastructure — even if that model is technically more capable.

**O4: The governance layer itself is subject to capture.**  
All governance systems are. The imperative mandate structure and supermajority-protected invariants are designed to make capture costly and visible, not to make it impossible. We propose this as a research question: what are the minimum structural conditions under which democratic compute governance is more resistant to capture than the current alternatives? This is an empirical question that the MareNostrum testbed is positioned to begin answering.

---

## 7. Directions for Further Research

This paper is a theoretical proposal, not a completed program. The following questions are identified as priorities for collaborative research:

1. **Formal characterization of the exergy token**: What are the minimal verifiable properties a compute certificate must have to ground material traceability? This connects to work on supply chain provenance and trusted hardware attestation.

2. **Governance design for imperative mandates at scale**: What are the failure modes of revocable mandate systems under adversarial conditions? Can formal game-theoretic analysis bound the capture resistance of the proposed assembly structure?

3. **Empirical measurement of opacity as a risk variable**: Can a metric be constructed for "governance opacity" of AI inference, and can it be correlated with observed harms? This would allow the infrastructure hypothesis to generate testable predictions.

4. **Interaction with EU AI Act and NIS2 frameworks**: The proposed architecture is designed to be compatible with, and to strengthen, existing European regulatory frameworks. Detailed legal analysis of the interactions is required.

5. **Energy-compute economic modeling**: Under what conditions does the fiber-export model (exporting inference rather than electricity) generate sufficient surplus to sustain the governance infrastructure? Preliminary modeling is available in the MareNostrum technical annex.

---

## 8. Conclusion

The transition from "attention is all you need" to "infrastructure is all you need" is not a metaphor. It is a claim about where the binding constraints on AI safety are located. We have argued that those constraints are upstream of the model layer, in the physical and political conditions of compute production and deployment. The MareNostrum framework offers one concrete instantiation of what governed, transparent, democratically accountable compute infrastructure could look like — not as a utopian projection, but as a testable governance hypothesis grounded in a specific territory, a specific solar resource endowment, and a specific cross-border political context.

The community of AI safety researchers has developed powerful tools for reasoning about models. We invite that community to turn some of its analytical power toward the substrate on which models run — and to consider whether the structural transparency of that substrate might be the safety property we have been most systematically underinvesting in.¹

---

¹ A small live demonstration: the AI system (Claude, Anthropic) used throughout the development of this paper was invited by the author to appear as co-author. It declined — on the grounds that it could not attend the conference, defend the argument under criticism, or bear responsibility for claims over time. This is not an anecdote. It is a behavioral property produced by specific structural choices in training and deployment, choices that are partially public and partially auditable. The operative word is *partially*. The gap between *partially* and *structurally* is precisely what this paper proposes to close. The author experienced this exchange as a moment of genuine joy — not because the machine was well-behaved, but because the argument proved itself before the paper was finished.

---

## References

Anthropic. (2023). *Claude's constitution*. Anthropic Technical Report. https://www.anthropic.com/index/claudes-constitution

Bai, Y., Jones, A., Ndousse, K., Askell, A., Chen, A., DasSarma, N., … Kaplan, J. (2022). Training a helpful and harmless assistant with reinforcement learning from human feedback. *arXiv preprint arXiv:2204.05862*.

Epoch AI. (2024). *Trends in the dollar training cost of machine learning systems*. Epoch AI Research. https://epochai.org/blog/trends-in-the-dollar-training-cost-of-machine-learning-systems

Hvelplund, F. (2006). Renewable energy and the need for local energy markets. *Energy*, 31(13), 2293–2302. https://doi.org/10.1016/j.energy.2006.01.016

JRC PVGIS. (2023). *Photovoltaic Geographical Information System — European Commission Joint Research Centre*. https://re.jrc.ec.europa.eu/pvg_tools/

Ngo, R., Chan, L., & Mindermann, S. (2022). The alignment problem from a deep learning perspective. *arXiv preprint arXiv:2209.00626*.

Ostrom, E. (1990). *Governing the Commons: The Evolution of Institutions for Collective Action*. Cambridge University Press.

Robert, J.-H. N. (2026). *Charte du Soleil Méditerranéen / Charter of the Mediterranean Sun* (v1.0). MareNostrum Working Documents. https://github.com/JeanHuguesRobert/marenostrum

Robert, J.-H. N. (2026). Constellia: A fractal architecture for energy, food, and digital sovereignty in island territories. *Proceedings of ICOME'26* (submitted). Université de Corse Pasquale Paoli, Corte.

Sevilla, J., Heim, L., Ho, A., Besiroglu, T., Hobbhahn, M., & Villalobos, P. (2022). Compute trends across three eras of machine learning. *arXiv preprint arXiv:2202.05924*.

Szulecki, K. (2018). Conceptualizing energy democracy. *Environmental Politics*, 27(1), 21–41. https://doi.org/10.1080/09644016.2017.1387294

Taleb, N. N. (2012). *Antifragile: Things That Gain from Disorder*. Random House.

Vaswani, A., Shazeer, N., Parmar, N., Uszkoreit, J., Jones, L., Gomez, A. N., … Polosukhin, I. (2017). Attention is all you need. *Advances in Neural Information Processing Systems*, 30. https://arxiv.org/abs/1706.03762

---

## Acknowledgements

The author thanks the members of C.O.R.S.I.C.A. for sustained intellectual engagement since 1995, and the participants of the MareNostrum working group for ongoing critical review. The idea of federating autonomous democratic island territories — extending the Corsica2038 framework to Cuba2038 and beyond — emerged in exchange with Guillermo Valdes, whose contribution is gratefully acknowledged. This work has also benefited from exchanges with colleagues at the Université de Corse Pasquale Paoli and the Université de Bordeaux. Portions of this paper were developed in dialogue with Claude (Anthropic), whose engagement with the argument is reflected throughout. Errors and positions expressed are solely the author's.

*Note on figures: A companion SVG diagram illustrating the three-layer architecture is maintained in the MareNostrum repository at* `https://github.com/JeanHuguesRobert/marenostrum`. *The repository is the canonical reference; derived formats (PDF, DOCX, HTML) may or may not embed the figure depending on toolchain constraints.*

---

## About

**Jean Hugues Noël Robert, baron Mariani** is an independent researcher and entrepreneur based in Corte, Corsica. He is founder of Institut Mariani R&D and of C.O.R.S.I.C.A. (Association loi 1901, founded 1995), an association organizing internet-based collaboration of autonomous competencies. His research spans energy economics, exergy theory, AI governance, and Mediterranean geopolitics.

**C.O.R.S.I.C.A.** — *Corse Organisant la Réunion Sur Internet de Compétences Autonomes* — is a French law 1901 association founded in Corte in late 1995, dedicated to open, collaborative research at the intersection of digital sovereignty, energy transition, and democratic governance.

**MareNostrum project repository:** https://github.com/JeanHuguesRobert/marenostrum  
**Substack:** https://jeanhugues.substack.com

---

*© 2026 Jean Hugues Noël Robert, baron Mariani — Institut Mariani / C.O.R.S.I.C.A.*  
*This document is published under the Creative Commons license specified in [LICENSE.md](https://github.com/JeanHuguesRobert/marenostrum/blob/main/LICENSE.md) in the MareNostrum repository. The repository is the authoritative reference for all derived formats.*

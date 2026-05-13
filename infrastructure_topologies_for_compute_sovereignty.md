---
canonical_url: https://github.com/JeanHuguesRobert/marenostrum/blob/main/infrastructure_topologies_for_compute_sovereignty.md
last_stamped_at: 2026-05-13
---
# Toward Empirical Validation of Infrastructure Topologies for Compute Sovereignty

**Jean Hugues Noël Robert, baron Mariani**,
Institut Mariani / C.O.R.S.I.C.A.
1 cours Paoli, F-20250 Corte, Corsica, France. 
[jhr@baronsmariani.org](mailto:jhr@baronsmariani.org)

## Abstract

This paper proposes a comparative framework for evaluating compute sovereignty as the capacity of an AI infrastructure to remain controllable, repairable, and governable under stress. We compare two infrastructure topologies: Orbital Topology (OT), characterized by centralized manufacturing, distributed low-Earth-orbit nodes, and high coordination dependency; and Territorial Topology (TT), characterized by terrestrial, energy-aware compute systems deployed across Mediterranean island and coastal regions and coordinated through Stella, a federated routing and governance layer with limited satellite fallback.

We define sovereignty as a composite index $S = f(R, P, D, G, F)$, where resilience, reparability, dependency depth, governance accessibility, and failure propagation sensitivity capture distinct structural properties of infrastructure. The contribution of this paper is threefold: a conceptual framework, a comparative metric, and a set of falsifiable hypotheses suitable for pilot validation. Preliminary scenario analysis suggests that TT architectures may outperform OT on sovereignty-related dimensions, particularly when renewable-energy co-location and local governance are available.

**Keywords**: compute sovereignty, infrastructure topology, resilience, reparability, governance, territorial computing, Mediterranean digital sovereignty.

***

## 1. Introduction

Compute sovereignty is commonly discussed in terms of ownership, jurisdiction, or regulatory control. These dimensions matter, but they do not fully capture the effect of physical infrastructure on operational autonomy. The topology of the compute substrate influences repairability, control under disruption, dependency on external supply chains, and the ability of local institutions to intervene when systems fail.

This paper argues that the relevant comparison is not simply centralized versus distributed compute. The deeper distinction is between architectures optimized for steady-state efficiency and architectures optimized for recoverability under stress. Orbital Topology and Territorial Topology represent two poles of this design space.

The objective is not to prove that one topology is universally superior. It is to define measurable sovereignty-related variables, articulate a coherent comparison, and specify a testable protocol for empirical validation.

***

## 2. Conceptual Framework

We define compute sovereignty as the capacity of an infrastructure to preserve operational control, repairability, and governance under adverse conditions. The concept is intentionally composite, because no single variable captures the full structural problem.

The proposed dimensions are:

- **R**: resilience to local failure.
- **P**: reparability, understood as the latency and feasibility of restoring service.
- **D**: dependency depth, inversely related to external supply-chain and coordination dependence.
- **G**: governance accessibility, meaning the degree to which legitimate local actors can inspect, intervene, and decide.
- **F**: failure propagation sensitivity, inversely related to the blast radius of a fault.

These dimensions are not claimed to be exhaustive. They are selected because they are conceptually relevant and operationally measurable.

***

## 3. Topological Comparison

Orbital Topology (OT) refers to a model in which compute infrastructure relies on low-Earth-orbit deployment, centralized manufacturing, and complex external dependencies. Its principal advantages are potential reach, reduced dependence on local land use, and certain deployment efficiencies. Its principal disadvantages are high coordination complexity, repair constraints, and reduced local governability.

Territorial Topology (TT) refers to terrestrial compute systems deployed close to renewable energy sources and situated in jurisdictions where local governance, maintenance, and energy management can be aligned. Its principal advantages are repairability, jurisdictional legibility, and the possibility of co-locating compute with local energy production. Its principal disadvantages are lower nominal efficiency in some configurations and stronger dependence on local political feasibility.

Stella is conceived as a federated coordination layer that links multiple territorial nodes while preserving local autonomy. In this framing, Stella is not a replacement for governance, but an interoperability mechanism between locally governed compute sites.

***

## 4. Methodology

The current version of the paper uses a scenario-based comparative framework. It does not yet claim completed field validation. Instead, it specifies a measurement architecture for future deployment.

The sovereignty score $S$ is modeled as a weighted function of the five variables above:

$$
S = f(R, P, D, G, F)
$$

The exact weighting scheme should be treated as provisional and calibrated empirically. In the present draft, the score is used for comparison between candidate infrastructures, not as a universal law.

The empirical program should proceed in three steps:

1. Simulation of failure propagation, repair latency, and governance response under stress.
2. Pilot deployment in selected Mediterranean sites.
3. Calibration of the sovereignty index against observed performance indicators.

This approach allows the paper to remain theoretically ambitious while preserving methodological credibility.

***

## 5. Mediterranean Testbed

The Mediterranean basin provides a plausible testbed for comparative infrastructure analysis because it combines high solar potential, existing fiber infrastructure, and multiple jurisdictions with partial institutional compatibility. Island and coastal territories are particularly relevant because they face energy constraints, logistical constraints, and governance fragmentation that make infrastructure topology observable in practice.

The proposed testbed includes Corsica, Sardinia, Sicily, and Tunisia. These territories differ in energy resources, governance context, and scaling potential, which makes them suitable for comparative analysis rather than simple case illustration.

Tunisia is especially important as a high-potential energy and storage node. Its Sahara region offers strong solar potential and a plausible pathway for large-scale renewable co-location. In a territorial model, Tunisia could function as a regional energy and backup hub, complementing smaller island sites with more immediate governability.

***

## 6. Comparative Scenario Table

The following values are provisional scenario estimates. They should be treated as illustrative until they are validated through measurement.


| Territory | Solar density | Storage | R | P | D | G | F | S |
| :-- | --: | :-- | --: | --: | --: | --: | --: | --: |
| OT | N/A | None | 0.70 | 0.20 | 0.80 | 0.30 | 0.70 | 0.45 |
| Corsica TT | 2,800 | Battery + micro-STEP | 0.95 | 0.90 | 0.10 | 0.85 | 0.05 | 0.82 |
| Sardinia TT | 2,600 | Micro-STEP | 0.92 | 0.88 | 0.12 | 0.82 | 0.08 | 0.80 |
| Sicily TT | 2,700 | Battery | 0.90 | 0.85 | 0.15 | 0.80 | 0.10 | 0.78 |
| Tunisia TT | 3,200–3,500 | Green hydrogen | 0.98 | 0.85 | 0.05 | 0.75 | 0.02 | 0.90 |

The purpose of the table is comparative structure, not final proof. A policy audience can use it to understand which variables matter and where empirical uncertainty remains.

***

## 7. Hypotheses

The paper advances three falsifiable hypotheses.

**H1.** Increasing physical centralization decreases reparability under stress.
Rationale: architectures dependent on complex external manufacturing and launch systems are harder to repair quickly when a systemic fault occurs.

**H2.** Increasing territorial distribution with Stella decreases failure propagation sensitivity.
Rationale: a federated topology with local autonomy should reduce cascading failure across the whole system.

**H3.** A Tunisia-based territorial deployment can achieve the highest sovereignty score in the Mediterranean testbed.
Rationale: its solar potential, storage options, and geographic position may provide superior continuity under stress, subject to political and infrastructural feasibility.

These hypotheses are deliberately stated in a form that can be tested, rejected, or revised.

***

## 8. Discussion

The main analytical result is that sovereignty should be treated as a property of infrastructure topology, not only of software or legal ownership. A system may be formally sovereign in one sense while remaining structurally dependent in another.

The paper also suggests that efficiency and recoverability are not interchangeable. An orbital architecture may appear efficient under nominal conditions, but a territorial architecture may better preserve continuity, local intervention capacity, and repairability under disruption. This distinction is likely to matter more for public-interest infrastructure than for purely commercial systems optimized for steady-state throughput.

Tunisia should be understood here as a strategic node within a regional architecture, not as a rhetorical centerpiece. That framing makes the argument more credible to experts because it connects the territorial option to measurable infrastructure and governance variables.

***

## 9. Limitations

This paper is a framework paper. It does not yet present a complete quantitative dataset. The sovereignty index remains subject to calibration, and the operational definitions of each variable require refinement through field work.

The orbital case is partly speculative because large-scale LEO deployment remains technically and economically contingent. The territorial case is also contingent, because it depends on local governance capacity, regulatory alignment, and capital deployment. These constraints are not incidental; they are part of the phenomenon being studied.

For that reason, the correct conclusion is not that TT is always superior. The more defensible conclusion is that territorial architectures may offer a better sovereignty profile under conditions where local recoverability and governance matter more than nominal throughput.

***

## 10. Conclusion

Compute sovereignty is a structural property of infrastructure topology. The proposed comparison between Orbital Topology and Territorial Topology shows that the trade-off is not simply between centralized and distributed systems, but between dependency-heavy efficiency and locally recoverable autonomy.

The paper’s main contribution is a framework that can be audited, criticized, and empirically refined. The next step is to move from scenario analysis to pilot deployment, metric calibration, and comparative observation.

***

## References

1. Robert, J. H. (2026). *Infrastructure Is All You Need: Toward a Structural Theory of AI Safety Grounded in Compute Sovereignty and Democratic Energy Governance*. MareNostrum Working Paper Series.
2. Robert, J. H., \& Valdes, G. (2026). *Constellia: A Fractal Architecture for Energy, Food, and Digital Sovereignty in Island Territories*. submitted to ICOME 2026.
3. European Space Agency. (2023). *Space Debris: The Silent Threat*.
4. ANME Tunisia. (2025). *Tunisia Solar Plan 2030: Pathways to 30% Renewables by 2030*.

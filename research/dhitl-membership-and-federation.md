---
author: "Jean Hugues Noël Robert, baron Mariani"
affiliation: "Institut Mariani / C.O.R.S.I.C.A., 1 cours Paoli, F-20250 Corte, Corsica"
license: "CC BY-SA 4.0"
canonical_url: https://github.com/JeanHuguesRobert/marenostrum/blob/main/research/dhitl-membership-and-federation.md
title: "DHITL — Membership, Affected Publics, and Federated Citizenship"
date: "2026-06-24"
status: "working-paper — doctrinal and procedural specification"
document_role: "source"
document_kind: "doctrine/specification"
visibility: "public"
lifecycle_state: "working"
review_status: "self-reviewed"
related_to:
  - "research/DHITL.md"
  - "research/DHITL-COVENANT.md"
  - "Democratic Humans In The Loop"
  - "One living person, one voice"
  - "Only the living vote"
  - "Affected-community suffrage"
  - "Inseme federated instances"
  - "Kudocracy / liquid democracy"
---

# DHITL — Membership, Affected Publics, and Federated Citizenship

## Orientation

This document specifies the membership layer of **DHITL — Democratic Humans In The Loop**.

It develops the principle introduced in the DHITL Covenant:

> **The affected should vote; when impact is uncertain, the relevant community votes; when several communities are affected, federation is required.**

French canonical form:

> **Les impactés doivent voter ; quand l'impact est incertain, la communauté pertinente vote ; quand plusieurs communautés sont impactées, la fédération devient nécessaire.**

The problem is simple to state and difficult to operationalize: democratic justice suggests that those affected by a decision should have a voice in that decision, but the perimeter of impact is rarely obvious.

DHITL therefore treats **membership** as a constitutional layer: not a mere user-account property, not a marketing segment, not a platform role, but the rule by which living persons are attached to a decision community.

This document is not a legal license, not a national citizenship theory, not an identity-provider specification, and not a claim that a single platform can solve democratic membership. Its role is narrower: define the anti-capture invariants that any DHITL-compatible membership system should preserve.

## 1. Core thesis

The intuitive rule is:

> **Those affected by a decision should have a voice in that decision.**

The stabilizing rule is:

> **When the affected public cannot be identified without arbitrariness, the relevant community becomes the voting body.**

The federating rule is:

> **When several communities are materially affected, the decision must move to a federated layer, require plural legitimacy, or make the exclusion of affected communities explicit, contestable, and auditable.**

Together:

> **Affected publics ground legitimacy. Membership stabilizes uncertainty. Federation handles cross-community impact.**

French compression:

> **L'impact fonde la légitimité. L'appartenance stabilise l'incertitude. La fédération traite les impacts transcommunautaires.**

## 2. Definitions

### 2.1 Living person

A **living person** is a human being currently alive.

In DHITL, only living persons can hold sovereign voting rights.

Agents, bots, digital twins, corporations, associations, foundations, DAOs, estates, memorial systems, and automated delegates may assist, testify, coordinate, administer, or execute technical mandates. They do not become sovereign voters.

### 2.2 Community

A **community** is a bounded decision context in which living persons share some legitimate basis for deliberation and collective action.

A community may be:

- geographic: commune, village, island, region, watershed, neighborhood;
- institutional: association, cooperative, school, university, foundation, commons institution;
- thematic: energy, water, biodiversity, language, culture, digital sovereignty, care;
- operational: maintainers, contributors, operators, users, validators;
- situated: crisis assembly, local consultation, project-specific public;
- federated: a community composed of several communities deciding together through a shared layer.

A community is not necessarily a state. Citizenship in DHITL is broader than national citizenship: it is scoped membership in a decision community.

### 2.3 Member

A **member** is a living person recognized as belonging to a community under explicit, published, contestable rules.

Membership is not merely an account. A user account may be the technical representation of a member, but the democratic status is attached to the living person, not to the account.

### 2.4 Citizen

A **citizen**, in the DHITL sense, is a living member of a decision community whose rules give that member legitimate voice in decisions within the community's scope.

This is a functional concept, not only a state-law concept.

A person may be a citizen of several communities: a commune, an association, a cooperative, a watershed assembly, a project, a university, an island network, or a thematic federation.

Multiple memberships do not create multiple sovereign votes inside the same decision body.

### 2.5 Affected public

An **affected public** is the set of living persons and communities materially affected by a decision.

Impact may be:

- direct: the decision acts on the person, property, service, rule, or environment of the affected persons;
- indirect but material: the decision creates foreseeable consequences for them;
- territorial: the decision affects a place they inhabit, use, preserve, or govern;
- functional: the decision affects a system they depend on or maintain;
- cultural or symbolic: the decision affects shared memory, language, heritage, or public meaning;
- ecological: the decision affects common conditions of life;
- intergenerational: the decision creates durable consequences beyond the current decision cycle.

Intergenerational and ecological impacts do not create votes for non-living persons. They require guardianship procedures, impact statements, supermajority thresholds, review triggers, reversibility analysis, or stewardship mandates held by living persons under explicit accountability.

### 2.6 Decision space

A **decision space** is the bounded domain in which a given vote, consultation, mandate, or deliberation applies.

A decision space must specify:

- subject matter;
- affected perimeter;
- voting body;
- membership rules;
- decision procedure;
- auditability level;
- appeal or challenge process;
- federation trigger, if any.

### 2.7 Federation

A **federation** is a structured relation between several communities that allows decisions to be made across community boundaries without erasing the autonomy of each community.

Federation is not centralization. It is the rule by which plural communities coordinate when impact crosses boundaries.

## 3. Why membership counts

The statement “vote those who are affected” is just, but unstable if left alone.

The perimeter of impact may be uncertain, contested, manipulable, delayed, distributed, or technically complex.

If the perimeter is defined too narrowly, affected persons are excluded.

If it is defined too broadly, the decision becomes illegible, manipulable, or captured by actors who are only weakly affected.

Membership is the stabilizer.

A community does not perfectly identify all affected persons, but it provides a legitimate default when exact impact measurement would be arbitrary, expensive, invasive, or capturable.

The democratic move is therefore:

1. identify the affected public where possible;
2. when exact identification is unstable, use the relevant community as the voting body;
3. when several communities are affected, federate the decision;
4. make perimeter choices explicit, contestable, and auditable.

## 4. Membership invariants

### M1 — Living-person anchoring

Membership attaches to living persons.

Accounts, tokens, credentials, devices, organizations, agents, digital twins, or wallets may represent or assist the person, but they do not become the person.

### M2 — Scope specificity

Membership is always scoped.

A person may be a member of a commune for territorial decisions, of a cooperative for cooperative decisions, of an association for association decisions, and of a thematic federation for thematic decisions.

No membership is universal by default.

### M3 — Equal sovereign weight within scope

Inside a given decision body, each living member has equal sovereign weight unless the process is explicitly consultative, weighted for a non-sovereign reason, and labeled as such.

A governance process may collect expert input, stakeholder testimony, contribution-weighted signals, or institutional opinions, but it must not confuse those signals with sovereign equal voting.

### M4 — No arbitrary exclusion

A community may not define membership or the affected public so narrowly that materially affected living persons are excluded without justification.

Exclusion must be justified, contestable, and reviewable.

### M5 — No artificial vote multiplication

A living person may belong to several communities, but overlapping memberships must not multiply sovereign weight inside the same decision.

A person cannot obtain additional sovereign weight by controlling several associations, companies, bots, wallets, accounts, foundations, DAOs, or digital delegates.

### M6 — Contestability

Membership decisions must be contestable.

A person who is denied membership, removed from a community, or excluded from a decision body must have access to a clear challenge procedure proportionate to the decision's importance.

### M7 — Minimality

A DHITL-compatible membership system should collect the minimum evidence necessary to establish membership and voting eligibility for the decision at hand.

Identity verification must not become political profiling.

Liveness verification must not become permanent surveillance.

### M8 — Federation trigger

When a decision materially affects more than one community, the process must identify whether the decision remains local, requires consultation of affected communities, requires dual legitimacy, or must move to a federated decision layer.

### M9 — Auditability without exposure

Membership rules, decision procedures, and aggregate eligibility decisions must be auditable.

Personal evidence used to establish membership should be disclosed only at the minimum level necessary, with privacy-preserving proofs where possible.

### M10 — Reversibility preference

When membership perimeter is uncertain, decisions should prefer reversible, staged, or sunsetted actions until legitimacy is clarified.

Irreversible decisions require stronger perimeter justification and stronger federation safeguards.

## 5. Minimum membership rule schema

Any DHITL-compatible community instance should publish a membership rule set with at least the following fields:

```yaml
community_id: string
community_name: string
community_type: territorial | institutional | thematic | operational | situated | federated
scope_statement: string
membership_classes:
  - name: string
    eligibility_criteria: string
    evidence_required: string
    rights:
      vote: boolean
      propose: boolean
      deliberate: boolean
      delegate: boolean
      challenge: boolean
    duties: string
entry_process: string
exit_process: string
removal_process: string
appeal_process: string
liveness_policy: string
identity_policy: string
privacy_policy: string
anti_sybil_policy: string
federation_triggers:
  - condition: string
    consequence: consultation | dual_legitimacy | federated_vote | ad_hoc_assembly | explicit_exclusion_with_audit
review_cycle: string
public_audit_surface: string
```

This schema is deliberately procedural rather than metaphysical. It does not pretend to know the true essence of belonging. It requires the community to state how belonging is recognized, challenged, audited, and revised.

## 6. Decision-body selection procedure

A DHITL-compatible process should determine the voting body through a visible sequence.

### Step 1 — Describe the decision

State what is being decided, what can change, what cannot change, and whether the decision is reversible.

### Step 2 — Map affected publics

Identify direct, indirect, territorial, functional, cultural, ecological, and intergenerational impacts.

Do not require impossible precision. Require explicit reasoning.

### Step 3 — Identify the relevant community

If the impact is mainly internal to one community, that community's living members form the default voting body.

### Step 4 — Test for arbitrary exclusion

Ask whether any materially affected living persons or communities have been excluded by the chosen perimeter.

If yes, justify, include, consult, or federate.

### Step 5 — Test for artificial vote multiplication

Ask whether any person or actor can multiply sovereign weight through overlapping structures, organizational stacking, multiple accounts, bots, proxies, or delegated machine agents.

If yes, deduplicate or separate the decision spaces.

### Step 6 — Choose the decision layer

Possible outcomes:

1. **Local vote**: one community is primarily affected.
2. **Local vote with affected-public consultation**: external effects are real but secondary.
3. **Dual legitimacy**: two communities must approve.
4. **Federated vote**: multiple communities are materially affected.
5. **Ad hoc affected-public assembly**: no standing community adequately covers the affected public.
6. **Explicit exclusion with audit**: some affected persons are excluded for stated reasons, with challenge rights.

### Step 7 — Publish the membership decision

Publish:

- decision scope;
- voting body;
- excluded publics, if any;
- federation choice;
- challenge period;
- audit surface.

## 7. Federation patterns

### 7.1 Local autonomy with notification

A local community decides, while notifying other communities because the effect is minor, reversible, or informational.

### 7.2 Local autonomy with consultation

The local community retains the vote, but affected external communities may submit arguments, objections, expert evidence, or minority reports.

### 7.3 Dual legitimacy

The decision requires approval by the directly acting community and by another materially affected community or federation.

This is suitable when a decision is local in execution but external in effect.

### 7.4 Federated vote

A shared decision body is formed across communities.

Deduplication is required: one living person should not vote twice inside the same federated decision merely because they belong to several member communities.

### 7.5 Ad hoc affected-public assembly

When no standing community captures the affected public, a temporary decision body may be formed.

Its mandate must be narrow, time-bounded, auditable, and dissolved after the decision cycle.

### 7.6 Emergency provisional decision

In urgent situations, a smaller body may act provisionally.

Conditions:

- narrow mandate;
- public justification;
- automatic sunset;
- post-hoc review;
- possibility of reversal or compensation;
- no conversion of emergency power into permanent authority.

## 8. Inseme implementation alignment

Inseme already points toward this architecture.

The software expression is approximately:

- an **instance** represents a community decision space;
- the **instance configuration** states community type, name, location, subdomain, and federation settings;
- the **hub registry** records instances and enables federation surfaces;
- **Kudocracy** provides proposals, deliberation, voting, delegation, and rule-based governance;
- **COP** provides replayable and auditable cognitive work across long-running processes;
- AI mediation may assist deliberation but must remain subordinate to living-person sovereignty.

The missing layer is not merely technical. It is constitutional: each instance must publish its membership rules and federation triggers.

### 8.1 Instance-level requirement

Every Inseme-compatible civic instance should have a `membership_policy` attached to its configuration.

Minimum fields:

```yaml
membership_policy:
  scope_statement: string
  member_classes: []
  voting_rights: []
  challenge_process: string
  federation_triggers: []
  liveness_policy: string
  deduplication_policy: string
  audit_surface: string
```

### 8.2 Proposal-level requirement

Every proposal should declare its expected impact scope.

```yaml
proposal_scope:
  primary_community_id: string
  affected_communities: []
  impact_level: internal | spillover | cross_community | federated | emergency
  reversibility: reversible | staged | difficult_to_reverse | irreversible
  decision_layer: local | consultative | dual_legitimacy | federated | ad_hoc
  membership_challenge_until: datetime
```

### 8.3 Delegation requirement

Delegation must remain compatible with living-person sovereignty.

Delegations should be:

- explicit;
- scoped by topic or decision type;
- revocable at any time;
- time-bounded by default;
- inspectable at least by the principal, and publicly inspectable where democratic integrity requires it;
- non-transferable to autonomous agents as sovereign delegates.

AI may suggest a delegate. AI may not become the delegate.

## 9. Hard cases

### 9.1 Residents, owners, workers, and users

A territorial decision may affect residents, property owners, workers, users, visitors, and future inhabitants differently.

DHITL does not automatically give each category equal decision rights in every case. It requires the community to state the rule and justify exclusions.

Example pattern:

- residents: default sovereign voters for local life decisions;
- owners: voting or consultative rights on property-linked obligations;
- workers and users: consultative or voting rights when the decision materially affects access, livelihood, or safety;
- external affected communities: federation trigger when spillovers are material.

### 9.2 Minors

Minors are living persons and are often materially affected by decisions.

Legal systems vary on whether and how they vote.

DHITL should not hide the issue. Possible stabilizers include youth assemblies, consultative voice, guardian representation, lowered voting age for certain communities, or issue-specific participation.

Any proxy must avoid vote multiplication by parents, institutions, or platforms.

### 9.3 Persons under protection, disability, or dependency

A person who needs assistance to deliberate or express a vote must not be treated as absent from sovereignty.

Assistance is legitimate when it increases the person's capacity. It becomes capture when the assistant substitutes their own will.

A DHITL-compatible process should support accessible deliberation, assisted expression, and auditable safeguards against substitution.

### 9.4 Diaspora

Diaspora membership may be legitimate for cultural, linguistic, patrimonial, or historical communities.

It is not automatically legitimate for all territorial decisions.

The question is scope: does the decision materially affect the diaspora as a community, or only symbolically interest it?

### 9.5 Future generations

Future generations are affected but cannot vote because they are not living persons.

DHITL handles this through living trusteeship, not postulated votes.

Tools: reversibility preference, long-term impact statements, supermajority for irreversible decisions, ecological thresholds, stewardship mandates, periodic review.

### 9.6 Non-human living beings and ecosystems

Animals, ecosystems, rivers, forests, and species can be materially affected but do not vote.

DHITL does not turn them into voters. It requires living human communities to create stewardship duties and evidence procedures so that their interests are not erased.

### 9.7 Legal persons

Associations, companies, foundations, parties, unions, DAOs, and public institutions may speak, act, own, contract, litigate, or administer.

They do not hold sovereign votes as persons.

Their voice can be recorded as institutional testimony, stakeholder position, or legal mandate, but not as an additional living-person vote.

## 10. Failure modes

### FM-M1 — Perimeter capture

The voting body is defined to include friends and exclude affected opponents.

Mitigation: published impact criteria, challenge period, minority-triggered review, federation trigger.

### FM-M2 — Identity monopoly

One state, corporation, biometric provider, or platform controls who counts as a person.

Mitigation: plural identity proofs, local attestations, revocable credentials, privacy-preserving verification, separation between identity verification and political profiling.

### FM-M3 — Community inflation

Actors create artificial communities to claim decision rights or dilute existing communities.

Mitigation: community recognition criteria, minimum continuity, affected-scope test, public registry, challenge procedure.

### FM-M4 — Organizational vote multiplication

One person controls several legal entities and turns them into extra political weight.

Mitigation: distinguish institutional voice from sovereign vote; deduplicate living-person control where the vote is sovereign.

### FM-M5 — Expert capture

Operational competence becomes sovereign authority.

Mitigation: separate technical maintainership, expert testimony, emergency execution, and democratic decision rights.

### FM-M6 — Platform capture

The platform operator defines membership, controls visibility, shapes options, and indirectly controls outcomes.

Mitigation: open protocols, exportable membership records, transparent ranking, audit logs, right to fork, and independent dispute resolution.

### FM-M7 — Bureaucratic capture of belonging

Membership becomes so administratively heavy that only organized actors can participate.

Mitigation: proportional evidence requirements, default inclusion where risk is low, staged verification, assisted onboarding, and appeal by simple procedure.

### FM-M8 — Privacy collapse

Membership verification exposes sensitive personal data.

Mitigation: minimal evidence, selective disclosure, local attestations, data minimization, short retention, and privacy-preserving credentials.

### FM-M9 — Liquid delegation alienation

Delegation becomes permanent political alienation.

Mitigation: expiry, active renewal, revocation by default, delegation dashboards, and alerts when one delegate accumulates excessive authority.

### FM-M10 — Federation paralysis

Every decision is said to affect everyone, making action impossible.

Mitigation: materiality threshold, reversibility analysis, tiered decision layers, and sunset clauses.

### FM-M11 — Emergency normalization

Emergency provisional decisions become permanent governance.

Mitigation: automatic sunset, mandatory review, post-hoc ratification, and public record of exceptional powers.

## 11. Reviewer pass — internal critique

This document has been reviewed internally using a second role: reviewer in addition to redactor.

### 11.1 Redactor prompt used

```text
Role: DHITL corpus redactor.
Task: Write a source document that extends DHITL-COVENANT.md by specifying membership, affected publics, and federated citizenship. Preserve the invariant "one living person, one voice; only the living vote". Integrate the user's principle: those affected by a decision should vote, but when impact is uncertain the relevant community votes, and when several communities are affected the decision must federate. Align with Inseme's multi-instance/federated architecture and Kudocracy's voting/delegation layer. Separate doctrine from legal licensing. Identify implementation requirements and failure modes. Use concise, stable, auditable formulations suitable for a versioned corpus.
```

### 11.2 Reviewer prompt used

```text
Role: DHITL corpus reviewer and anti-capture critic.
Task: Review the draft as if it might be used to govern real civic, associative, territorial, thematic, or federated decisions. Check for contradictions with DHITL-COVENANT.md, especially "one living person, one voice" and "only the living vote". Identify capture risks: arbitrary exclusion, vote multiplication, identity monopoly, platform capture, expert capture, bureaucratic capture, privacy collapse, delegation alienation, federation paralysis, and emergency normalization. Check whether the text confuses sovereign vote, consultative voice, organizational authority, technical maintainership, and AI assistance. Propose corrections that make the doctrine more operational, more auditable, and less capturable, without turning it into a closed or exclusionary license.
```

### 11.3 Reviewer findings

| Criterion | Finding | Correction integrated | Residual issue |
|---|---|---|---|
| Alignment with DHITL | The document preserves living-person sovereignty and AI subordination. | Repeated distinction between living person, account, organization, and agent. | Needs future direct link from `research/DHITL.md`. |
| Affected-public principle | Correct but dangerous if impact is undefined. | Added impact categories and decision-body selection procedure. | Materiality thresholds remain to be specified. |
| Membership | Treated as constitutional, not merely technical. | Added minimum membership schema. | Needs executable schema in Inseme. |
| Federation | Present and operationalized. | Added six federation patterns. | Vote deduplication across federated instances needs a technical spec. |
| Anti-capture | Main risks identified. | Added eleven membership failure modes. | Certification and dispute resolution still need institutional design. |
| Minors and protected persons | Not ignored. | Added hard-case sections. | Requires jurisdiction-specific legal treatment. |
| Future generations/ecology | Recognized without violating “only the living vote”. | Added stewardship mechanisms rather than fictional votes. | Needs a doctrine of trusteeship. |
| Privacy | Present but not solved. | Added minimality and auditability-without-exposure. | Requires concrete privacy-preserving credentials. |
| Liquid democracy | Compatible if delegation remains revocable and scoped. | Added delegation requirements. | Needs delegation concentration thresholds. |
| Open-source/legal layer | No restrictive license condition inserted. | Covenant remains separate from licensing. | Trademark/certification policy still needed. |

### 11.4 Reviewer conclusion

The document is coherent with DHITL and strengthens the covenant by turning “the affected should vote” into a procedural doctrine of membership and federation.

The main remaining weakness is not conceptual but operational: the doctrine needs a machine-readable membership policy schema, federation trigger rules, deduplication logic, and dispute-resolution procedure in Inseme/Kudocracy.

## 12. Next implementation targets

The next corpus and code targets should be:

1. `membership_policy.schema.json` for Inseme instances.
2. `proposal_scope.schema.json` for proposals and consultations.
3. Federation trigger rules in Kudocracy.
4. Delegation concentration warnings.
5. A privacy-preserving liveness and membership verification note.
6. A `TRADEMARKS.md` / compatibility label policy that links DHITL compatibility to covenant adherence without turning the license itself into a political exclusion clause.

## 13. Doctrinal compression

Very short form:

> **Belonging counts because impact is hard to delimit.**

Public form:

> **Votent ceux que la décision impacte ; quand l'impact est incertain, la communauté pertinente vote ; quand plusieurs communautés sont impactées, la décision se fédère. L'appartenance ouvre la voix, mais ne multiplie jamais la souveraineté : une personne vivante, une voix.**

Operational form:

> **Every decision must declare its affected public, voting body, membership rule, federation trigger, and challenge procedure.**

French operational form:

> **Toute décision doit déclarer son public impacté, son corps votant, sa règle d'appartenance, son déclencheur de fédération et sa procédure de contestation.**

---

*Institut Mariani, Corte, Corsica — 2026-06-24*  
*Published in the open: https://github.com/JeanHuguesRobert/marenostrum — CC BY-SA 4.0*

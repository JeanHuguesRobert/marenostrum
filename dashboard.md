---
title: "MareNostrum — Tableau de bord"
subtitle: "Suivi des expositions institutionnelles, apprentissages et continuations"
date: "2026-06-12"
status: "draft"
author: "Jean Hugues Noël Robert"
repository: "marenostrum"
path: "dashboard.md"
type: "dashboard"
related_trace_register: "https://github.com/JeanHuguesRobert/cogentia/blob/main/interaction_packets/mail_trace.md"
tags:
  - MareNostrum
  - dashboard
  - institutional_exposure_test
  - interactions
  - strategic_learning
---

# MareNostrum — Tableau de bord

Ce tableau de bord suit la transformation de MareNostrum :

```text
corpus public
→ interactions tracées
→ tests d’exposition
→ apprentissages
→ continuations
→ consortium ouvert
```

Il ne mesure pas seulement les succès. Il mesure aussi les apprentissages produits par les refus, silences, erreurs d’adressage, non-remises et cadrages institutionnels insuffisants.

## 1. État général

| Dimension | État | Commentaire |
|---|---|---|
| Corpus public | actif | Le dépôt MareNostrum documente déjà le cadre stratégique, énergétique, computationnel et démocratique. |
| Traçabilité des interactions | active | Les interactions publiques significatives sont suivies dans `cogentia/interaction_packets/mail_trace.md`. |
| Cadre institutionnel d’accueil | insuffisant | ICOME’26 a confirmé que MareNostrum ne se réduit pas à une session de colloque. |
| Presse / espace public | faible | Aucun relais public fort identifié à ce stade. |
| Partenaires potentiels | embryonnaire | Pistes énergie, recherche, autonomie alimentaire, institutions, mais pas encore de coalition. |
| Consortium ouvert | à constituer | La suite doit passer d’une demande d’accueil à une construction progressive du cadre. |

## 2. Tests d’exposition institutionnelle

| ID | Date | Objet | Canal | Résultat | Apprentissage | Continuation |
|---|---:|---|---|---|---|---|
| MN-2026-03-27-001 | 2026-03-27 | FractaVolta / Constellia ICOME26 | email partenaires énergie | pas de réponse détectée | L’intérêt potentiel des opérateurs doit être préparé par un paquet plus directement opératoire. | produire une note opérateurs énergie. |
| MN-2026-03-30-001 | 2026-03-30 | RFC Infrastructure Is All You Need | GitHub issue / email | critique ouverte, peu de réponse externe | Le design in the open existe, mais doit être activement relayé. | identifier lecteurs critiques ciblés. |
| MN-2026-03-31-001 | 2026-03-31 | Session spéciale MareNostrum ICOME’26 | email institutionnel | réponse institutionnelle ; intégration non obtenue | Échec de cadrage plus que de contenu. | constituer un cadre autonome. |
| MN-2026-04-11-001 | 2026-04-11 | Relance Jean-Louis Rossi / ICOME | email | suivi puis réponse négative consolidée | L’institution traite la proposition comme demande de programme, non comme cadre stratégique. | ne pas insister dans ce canal. |
| MN-2026-04-11-002 | 2026-04-11 | PRIMA Secretariat | email | échec de livraison | Adresse ou canal inadapté. | rechercher canal PRIMA fiable. |
| MN-2026-04-12-001 | 2026-04-12 | PRIMA France / ANR | email | aucune réponse détectée | Le message doit probablement être recadré comme question d’éligibilité ou appel précis. | préparer relance courte ou abandonner. |
| MN-2026-04-12-002 | 2026-04-12 | François Casabianca / autonomie alimentaire | email | réponse reçue, rapport transmis | L’entrée alimentaire est un point d’ancrage territorial plus concret. | intégrer alimentation / autonomie au paquet territorial. |
| MN-2026-06-12-001 | 2026-06-12 | Bilan post-ICOME’26 | journal de bord | apprentissage formalisé | Un non-accueil peut devenir une donnée stratégique. | passer au consortium ouvert. |

## 3. Modèle généralisable : test d’exposition institutionnelle

Un test d’exposition institutionnelle suit le cycle :

```text
proposition structurée
→ institution cible
→ réponse / silence / refus / non-remise
→ diagnostic : contenu ou cadrage ?
→ apprentissage
→ continuation
```

### Typologie des résultats

| Résultat observé | Lecture possible | Action possible |
|---|---|---|
| Réponse positive | adéquation contenu + cadrage | approfondir, documenter, transformer en partenariat. |
| Réponse négative argumentée | contenu ou timing contesté | extraire les objections, réviser. |
| Réponse négative administrative | cadrage institutionnel insuffisant | changer de format ou de canal. |
| Silence | faible lisibilité ou faible priorité | reformuler, cibler autrement, ou abandonner. |
| Non-remise | erreur d’adressage | corriger l’infrastructure de contact. |
| Relais inattendu | émergence d’un autre chemin | suivre la continuation. |

## 4. Décision stratégique post-ICOME’26

Décision provisoire :

> MareNostrum ne doit plus être pensé comme une proposition cherchant à être accueillie dans un cadre existant. Il doit devenir progressivement un cadre autonome, suffisamment documenté pour que des institutions, chercheurs, élus, opérateurs et citoyens puissent ensuite le rejoindre.

Conséquence :

```text
session spéciale
→ cadre autonome
→ consortium ouvert
```

## 5. Prochaines actions

| Priorité | Action | Support probable | Statut |
|---:|---|---|---|
| P1 | Rédiger une note post-ICOME’26 courte, non polémique | `research/post_icome26_conclusions.md` | à faire |
| P1 | Transformer le journal de bord en leçon méthodologique réutilisable | `journal/2026-06-12-post-icome26.md` | fait |
| P2 | Produire un paquet d’introduction pour partenaires énergie | `research/operator_memo.md` ou `memos/energy_operators.md` | à faire |
| P2 | Produire une version élus / collectivités | `memos/elected_officials.md` | à faire |
| P2 | Identifier trois partenaires hors université | dashboard | à faire |
| P3 | Formaliser un modèle minimal de consortium ouvert | `governance/open_consortium_model.md` | à faire |

## 6. Documents liés

- [Journal de bord — Après ICOME’26](journal/2026-06-12-post-icome26.md)
- [RFC: Infrastructure Is All You Need](https://github.com/JeanHuguesRobert/marenostrum/issues/1)
- [Mail Trace Register](https://github.com/JeanHuguesRobert/cogentia/blob/main/interaction_packets/mail_trace.md)
- [MareNostrum repository README](README.md)

## 7. Principe de lecture

Ce tableau de bord ne doit pas servir à produire un récit victimaire.

Il sert à transformer chaque interaction en donnée d’apprentissage.

La question n’est pas :

> Qui a refusé ?

La question est :

> Que révèle ce refus, ce silence ou cette absence de relais sur le cadre qu’il faut construire ?

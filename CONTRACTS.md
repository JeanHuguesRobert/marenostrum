# MareNostrum — CONTRATS de disponibilité énergétique

## 1. Objet

Ce document définit la couche contractuelle du système MareNostrum.

Il formalise les engagements entre :
- producteurs de capacité énergétique
- consommateurs / collectivités
- opérateurs de réseau

Le contrat porte non pas sur l’énergie produite, mais sur la **capacité garantie de fourniture**.

---

## 2. Définition du service contractuel

Le service vendu est une unité de :

> disponibilité énergétique sous contrainte de système

Formalisée comme :

- une quantité d’énergie (kWh)
- livrable dans une fenêtre temporelle donnée
- avec un niveau de garantie explicite

---

## 3. Types de contrats

### 3.1 Contrat spot
- livraison immédiate
- prix dépendant de la rareté instantanée
- faible garantie

---

### 3.2 Contrat standard
- livraison planifiée
- tolérance de variation limitée
- prix stabilisé par moyenne de rareté

---

### 3.3 Contrat de sécurité (ou assurance énergétique)
- engagement de livraison même en situation de tension
- activation des réserves et du stockage
- prime de risque élevée

---

## 4. Niveau de garantie

Chaque contrat est défini par un coefficient G :

G ∈ [0,1]

- G = 0 → aucune garantie (marché spot)
- G = 1 → garantie totale en période critique

Le prix est proportionnel à G et à la rareté attendue.

---

## 5. Mécanisme de déclenchement

En cas de tension système R(t) élevée :

- activation du stockage
- redirection de flux
- priorisation des contrats à haut G

Les contrats deviennent hiérarchisés selon :
1. niveau de garantie
2. criticité d’usage
3. ancienneté contractuelle

---

## 6. Rôle du stockage

Le stockage agit comme :

- amortisseur contractuel
- réserve de sécurité
- outil d’exécution des engagements

Sans stockage, les contrats à forte garantie deviennent impossibles à honorer.

---

## 7. Non-livraison et compensation

En cas de défaut de livraison :

- compensation automatique financière
- indexation sur prix de rareté instantané
- possibilité de basculement vers crédit énergétique futur

---

## 8. Architecture institutionnelle

Le système nécessite trois rôles :

- Producteurs (capacité physique)
- Opérateurs (allocation et arbitrage)
- Assureur énergétique (gestion du risque systémique)

---

## 9. Couplage avec le pricing

Le prix contractuel est :

Prix = Prix énergie (PRICING.md) + Prime de garantie (G × risque système)

---

## 10. Propriété fondamentale

Un contrat énergétique n’est pas un échange de matière.

C’est un **transfert de responsabilité sur la continuité énergétique**.

---

## 11. Extension possible

Ce modèle permet :

- marchés régionaux interconnectés
- mutualisation méditerranéenne des risques
- création d’instruments financiers adossés à la disponibilité énergétique
- intégration dans des systèmes de gouvernance énergétique locale

---

## 12. Lien avec le modèle physique

Les contraintes contractuelles sont directement dérivées de la dynamique d’exergie :

E = ∫ w(t) · U(t) dt

Un contrat est une contrainte imposée sur U(t) dans le temps.

---

## 13. Principe directeur

La valeur du système ne réside pas dans la production brute.

Elle réside dans la **continuité garantie de la disponibilité sous contrainte réelle**.

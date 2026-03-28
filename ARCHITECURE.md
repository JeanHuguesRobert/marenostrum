# Mare Nostrum — ARCHITECTURE du système

## 1. Objet

Ce document unifie les couches du système Mare Nostrum en une architecture cohérente.

Il relie :
- la physique du système
- la formation des prix
- les mécanismes contractuels
- la gouvernance des décisions

---

## 2. Principe d’ensemble

Le système est une boucle fermée :

> énergie physique → transformation → signal économique → engagement contractuel → arbitrage de gouvernance → retour sur flux physique

Chaque couche agit comme contrainte sur la suivante.

---

## 3. Architecture en couches

### 3.1 Couche physique (MODEL.md)

Entrées :
- irradiation solaire
- production locale
- stockage
- consommation

Sorties :
- flux disponibles
- état de rareté

---

### 3.2 Couche économique (PRICING.md)

Entrées :
- rareté R(t)
- demande D(t)
- production P(t)

Sorties :
- prix instantané p(t)
- signal de tension système

Rôle :
> transformer une contrainte physique en signal exploitable

---

### 3.3 Couche contractuelle (CONTRACTS.md)

Entrées :
- prix
- niveau de garantie G
- état du stockage

Sorties :
- engagements de livraison
- hiérarchie de priorité
- mécanismes de compensation

Rôle :
> transformer le signal de prix en obligations exécutables

---

### 3.4 Couche de gouvernance (GOVERNANCE.md)

Entrées :
- besoins locaux
- contraintes systémiques
- données de production et consommation

Sorties :
- règles d’allocation
- priorités de distribution
- évolution des règles du système

Rôle :
> arbitrer la distribution du pouvoir sur les flux physiques

---

## 4. Boucle de rétroaction

Le système fonctionne en boucle :

1. Le système physique produit des flux
2. La rareté est calculée
3. Le prix s’ajuste
4. Les contrats s’activent
5. La gouvernance arbitre les priorités
6. Les flux physiques sont réalloués

---

## 5. Variable centrale du système

La variable structurante unique est :

> R(t) = déséquilibre instantané entre production et demande

Toutes les couches sont des transformations de R(t).

---

## 6. Propriété systémique

Le système est :

- non linéaire
- dépendant des événements rares
- fortement couplé au stockage
- sensible aux pics de demande

---

## 7. Rôle du stockage

Le stockage est un élément transversal :

- amortit les variations physiques
- stabilise les prix
- rend les contrats de garantie possibles
- réduit la charge de gouvernance en crise

---

## 8. Hiérarchie des couches

Ordre de contrainte :

1. Physique (invariante)
2. Économie (dérivée)
3. Contrats (interprétation opérationnelle)
4. Gouvernance (règles d’arbitrage)

La gouvernance ne peut pas violer la physique.

---

## 9. Principe de cohérence

Aucune couche ne peut introduire une logique :

- indépendante de R(t)
- contradictoire avec les contraintes physiques
- déconnectée de la disponibilité réelle

---

## 10. Extension du système

L’architecture est compatible avec :

- simulation multi-agents
- marchés interconnectés (îles, régions)
- intégration de stockage massif
- mécanismes assurantiels énergétiques
- réseaux méditerranéens couplés

---

## 11. Limite structurelle

Le système est borné par :

- l’énergie solaire disponible
- la capacité de stockage
- la stabilité des flux inter-zones

---

## 12. Principe final

Le système Mare Nostrum n’est pas un marché énergétique.

C’est un système de transformation contrôlée de contraintes physiques en équité d’accès à une ressource finie.

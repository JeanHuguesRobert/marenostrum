# Mare Nostrum — Modèle d’exergie opérationnelle

## 1. Objet

Ce document définit un modèle minimal de représentation d’un système énergétique fondé sur la notion d’exergie opérationnelle.

Il formalise la transition :
- d’un système optimisé sur la production
- vers un système optimisé sur la disponibilité utile en conditions de contrainte

---

## 2. Variables fondamentales

On définit les grandeurs suivantes :

- **P(t)** : puissance produite à l’instant t (kW)
- **D(t)** : demande instantanée (kW)
- **S(t)** : énergie stockée disponible (kWh)
- **C** : capacité maximale de stockage (kWh)
- **τ** : horizon temporel d’analyse

Contraintes :
- 0 ≤ S(t) ≤ C

---

## 3. Énergie utile

L’énergie effectivement utilisable est définie par :

U(t) = min(P(t) + S(t), D(t))

Cette fonction exprime la capacité du système à satisfaire la demande réelle.

---

## 4. Définition de la rareté

La rareté instantanée du système est :

R(t) = max(0, D(t) − P(t))

- R(t) = 0 : situation de surplus
- R(t) > 0 : situation de déficit structurel

---

## 5. Fonction de valeur temporelle

La valeur de l’énergie dépend de la rareté.

On définit un poids temporel :

w(t) = f(R(t))

Deux formes simples possibles :

- linéaire :
  w(t) = 1 + α · R(t)

- exponentielle :
  w(t) = exp(α · R(t))

où α > 0 représente la sensibilité à la rareté.

---

## 6. Définition de l’exergie opérationnelle

L’exergie opérationnelle E est définie comme :

E = ∫₀^τ w(t) · U(t) dt

Elle mesure la valeur totale du service énergétique rendu sous contrainte de rareté.

---

## 7. Interprétation des régimes

### Surproduction
P(t) > D(t)
- faible valeur marginale de l’énergie
- dépendance au stockage

### Équilibre
P(t) ≈ D(t)
- efficacité maximale du système

### Rareté
P(t) < D(t)
- forte augmentation de la valeur de l’énergie disponible

---

## 8. Loi structurelle

La valeur d’un système énergétique ne dépend pas de la production moyenne, mais de sa capacité à couvrir les périodes de rareté.

Les événements extrêmes dominent la valeur du système.

---

## 9. Lecture économique

Ce modèle définit implicitement un produit énergétique nouveau :

- non pas une quantité d’énergie (kWh)
- mais une garantie de disponibilité en conditions de rareté

Cela constitue une base pour un mécanisme de type assurance énergétique.

---

## 10. Conséquence système

Deux leviers principaux :

- augmentation de la production P(t)
- augmentation du stockage S(t)

Leur efficacité dépend de la distribution des événements de rareté.

---

## 11. Principe structurant

Le système est optimisé sur les extrêmes, non sur la moyenne.

La robustesse remplace le rendement moyen comme critère principal.

---

## 12. Extension

Ce modèle est volontairement minimal.

Il constitue la base de :
- modélisations économiques
- architectures énergétiques distribuées
- systèmes d’assurance de disponibilité

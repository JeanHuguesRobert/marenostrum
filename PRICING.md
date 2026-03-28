# Mare Nostrum — Modèle de pricing de la disponibilité énergétique

## 1. Objet

Ce document définit un modèle économique minimal permettant de valoriser la disponibilité énergétique dans un système fondé sur l’exergie opérationnelle.

Il prolonge le modèle physique défini dans `MODEL.md` en introduisant une logique de prix dépendante de la rareté.

---

## 2. Hypothèse centrale

La valeur de l’énergie n’est pas constante.

Elle dépend de sa capacité à être délivrée :
- au bon moment
- dans des conditions de contrainte
- lorsque le système global est en tension

Le produit économique n’est donc pas un kilowattheure, mais une **disponibilité garantie**.

---

## 3. Variable de rareté système

On définit la rareté globale :

R(t) = max(0, D(t) − P(t))

où :
- D(t) : demande
- P(t) : production

Cette variable détermine la tension du système.

---

## 4. Prix de l’énergie instantanée

Le prix unitaire de l’énergie devient fonction de la rareté :

p(t) = p₀ · f(R(t))

où :
- p₀ : prix de base
- f : fonction croissante de la rareté

Deux formes simples :

- linéaire :
  f(R) = 1 + αR

- exponentielle :
  f(R) = exp(αR)

---

## 5. Interprétation économique

### Situation normale
- R(t) ≈ 0
- prix proche du prix de base
- énergie abondante

### Situation tendue
- R(t) > 0
- augmentation rapide du prix
- valeur marginale élevée de la disponibilité

### Situation critique
- forte rareté
- prix dominé par la capacité de livraison, non par la production

---

## 6. Définition du produit

Le produit économique fondamental devient :

> une unité de capacité de fourniture énergétique sous contrainte

Autrement dit :
- non pas “1 kWh”
- mais “1 kWh garanti en situation de rareté”

---

## 7. Structure assurantielle

Le système peut être interprété comme une assurance :

- l’utilisateur paie une prime
- le système garantit une disponibilité
- la rareté déclenche la valeur économique

Le prix est donc structurellement un **prix du risque énergétique**.

---

## 8. Couplage avec le stockage

Le stockage S(t) agit comme amortisseur de prix :

- plus S(t) est élevé
- plus les pics de prix sont lissés

Mais sa valeur marginale augmente fortement en période de rareté prolongée.

---

## 9. Propriété structurelle

Le système est dominé par les événements rares.

La distribution du prix n’est pas normale :
- elle est asymétrique
- avec des pics liés aux périodes de déficit énergétique

---

## 10. Loi fondamentale

Le prix n’est pas déterminé par la moyenne de production.

Il est déterminé par :
> la capacité du système à éviter l’échec en période de contrainte.

---

## 11. Conséquence stratégique

Dans ce modèle :
- produire plus réduit partiellement le risque
- stocker réduit fortement la volatilité
- mais seule la combinaison des deux garantit la stabilité du prix

---

## 12. Extension

Ce modèle constitue une base pour :
- contrats de disponibilité énergétique
- mécanismes d’assurance énergétique
- marchés régionaux interconnectés (multi-zones méditerranéennes)

---

## 13. Lien avec le modèle physique

Ce pricing est directement dérivé de l’exergie opérationnelle :

E = ∫ w(t) · U(t) dt

Le prix est la projection économique de la valeur de disponibilité sous contrainte.

# Modèle économique — Compte courant géré par l'asso

## Le flux complet (CORRECT ET LÉGAL)

### Opération Gaming (Ronan porte)

```text
CA encaissé : 100 000 EUR
    ↓ [Ronan déclare à l'URSSAF]
URSSAF : 100 000 EUR déclaré
    ↓ [Ronan paie cotisations + charges]
Charges opérationnelles : -37 000 EUR
Cotisations URSSAF : -12 300 EUR
Impôt sur revenu (estimé) : -8 700 EUR
    ↓
NET : 42 000 EUR
    ↓ [Ronan verse à l'asso]
ASSO reçoit : 42 000 EUR
```text

### Opération Musique (Johann porte)

```text
CA encaissé : 60 000 EUR
    ↓ [Johann déclare à l'URSSAF]
URSSAF : 60 000 EUR déclaré
    ↓ [Johann paie cotisations + charges]
Charges opérationnelles : -22 000 EUR
Cotisations URSSAF : -7 380 EUR
Impôt sur revenu (estimé) : -5 220 EUR
    ↓
NET : 25 000 EUR
    ↓ [Johann verse à l'asso]
ASSO reçoit : 25 000 EUR
```text

### Asso gère le compte courant

```text
ASSO reçoit total : 42 000 + 25 000 = 67 000 EUR

Compte courant :
├─ Ronan a apporté : 42 000 EUR (Op 1)
├─ Johann a apporté : 25 000 EUR (Op 2)
├─ Différence : 42 000 - 25 000 = 17 000 EUR en faveur de Ronan
└─ Compensation : Johann reçoit + 8 500 EUR pour équilibrer

Distribution finale (50/50) :
├─ Ronan : 42 000 - 8 500 = 33 500 EUR
└─ Johann : 25 000 + 8 500 = 33 500 EUR
```text

---

## Légalité du modèle

### ✅ Pourquoi c'est légal

1. **Déclaration URSSAF honnête**


   - Ronan déclare 100k (CA réel Gaming)

   - Johann déclare 60k (CA réel Musique)

   - Total : 160k (aucun mensonge)

2. **Pas de "société de fait"**


   - Ce n'est pas un partage de bénéfices entre AE

   - C'est un versement à l'asso (entité légale)

   - L'asso redistribue = son droit

3. **Chacun paie ses cotisations correctement**


   - Ronan : 12,3% de 100k

   - Johann : 12,3% de 60k

   - Pas de double-taxation

4. **Trace documentée**


   - Versements Ronan→Asso : documentés

   - Versements Johann→Asso : documentés

   - Redistribution via compte courant : formalisée dans statuts

### ⚠️ Points clés pour rester légal


- ❌ **Ne JAMAIS** : transférer directement entre AE (Ronan→Johann)

- ✅ **TOUJOURS** : passer par l'asso pour redistribuer

- ❌ **Ne JAMAIS** : mélanger les comptes Stripe

- ✅ **TOUJOURS** : garder traces des versements à l'asso

---

## Implémentation technique

### Comptes bancaires

| Entité            | Compte               | Détail                          |
|-------------------|----------------------|---------------------------------|
| **Ronan (AE A)**  | Stripe Ronan         | Encaisse CA Gaming              |
| **Johann (AE B)** | Stripe Johann        | Encaisse CA Musique             |
| **Asso**          | Compte bancaire asso | Reçoit versements + redistribue |

### Flux mensuel

```text
Semaine 1-12 : Opération gaming lancée
├─ Clients achètent → Stripe Ronan
├─ Ronan paie charges sur Stripe Ronan
└─ À la fin : Ronan verse son NET à l'asso

Semaine 13-24 : Opération musique lancée
├─ Clients achètent → Stripe Johann
├─ Johann paie charges sur Stripe Johann
└─ À la fin : Johann verse son NET à l'asso

Fin d'année : Redistribution compte courant
├─ Asso calcule la différence
├─ Asso transfère compensation (si besoin)
└─ Résultat : 50/50 chacun
```text

### Documents à garder


- ✅ Versements Ronan→Asso : relevé bancaire

- ✅ Versements Johann→Asso : relevé bancaire

- ✅ Redistribution asso : décision AG ou procès-verbal

- ✅ Compte courant : suivi annuel formalisé

---

## Exemple chiffré concret

### Scenario 1 : Gaming rapporte plus

| Année                    | Op Gaming (Ronan) | Op Musique (Johann) | Total          | Equilibre   |
|--------------------------|-------------------|---------------------|----------------|-------------|
| Net apporté              | 42 000 EUR        | 25 000 EUR          | 67 000 EUR     | -17 000 EUR |
| Réception compte courant | -8 500 EUR        | +8 500 EUR          | 0 EUR          | ✅           |
| **Final reçu**           | **33 500 EUR**    | **33 500 EUR**      | **67 000 EUR** | **50/50**   |

### Scenario 2 : Musique rapporte plus

| Année                    | Op Gaming (Ronan) | Op Musique (Johann) | Op Lifestyle (Ronan) | Total          | Equilibre   |
|--------------------------|-------------------|---------------------|----------------------|----------------|-------------|
| Net apporté              | 42 000 EUR        | 35 000 EUR          | 20 000 EUR           | 97 000 EUR     | -13 000 EUR |
| Réception compte courant | +6 500 EUR        | -6 500 EUR          | +0 EUR               | 0 EUR          | ✅           |
| **Final reçu**           | **48 500 EUR**    | **28 500 EUR**      | **20 000 EUR**       | **97 000 EUR** | **~50/50**  |

---

## À inclure dans les documents

### Statuts asso (à ajouter)

```text
Article X — Compte courant

L'association gère un compte courant entre les auto-entrepreneurs
associés pour équilibrer leurs contributions.

1. Chaque auto-entrepreneur verse son bénéfice net à l'association
   à la fin de chaque opération commerciale.

2. L'association tient un compte courant documentant les versements
   de chacun.

3. En fin de période (annuelle), l'association opère une redistribution
   pour équilibrer les contributions, afin que chaque partenaire
   reçoive sa part équitable.

4. Cette redistribution est décidée par l'assemblée générale.
```text

### Contrat de partenariat (à créer)

```text
Les deux auto-entrepreneurs conviennent que :

1. Chacun porte alternativement ou concurremment les opérations
   commerciales au nom de la marque Drop & Loot.

2. Chacun encaisse et déclare 100% du CA de l'opération qu'il porte
   à l'URSSAF.

3. Chacun paie ses cotisations et charges sur ses revenus.

4. Chacun verse son bénéfice net à l'association.

5. L'association gère un compte courant et redistribue en fin de période
   pour équilibrer les contributions à 50/50.

6. Cette redistribution est transparente et documentée.
```text

---

## Questions à l'avocat

Ajouter au courrier :

> "Nous avons deux auto-entrepreneurs indépendants qui versent leurs bénéfices nets à l'association, qui gère un compte courant pour redistribuer équitablement (50/50). Est-ce juridiquement conforme ? Comment formaliser cela dans les statuts et un contrat de partenariat ?"

---

## Avantages du modèle

✅ **Légal** — pas de "société de fait"
✅ **Honnête** — URSSAF voit 100% du CA réel
✅ **Transparent** — traces documentées
✅ **Équitable** — compte courant = 50/50
✅ **Flexible** — chacun peut porter n'importe quelle opération
✅ **Pas de redessus** — aucun risque de requalification

---

## Résumé : Qui fait quoi

| Entité            | Rôle                                                            |
|-------------------|-----------------------------------------------------------------|
| **Ronan (AE A)**  | Porte opérations, encaisse CA, déclare URSSAF, verse net à asso |
| **Johann (AE B)** | Porte opérations, encaisse CA, déclare URSSAF, verse net à asso |
| **Asso**          | Gère compte courant, redistribue pour équilibre 50/50           |
| **URSSAF**        | Voit 100% du CA réel, aucune fraude                             |


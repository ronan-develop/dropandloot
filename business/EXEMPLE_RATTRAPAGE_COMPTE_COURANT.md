# Exemple: Rattrapage par compte courant

Démonstration du système avec 3 opérations montrant comment celui en retard se rattrappe.

---

## 📊 Données des opérations

| Opération | CA | Charges URSSAF (12.3%) | Net versé asso |
|-----------|-----|------------------------|-----------------|
| **Op 1** | 10 000€ | -1 230€ | **8 770€** |
| **Op 2** | 5 000€ | -615€ | **4 385€** |
| **Op 3** | 15 000€ | -1 845€ | **13 155€** |

---

## 🔢 Scénario: Ronan fait Op 1 et Op 3, Johann fait Op 2

### Phase 1: Opération 1 (Ronan encaisse)

**Qui?** : Ronan (AE A)  
**CA** : 10 000€  
**Charges URSSAF** : -1 230€ (12.3%)  
**Bénéfice net** : 8 770€  
**Versé à l'asso** : 8 770€  

**État compte courant** :
- Ronan: +8 770€
- Johann: 0€
- **Écart**: 8 770€ (Ronan en avance)

```
Ronan:   ████████ 8 770€
Johann:  
```

---

### Phase 2: Opération 2 (Johann encaisse)

**Qui?** : Johann (AE B)  
**CA** : 5 000€  
**Charges URSSAF** : -615€ (12.3%)  
**Bénéfice net** : 4 385€  
**Versé à l'asso** : 4 385€  

**État compte courant** :
- Ronan: +8 770€
- Johann: +4 385€
- **Écart**: 4 385€ (Ronan toujours en avance)

```
Ronan:   ████████ 8 770€
Johann:  ████ 4 385€
```

---

### Phase 3: Opération 3 (Ronan encaisse à nouveau)

**Qui?** : Ronan (AE A)  
**CA** : 15 000€  
**Charges URSSAF** : -1 845€ (12.3%)  
**Bénéfice net** : 13 155€  
**Versé à l'asso** : 13 155€  

**État compte courant** :
- Ronan: 8 770€ + 13 155€ = **+21 925€**
- Johann: **+4 385€**
- **Écart**: 17 540€ (Ronan très en avance)

```
Ronan:   ████████████████████ 21 925€
Johann:  ████ 4 385€
```

---

## ⚖️ Redistribution: Comment Johann se rattrape

**L'association calcule** :
```
Écart = 21 925€ - 4 385€ = 17 540€
Redistribution par personne = 17 540€ ÷ 2 = 8 770€
```

**L'association opère** :
- Prend 8 770€ à Ronan
- Donne 8 770€ à Johann

**Résultat final (50/50)** :
- Ronan: 21 925€ - 8 770€ = **13 155€**
- Johann: 4 385€ + 8 770€ = **13 155€**

```
AVANT redistribution:
Ronan:   ████████████████████ 21 925€
Johann:  ████ 4 385€

APRÈS redistribution:
Ronan:   █████████████ 13 155€
Johann:  █████████████ 13 155€
         ✅ ÉGAL!
```

---

## 📈 Visualisation complète

### Étape par étape

```
OP 1 (Ronan) — CA 10k:
Ronan:   ████ 8 770€ → vers asso
Johann:  
───────────────────────

OP 2 (Johann) — CA 5k:
Ronan:   ████████ 8 770€
Johann:  ██ 4 385€ → vers asso
───────────────────────

OP 3 (Ronan) — CA 15k:
Ronan:   ████████████████ 21 925€ → vers asso
Johann:  ████ 4 385€
───────────────────────

REDISTRIBUTION (asso donne 8 770€ à Johann):
Ronan:   █████████ 13 155€ ✅
Johann:  █████████ 13 155€ ✅
```

---

## 🔑 Points clés

✅ **Chacun déclare 100% du CA réel** → Pas de "société de fait"  
✅ **L'association gère la redistribution** → Légal et transparent  
✅ **Résultat final équitable** → 50/50 exact malgré les écarts  
✅ **Flexible**: Fonctionnne avec n'importe quel ordre/montant d'opérations  

---

## 💡 Variation: Et si Johann fait une grosse opération?

### Cas alternatif: Johann rattrape Ronan

**Mêmes opérations, ordre différent** :

```
OP 1 (Ronan) — 10k:
Ronan:   ████ 8 770€
Johann:  
───────────────────────

OP 2 (Johann) — 15k:
Ronan:   ████ 8 770€
Johann:  ███████████ 13 155€ → RATTRAPAGE!
───────────────────────
Écart réduit: 13 155€ - 8 770€ = 4 385€

OP 3 (Ronan) — 5k:
Ronan:   ██████ 12 155€
Johann:  ███████████ 13 155€ → Johann maintenant en avance!
───────────────────────

REDISTRIBUTION:
Ronan:   █████████ 12 885€
Johann:  █████████ 12 440€
         ✅ Quasi-égal (reste solde petit)
```

---

## 📝 Règle générale

Pour **n opérations** avec **CA₁, CA₂, ... CAₙ** :

1. Chacun déclare son CA réel à l'URSSAF
2. Chacun verse son net à l'asso: `Bénéfice = CA × (1 - 0.123)`
3. L'asso calcule: `Écart = Max(Ronan, Johann) - Min(Ronan, Johann)`
4. L'asso redistribue: `Écart ÷ 2` à chacun

**Résultat** : Toujours 50/50 final, peu importe l'ordre/montants

---

**Dernière mise à jour** : 14 mai 2026  
**Concept** : Article 31 des statuts — Compte courant équitable

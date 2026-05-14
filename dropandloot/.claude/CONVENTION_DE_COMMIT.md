# Conventions de commit — Symfony + Sulu

Format obligatoire pour tous les commits.

---

## Format

```txt
<emoji> <type>(scope): <description courte>
```

Corps optionnel (après ligne vide) pour expliquer le **pourquoi**, jamais le **quoi**.

---

## Types & emojis

| Emoji | Type | Quand |
|-------|------|-------|
| ✨ | `feat` | Nouvelle fonctionnalité (controller, service, page Sulu) |
| 🔧 | `fix` | Correction de bug |
| 📋 | `docs` | Documentation (README, guides, comments) |
| 🎨 | `style` | CSS, Twig templates, formatage |
| ♻️ | `refactor` | Restructuration sans changement comportement |
| ✅ | `test` | Tests unitaires, fixtures |
| 🛠️ | `chore` | Config, dépendances, build |
| 🚀 | `perf` | Optimisation (cache, requêtes DB) |
| 🔒 | `security` | Failles, authentification, validation |
| 🔄 | `ci` | GitHub Actions, workflows |
| ⏪ | `revert` | Annulation d'un commit |

---

## Scope

Identifie précisément ce qui change.

**Exemples** :

```txt
feat(admin): Ajouter gestion des utilisateurs
fix(api): Corriger pagination endpoints
docs(setup): Ajouter guide installation Docker
style(template): Refactoriser header.html.twig
refactor(service): Extraire logique UserService
test(controller): Tests endpoint /api/users
chore(composer): Mettre à jour Sulu 3.0.2
perf(query): Ajouter eager loading relations
security(auth): Valider tokens JWT
ci(github): Ajouter workflow tests automatiques
```

---

## Règles non négociables

- Emoji **toujours** présent
- Scope **toujours** présent (jamais `feat(misc)` ou `fix(various)`)
- Description courte, impérative (pas "Ajoute..." mais "Ajouter...")
- Commits atomiques — un changement logique par commit
- Jamais `git add .` — par fichier/scope explicite
- Pas de `Co-Authored-By: Claude`

---

## Exemples valides

```
✨ feat(admin): Ajouter dashboard utilisateurs
🔧 fix(api): Corriger 404 sur endpoint /users/:id
📋 docs(readme): Expliquer structure dossiers
🎨 style(template): Migrer CSS en Tailwind
♻️ refactor(service): Simplifier UserRepository
✅ test(controller): Couvrir API authentication
🛠️ chore(composer): Mettre à jour dependances
🚀 perf(query): Utiliser select() pour réduire load
🔒 security(password): Ajouter validation force
🔄 ci(github): Ajouter matrix PHP 8.2/8.3
```

---

## Corps du commit (optionnel)

Utilisé pour des changements complexes:

```
✨ feat(admin): Ajouter gestion des utilisateurs

Ajoute interface admin pour CRUD utilisateurs avec:
- Création/édition de comptes
- Assignation de rôles
- Validation emails

Closes #123
```

---

**Référence rapide** :

```
<emoji> <type>(scope): description courte
```

C'est tout ce qu'il faut retenir!

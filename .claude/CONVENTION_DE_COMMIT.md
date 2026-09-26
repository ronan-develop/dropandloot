# Conventions de commit — Drop & Loot

> ⛔ **JAMAIS de commit direct sur `main`.**
> Toujours : `git checkout -b <branche>` → commits → PR → merge.
> Vérifier la branche courante avant tout `git add`.

---

## Format

```txt
<emoji> <type>(<scope>): <description courte>
```

Corps optionnel (après une ligne vide) pour expliquer le *pourquoi*, jamais le *quoi*.

---

## Types & emojis

| Emoji | Type | Quand |
| --- | --- | --- |
| ✨ | `feat` | Nouvelle fonctionnalité, nouveau document |
| 🔧 | `fix` | Correction de bug, erreur dans les docs |
| 📋 | `docs` | Documentation, guides, explications |
| 💰 | `budget` | Budget, coûts, simulations financières |
| ⚖️ | `legal` | Aspects légaux, statuts, règlements |
| 🎮 | `game-design` | Stratégie gaming, confiance, obstacles |
| 🔒 | `security` | Certifications, RGPD, assurances |
| ♻️ | `refactor` | Restructuration sans changement de contenu |
| 🎨 | `style` | Formatage markdown, linting |
| ✅ | `test` | Tests, validations, vérifications |
| 🛠️ | `chore` | Outillage, config, .gitignore |
| ⏪ | `revert` | Annulation d'un commit |
| 🚧 | `wip` | Travail en cours — interdit sur `main` |

---

## Scope

Le scope identifie précisément ce qui a changé. Jamais générique.

**Documentation :**

```txt
feat(statuts): Article 31 compte courant
fix(synthese): Corriger les budgets minimums
docs(readme): Ajouter guide de navigation
budget(certifications): Détailler tous les coûts
legal(rgpd): Audit de conformité
game-design(confiance): Solutions obstacles gaming
```

**Configuration & outils :**

```txt
chore(.gitignore): Exclure .env.local
style(markdownlint): Formater tous les MD
```

---

## Règles non négociables

- Emoji **toujours** présent
- Scope **toujours** présent — jamais `feat(file)` ou `feat(misc)`
- Commits **atomiques** — un groupe logique par commit, jamais `git add .`
- Markdownlint clean avant tout commit
- Jamais de commit direct sur `main`
- Secrets et `.env.local` exclus — vérifier le diff avant staging
- Pas de `Co-Authored-By: Claude`

---

## Workflow

```bash
git checkout main && git pull
git checkout -b docs/mon-feature

# Stager par groupe logique
git add 01_STATUTS_Maison_DropLoot.md
git commit -m "⚖️ legal(statuts): Ajouter Article 31 compte courant"

# Autre groupe logique
git add 02_SYNTHESE_MASTER.md
git commit -m "💰 budget(synthese): Ajouter budgets minimums et optionnels"

# Créer PR
git push -u origin docs/mon-feature
gh pr create --title "..." --body "..."
```

---

## Limites — confirmation obligatoire avant de

- `git push`
- Merger dans `main`
- Ouvrir / fermer une PR
- Supprimer une branche ou des fichiers

**Le user décide de l'ouverture des PRs et des merges.**

---

## Référence rapide

Format simple à retenir :

```text
<emoji> <type>(scope): description courte
```

Exemples valides :

- ✨ feat(statuts): Article 31 redistribution équitable
- 🔧 fix(synthese): Corriger total budget
- 📋 docs(readme): Guide complet de lecture
- 💰 budget(certifications): Coûts RGPD et assurance
- 🎮 game-design(confiance): Solutions obstacles gaming

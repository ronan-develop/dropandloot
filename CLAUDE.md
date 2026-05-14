# CLAUDE.md — Drop & Loot

> Ce fichier est chargé automatiquement par Claude Code à chaque session.
> Il contient les règles absolues du projet.

---

## ⛔ Règles non négociables

### Branches

**Jamais de commit direct sur `main`.**

Workflow obligatoire :

1. `git branch --show-current` — vérifier la branche AVANT tout `git add`
2. Si `main` → `git checkout -b <type>/<nom-explicite>` avant de continuer
3. Commits sur la branche → PR → merge

### ⛔ Contenu autorisé sur main

**Seule la documentation peut être sur `main`** :

- Fichiers Markdown (`.md`) dans `/business/` — statuts, budgets, stratégie, présentation
- Documentation de configuration dans `/.claude/` — conventions, checklists
- Fichiers de configuration (`CLAUDE.md`, `README.md`, `.gitignore`)

**INTERDIT sur `main`** :

- Code (Python, JavaScript, HTML, CSS, etc.)
- Dépendances (requirements.txt, package.json, etc.)
- Configuration de déploiement ou secrets
- Tout fichier non-documentation

Pour du code ou des dépendances : créer une branche `dev/` ou `feature/` et valider avec le user avant merge.

### Commits

- Format obligatoire : `<emoji> <type>(<scope>): <description>` — voir `.claude/CONVENTION_DE_COMMIT.md`
- Jamais `git add .` — toujours par fichier ou groupe logique explicite
- Corps optionnel pour expliquer le **pourquoi**, jamais le **quoi**
- Jamais de `Co-Authored-By: Claude` dans les messages

### Markdownlint

- Tous les fichiers MD doivent être lint-clean (markdownlint)
- MD032, MD040, MD031 strictement respectés
- Pas de lignes > 80 caractères (sauf tableaux)

---

## Documentation du projet

Toute la doc de structure est dans `.claude/`. Lire `CONVENTION_DE_COMMIT.md` avant tout commit.

---

## Stack technique

- **Outils** : Markdown, Git, GitHub
- **Certifications** : Huissier, RC, RGPD, Estago
- **Domaine** : O2Switch (lenouvel.me partagé avec dropandloot.fr)
- **Structure** : Association loi 1901 + 2 auto-entrepreneurs

---

## Limites — confirmation obligatoire avant de

- `git push`
- Merger dans `main`
- Ouvrir / fermer une PR
- Supprimer une branche ou des fichiers non triviaux

**Le user décide de l'ouverture des PRs et des merges.**

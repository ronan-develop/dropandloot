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

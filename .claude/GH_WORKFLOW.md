# GitHub Workflow — Drop & Loot

Processus standard pour tous les changements.

---

## Workflow strict

### 1️⃣ Vérifier la branche
```bash
git branch --show-current
```
Si `main` → créer une branche avant de commencer.

### 2️⃣ Créer une branche
```bash
git checkout -b docs/description-courte
# ou
git checkout -b feat/description-courte
```

### 3️⃣ Faire les modifications
- Éditer les fichiers nécessaires
- Vérifier le linting Markdown (`markdownlint *.md`)
- Vérifier le statut : `git status`

### 4️⃣ Staging par groupe logique
```bash
git add fichier1.md fichier2.md
git commit -m "✨ feat(scope): description courte"

git add fichier3.md
git commit -m "📋 docs(scope): description courte"
```

**Jamais** `git add .`

### 5️⃣ Vérifier le diff
```bash
git log --oneline -3
git diff origin/main..HEAD
```

### 6️⃣ Pousser et créer une PR
```bash
git push -u origin docs/description-courte
gh pr create --title "Description courte" --body "..."
```

### 7️⃣ Merger après validation
```bash
gh pr merge --squash
```

---

## Format PR

```
## Titre court (< 70 caractères)

## Description
- Point 1
- Point 2
- Point 3

## Vérification
- [x] Markdownlint clean
- [x] Pas de secrets en dur
- [x] Budget/chiffres vérifiés
```

---

## Règles

- ❌ Jamais de commit direct sur `main`
- ❌ Jamais `git add .`
- ❌ Jamais `git push --force`
- ✅ Toujours créer une branche
- ✅ Toujours une PR avant merge
- ✅ Toujours vérifier le diff avant staging

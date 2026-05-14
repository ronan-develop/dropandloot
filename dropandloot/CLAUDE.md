# CLAUDE.md — Symfony + Sulu CMS

> Ce fichier est chargé automatiquement par Claude Code à chaque session.
> Règles absolues pour le développement du CMS Sulu.

---

## ⛔ Règles non négociables

### Branches

**Jamais de commit direct sur `main`.**

Workflow obligatoire:

1. `git branch --show-current` — vérifier la branche AVANT tout `git add`
2. Si `main` → `git checkout -b <type>/<nom-explicite>` avant de continuer
3. Commits sur feature branch → PR → review → merge

**Convention de nommage branches** :

- `feature/nom-descriptif` — nouvelles fonctionnalités
- `fix/nom-du-bug` — corrections
- `refactor/nom-du-refactor` — refactorisation
- `docs/nom-du-doc` — documentation

### ⛔ Contenu autorisé sur main

**Autorisé** :

- Code Symfony/Sulu (PHP, Twig, fixtures)
- Documentation (README, INSTALL, guides)
- Configuration (docker-compose, .env.example)
- Tests et fixtures

**INTERDIT** :

- `.env.local` ou secrets
- `vendor/` ou `node_modules/`
- Fichiers compilés (`var/cache/`, `public/build/`)
- Credentials ou tokens API

### Commits

Format obligatoire : `<emoji> <type>(scope): <description>`

Voir `.claude/CONVENTION_DE_COMMIT.md` pour la liste complète.

**Règles** :

- Jamais `git add .` — toujours par fichier/scope explicite
- Commits atomiques — un changement logique par commit
- Corps optionnel pour expliquer le **pourquoi**, jamais le **quoi**
- Jamais de `Co-Authored-By: Claude`

### Code quality

- **Tests** : PHPUnit pour logique métier, fixtures Sulu pour contenu
- **Linting** : `php-cs-fixer` (PSR-12)
- **Static analysis** : `phpstan` (level 5 minimum)
- **Sulu validation** : Tester l'admin panel après chaque changement

### Markdownlint

- Tous les fichiers MD doivent être lint-clean
- MD032, MD040, MD031 strictement respectés
- Max 80 caractères par ligne (sauf tableaux/code)

---

## 🏗️ Stack technique

- **Framework** : Symfony 7 (LTS)
- **CMS** : Sulu 3.0
- **Database** : MySQL 8.0+ (recommandé)
- **PHP** : 8.2+
- **Node** : 18+ (pour assets)
- **Package manager** : Composer 2, npm/yarn
- **Hosting** : O2Switch (ou compatible)

---

## 📁 Structure du projet

```txt
/
├── .claude/              # Configuration du projet
├── src/                  # Code PHP (Controllers, Entity, etc.)
├── templates/            # Templates Twig (pages, admin)
├── public/              # Assets publics (CSS, JS, images)
├── var/                 # Fichiers générés (cache, logs)
├── config/              # Configuration Symfony/Sulu
├── migrations/          # Migrations base de données
├── tests/               # Tests PHPUnit
├── docker-compose.yml   # Stack local (MySQL, Redis)
├── .env.example         # Variables d'environnement (exemple)
├── composer.json        # Dépendances PHP
├── package.json         # Dépendances JS
└── CLAUDE.md            # Règles du projet (ce fichier)
```

---

## 🚀 Workflow

### Avant de coder

```bash
git checkout main && git pull
git checkout -b feature/ma-feature
```

### Pendant le dev

```bash
# Installer dépendances (première fois)
composer install
npm install

# Démarrer localement
docker-compose up -d
symfony server:start

# Tests
php bin/phpunit
php-cs-fixer fix src/
phpstan analyse src/
```

### Avant de commiter

```bash
# Vérifier la branche
git branch --show-current

# Linter et tester
php-cs-fixer fix src/
phpstan analyse src/
php bin/phpunit

# Commit atomique
git add src/Controller/MonController.php
git commit -m "✨ feat(admin): Ajouter page gestion utilisateurs"

# Autre groupe logique
git add templates/admin/users.html.twig
git commit -m "🎨 style(admin): Template gestion utilisateurs"

# Push et PR
git push -u origin feature/ma-feature
gh pr create --title "Ajouter gestion utilisateurs" --body "..."
```

---

## 🛑 Limites — confirmation obligatoire avant de

- `git push` — vérifier la branche et commits
- Merger dans `main` — attendre review + tests verts
- Supprimer une branche ou des fichiers
- Déployer sur production

**Toi seul décide des merges sur main.**

---

## 📖 Ressources

- [Symfony 7 Docs](https://symfony.com/doc/7.0/)
- [Sulu Admin Panel](https://docs.sulu.io/en/2.5/book/getting-started/)
- [Sulu API](https://docs.sulu.io/en/2.5/book/getting-started-api/)

---

**Dernière mise à jour** : 14 mai 2026

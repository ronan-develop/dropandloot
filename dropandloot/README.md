# Symfony + Sulu CMS

Site marketing modern basé sur Symfony 7 + Sulu 3.0 CMS.

---

## 🚀 Quick Start

```bash
# 1. Clone et setup
git clone <repo> symfony-sulu && cd symfony-sulu
cp .env.example .env.local

# 2. Docker + dépendances
docker-compose up -d
composer install && npm install

# 3. Base de données
php bin/console doctrine:migrations:migrate
php bin/console doctrine:fixtures:load

# 4. Start
symfony server:start
```

**Accès** :
- Frontend: http://localhost:8000
- Admin: http://localhost:8000/admin (admin / password)

---

## 📖 Documentation

Toute la documentation se trouve dans `.claude/`:

- **[CLAUDE.md](CLAUDE.md)** — Règles absolues (branching, commits, code quality)
- **[.claude/CONVENTION_DE_COMMIT.md](.claude/CONVENTION_DE_COMMIT.md)** — Format commits
- **[.claude/SETUP_LOCAL.md](.claude/SETUP_LOCAL.md)** — Installation complète
- **[.claude/PROJECT_OVERVIEW.md](.claude/PROJECT_OVERVIEW.md)** — Architecture du projet
- **[.claude/DEPLOY_O2SWITCH.md](.claude/DEPLOY_O2SWITCH.md)** — Déploiement production
- **[.claude/INDEX.md](.claude/INDEX.md)** — Navigation complète

---

## 🏗️ Stack

| Tech | Version | Rôle |
|------|---------|------|
| Symfony | 7 (LTS) | Framework web |
| Sulu | 3.0 | CMS + Admin |
| PHP | 8.2+ | Langage serveur |
| MySQL | 8.0+ | Base de données |
| Node | 18+ | Assets (JS, CSS) |
| Docker | Compose | Environnement local |

---

## 📁 Structure

```txt
/
├── .claude/              # Configuration du projet
├── src/                  # Code PHP
├── templates/            # Templates Twig
├── public/              # Assets publics
├── config/              # Configuration Symfony/Sulu
├── migrations/          # Migrations DB
├── tests/               # Tests PHPUnit
├── docker-compose.yml   # Stack local
└── CLAUDE.md            # Règles du projet
```

---

## 💻 Development

```bash
# Tests
php bin/phpunit

# Linting
php-cs-fixer fix src/
phpstan analyse src/

# Build assets
npm run build
npm run watch
```

---

## 🚢 Deployment

Production prête pour O2Switch:

```bash
composer install --no-dev
php bin/console doctrine:migrations:migrate --env=prod
php bin/console cache:clear --env=prod
```

Voir [.claude/DEPLOY_O2SWITCH.md](.claude/DEPLOY_O2SWITCH.md) pour guide complet.

---

## ⚙️ Configuration

Lire **[CLAUDE.md](CLAUDE.md)** pour:
- Branching workflow (`feature/`, `fix/`, `refactor/`)
- Format commits obligatoire (`✨ feat(scope): description`)
- Règles de code quality
- Limites (push, merge, delete = confirmation)

---

## 📞 Support

- Symfony: https://symfony.com/doc/7.0/
- Sulu: https://docs.sulu.io/en/2.5/
- O2Switch: https://faq.o2switch.fr/

---

**Dernière mise à jour** : 14 mai 2026

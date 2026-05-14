# Setup local — Symfony + Sulu

Installation et configuration pour développement local.

---

## Prerequisites

- **PHP 8.2+**
- **Composer 2+**
- **MySQL 8.0+** (local ou distant)
- **Node 18+** (optionnel, pour assets custom)
- **Git**
- **Symfony CLI** (optionnel, recommandé)

---

## Installation (sans Docker)

```bash
# 1. Clone le projet
git clone <repo-url> symfony-sulu
cd symfony-sulu

# 2. Copier .env
cp .env.example .env.local

# 3. Configurer base de données dans .env.local
# Éditer DATABASE_URL avec tes identifiants MySQL local

# 4. Installer dépendances PHP
composer install

# 5. Setup base de données
php bin/console doctrine:database:create
php bin/console doctrine:migrations:migrate
php bin/console doctrine:fixtures:load

# 6. (Optionnel) Build assets
npm install
npm run build

# 7. Démarrer le serveur
symfony server:start
# Ou sans Symfony CLI:
php -S localhost:8000 -t public/
```

---

## Accès local

| Service | URL | Credentials |
|---------|-----|------------------|
| **Frontend** | `http://localhost:8000` | — |
| **Admin Sulu** | `http://localhost:8000/admin` | admin / password |

---

## Variables d'environnement (.env.local)

Pour développement local:

```bash
APP_ENV=dev
APP_DEBUG=true
APP_SECRET=test_secret_key_change_me
DATABASE_URL="mysql://root:password@localhost:3306/sulu_dev?serverVersion=8.0"
SULU_ADMIN_EMAIL=admin@example.com
```

⚠️ **Important** : `.env.local` ne doit JAMAIS être committée (voir `.gitignore`)

---

## Commandes courantes

```bash
# Symfony console
php bin/console              # Lister toutes les commandes

# Database
php bin/console doctrine:database:create
php bin/console doctrine:migrations:migrate
php bin/console doctrine:fixtures:load

# Assets
npm run build                # Production build
npm run watch                # Watch mode développement
npm run dev-server          # Dev server avec HMR

# Tests
php bin/phpunit             # Lancer les tests
php-cs-fixer fix src/      # Linting PHP
phpstan analyse src/        # Static analysis

# Sulu-specific
php bin/console sulu:build  # Build admin interface
php bin/console cache:clear # Clear Symfony cache
```

---

## Troubleshooting

### "Connection refused" sur MySQL

```bash
# Vérifier la connection
php bin/console doctrine:query:sql "SELECT 1"

# Vérifier les credentials dans .env.local
cat .env.local | grep DATABASE_URL
```

### "Asset build failed"

```bash
# Réinstaller node_modules
rm -rf node_modules
npm install
npm run build
```

### "Database migration failed"

```bash
# Vérifier le statut
php bin/console doctrine:migrations:status

# Rollback
php bin/console doctrine:migrations:migrate prev

# Re-apply
php bin/console doctrine:migrations:migrate
```

---

## Next steps

- Lire [DEPLOY_O2SWITCH.md](DEPLOY_O2SWITCH.md) pour déployer en production
- Consulter la [documentation Sulu](https://docs.sulu.io)

---

**Dernière mise à jour** : 14 mai 2026

# Deploy O2Switch — Symfony + Sulu

Guide de déploiement sur hébergement mutualisé O2Switch.

---

## Prerequisites

- Compte O2Switch avec SSH + Git activé
- Domaine pointant vers O2Switch
- PHP 8.2+ activé dans cPanel
- MySQL 8.0+ disponible
- SSH key configurée

---

## Étapes de déploiement

### 1. Préparer le serveur O2Switch

```bash
# SSH vers O2Switch
ssh username@lenouvel.me

# Créer répertoire pour le projet
mkdir -p ~/symfony-sulu
cd ~/symfony-sulu

# Sélectionner PHP 8.2 (cPanel)
# → Utiliser "PHP Selector" pour version correcte

# Vérifier versions
php -v        # 8.2+ requis
composer -v   # Composer 2
```

### 2. Cloner le repository

```bash
# Clone depuis GitHub
git clone https://github.com/ton-repo/symfony-sulu.git .

# Ou pull si déjà cloné
git pull origin main
```

### 3. Installer dépendances

```bash
# PHP dependencies
composer install --no-dev --optimize-autoloader

# Node dependencies (si assets custom)
npm install
npm run build
```

### 4. Configuration environnement

```bash
# Créer .env.local
nano .env.local
```

Contenu `.env.local` pour production:

```bash
APP_ENV=prod
APP_DEBUG=false
DATABASE_URL="mysql://user:password@localhost/sulu_prod"
MAILER_DSN="smtp://localhost:25"
SULU_ADMIN_EMAIL=admin@domain.com
TRUSTED_HOSTS=^(domain\.com|www\.domain\.com)$
```

### 5. Setup base de données

```bash
# Créer la DB (depuis cPanel ou SSH)
mysql -u user -p

# Migrer le schéma
php bin/console doctrine:migrations:migrate

# Charger fixtures (si needed)
php bin/console doctrine:fixtures:load --no-interaction
```

### 6. Permissions et cache

```bash
# Permissions correctes
chmod 755 .
chmod 644 public/.htaccess
chmod 777 var/cache var/log

# Vider cache
php bin/console cache:clear --env=prod
```

### 7. Configuration .htaccess (si Apache)

```apache
# public/.htaccess

<IfModule mod_rewrite.c>
    RewriteEngine On
    RewriteBase /
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteRule ^(.*)$ index.php [QSA,L]
</IfModule>
```

### 8. Vérifier installation

Accéder au domaine:

```
https://domain.com       # Frontend
https://domain.com/admin # Admin Sulu
```

---

## Post-déploiement

### SEO & Performance

```bash
# Générer sitemap
php bin/console sulu:web-spaces:dump

# Activer cache (production)
# → Configuration Redis dans .env si disponible
```

### Monitoring

- Vérifier logs: `tail -f var/log/prod.log`
- Vérifier permissions: `ls -la var/`
- Vérifier DB connection: `php bin/console doctrine:query:sql "SELECT 1"`

### SSL/HTTPS

O2Switch fournit Let's Encrypt:

- Activer HTTPS dans cPanel
- Forcer HTTPS dans `.env`: `SULU_ADMIN_SCHEME=https`

---

## Workflow CI/CD (optionnel)

Pour déploiement automatique via GitHub Actions:

```yaml
# .github/workflows/deploy.yml

name: Deploy to O2Switch

on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3

      - name: Deploy via SSH
        uses: appleboy/ssh-action@master
        with:
          host: ${{ secrets.HOST }}
          username: ${{ secrets.USERNAME }}
          key: ${{ secrets.SSH_KEY }}
          script: |
            cd ~/symfony-sulu
            git pull origin main
            composer install --no-dev
            php bin/console cache:clear --env=prod
```

---

## Troubleshooting

### "500 Internal Server Error"

```bash
# Vérifier logs
tail var/log/prod.log

# Vérifier permissions
chmod -R 777 var/
```

### "Database connection refused"

```bash
# Vérifier credentials dans .env.local
php bin/console doctrine:query:sql "SELECT 1"

# Vérifier user MySQL existe
mysql -u user -p
```

### "Admin panel not accessible"

```bash
# Rebuild Sulu
php bin/console sulu:build prod

# Vérifier permissions assets
chmod -R 755 public/
```

---

## Maintenance

### Mise à jour Sulu

```bash
git pull origin main
composer update sulu/*
php bin/console doctrine:migrations:migrate
php bin/console cache:clear --env=prod
```

### Backup base de données

```bash
# Mysqldump
mysqldump -u user -p database_name > backup.sql

# Ou depuis cPanel → Backups
```

---

## Support O2Switch

- Documentation: https://faq.o2switch.fr/
- SSH Guide: https://faq.o2switch.fr/guides/ssh/
- PHP Selector: https://faq.o2switch.fr/guides/php/changer-version-php-et-php-ini/

---

**Dernière mise à jour** : 14 mai 2026

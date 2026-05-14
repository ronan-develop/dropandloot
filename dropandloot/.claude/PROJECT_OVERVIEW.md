# PROJECT_OVERVIEW — Symfony + Sulu CMS

Vue d'ensemble du projet CMS.

---

## 🎯 Objectif

Créer un **CMS marketing/blog** moderne basé sur Symfony 7 + Sulu 3.0:

- Interface admin intuitive pour gestion contenu (pages, blog, média)
- Site frontend performant (headless possible)
- Déploiement simple sur O2Switch
- Maintenance facile pour non-tech

---

## 🏗️ Stack technique

| Composant | Version | Rôle |
|-----------|---------|------|
| **Symfony** | 7.0 (LTS) | Framework web |
| **Sulu** | 3.0 | CMS + Admin panel |
| **PHP** | 8.2+ | Langage serveur |
| **MySQL** | 8.0+ | Base de données |
| **Node** | 18+ | Assets (JS, CSS) |
| **Docker** | Compose | Environnement local |

---

## 📁 Structure

```txt
/
├── .claude/                    # Config projet (conventions, checklists)
├── src/
│   ├── Controller/            # Controllers HTTP
│   ├── Entity/               # Entités Doctrine
│   ├── Repository/           # Requêtes DB
│   ├── Service/              # Logique métier
│   └── Sulu/                 # Customization Sulu
├── templates/
│   ├── admin/                # Templates admin (si custom)
│   ├── pages/                # Pages frontend
│   └── base.html.twig        # Layout principal
├── public/
│   ├── assets/               # Fichiers statiques compilés
│   └── index.php             # Entry point
├── config/
│   ├── packages/             # Config services
│   ├── routes.yaml           # Routage
│   └── sulu.yaml             # Config Sulu
├── migrations/               # Migrations Doctrine
├── tests/
│   ├── Unit/                 # Tests unitaires
│   └── Functional/           # Tests intégration
├── docker-compose.yml        # Stack local
├── .env.example              # Vars d'environnement (exemple)
└── CLAUDE.md                 # Règles du projet
```

---

## 🚀 Features principales

### Sulu Admin Panel

- ✅ Gestion pages avec éditeur visuel
- ✅ Blog (articles, catégories, commentaires)
- ✅ Gestion média (images, documents)
- ✅ Utilisateurs et permissions
- ✅ SEO (meta, sitemap, robots.txt)
- ✅ Prévisualisation

### Frontend

- ✅ Pages statiques (qui sommes-nous, contact)
- ✅ Blog avec pagination
- ✅ Système de catégories
- ✅ Moteur de recherche (optionnel)
- ✅ Responsive design

### Technique

- ✅ API REST (Sulu natif)
- ✅ Caching (Redis optionnel)
- ✅ Security (authentication, CSRF, XSS)
- ✅ Tests automatisés (PHPUnit)
- ✅ CI/CD (GitHub Actions)

---

## 📊 Workflow développement

### Local (Docker)

```bash
docker-compose up -d
symfony server:start
# Admin: http://localhost:8000/admin
# Frontend: http://localhost:8000
```

### Tests

```bash
php bin/phpunit                    # Tests unitaires
php-cs-fixer fix src/             # Linting
phpstan analyse src/               # Static analysis
```

### Deploy O2Switch

```bash
git push origin feature/ma-feature
# → PR review
# → Merge sur main
# → Deploy SSH vers O2Switch
```

---

## 🎯 Timeline

| Phase | Semaine | Activité |
|-------|---------|----------|
| **Setup** | 1 | Symfony 7 + Sulu 3.0 initialization |
| **Foundation** | 2-3 | Entités Doctrine, fixtures, migrations |
| **Frontend** | 4-5 | Templates Twig, pages statiques, blog |
| **Polish** | 6 | Tests, SEO, optimisations |
| **Deploy** | 7 | O2Switch setup, domaine, SSL |
| **Launch** | 8 | 🚀 Mise en ligne |

---

## 📖 Documentation

- **CLAUDE.md** — Règles absolues du projet
- **.claude/CONVENTION_DE_COMMIT.md** — Format des commits
- **.claude/SETUP_LOCAL.md** — Installation locale
- **.claude/DEPLOY_O2SWITCH.md** — Déploiement production

---

**Dernière mise à jour** : 14 mai 2026

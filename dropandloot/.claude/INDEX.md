# INDEX — Symfony + Sulu Configuration

Navigation complète de la documentation de configuration.

---

## 🎯 À lire d'abord

### En début de session

1. **[CLAUDE.md](../CLAUDE.md)** — Règles absolues du projet (5 min)
2. **[CONVENTION_DE_COMMIT.md](CONVENTION_DE_COMMIT.md)** — Format des commits (3 min)
3. **[SETUP_LOCAL.md](SETUP_LOCAL.md)** — Installation locale (10 min)

### Pour comprendre le projet

4. **[PROJECT_OVERVIEW.md](PROJECT_OVERVIEW.md)** — Vue d'ensemble (10 min)
5. **[DEPLOY_O2SWITCH.md](DEPLOY_O2SWITCH.md)** — Déploiement production (15 min)

---

## 📋 Documentation par thème

### Configuration & Conventions

- **[CLAUDE.md](../CLAUDE.md)** — Règles du projet, branching, commits
- **[CONVENTION_DE_COMMIT.md](CONVENTION_DE_COMMIT.md)** — Format commits avec emojis
- **[PROJECT_OVERVIEW.md](PROJECT_OVERVIEW.md)** — Architecture et structure

### Development

- **[SETUP_LOCAL.md](SETUP_LOCAL.md)** — Installation locale avec Docker
- Symfony console commands (voir SETUP_LOCAL.md)
- Testing & linting (phpunit, php-cs-fixer, phpstan)

### Production

- **[DEPLOY_O2SWITCH.md](DEPLOY_O2SWITCH.md)** — Déploiement sur O2Switch
- Configuration .env pour production
- Monitoring et maintenance

---

## 🎯 Workflows courants

### "Je démarre le développement"

1. Lire [CLAUDE.md](../CLAUDE.md)
2. Lire [SETUP_LOCAL.md](SETUP_LOCAL.md)
3. `docker-compose up -d && composer install && npm install`

### "Je vais commiter mon code"

1. Lire [CONVENTION_DE_COMMIT.md](CONVENTION_DE_COMMIT.md)
2. `git checkout -b feature/ma-feature`
3. Faire les modifications
4. Linter : `php-cs-fixer fix src/` + `phpstan analyse src/`
5. Tester : `php bin/phpunit`
6. Commiter: `git commit -m "✨ feat(scope): description"`

### "Je dois déployer en production"

1. Lire [DEPLOY_O2SWITCH.md](DEPLOY_O2SWITCH.md)
2. Préparer `.env.local` pour production
3. SSH vers O2Switch et suivre les étapes
4. Tester accès frontend + admin

### "J'ajoute une nouvelle page Sulu"

1. Admin panel → Pages → Créer
2. Ajouter contenu dans l'éditeur Sulu
3. Créer template Twig correspondant si needed
4. Publier et tester frontend

---

## 📁 Fichiers clés

| Fichier | Contenu |
|---------|---------|
| **CLAUDE.md** | Règles absolues, branching, commits |
| **CONVENTION_DE_COMMIT.md** | Format des commits (obligatoire) |
| **PROJECT_OVERVIEW.md** | Vue d'ensemble, stack, features |
| **SETUP_LOCAL.md** | Installation locale Docker |
| **DEPLOY_O2SWITCH.md** | Déploiement production O2Switch |

---

## 🔗 Ressources externes

- [Symfony 7 Documentation](https://symfony.com/doc/7.0/)
- [Sulu 3.0 Documentation](https://docs.sulu.io/en/2.5/)
- [O2Switch FAQ](https://faq.o2switch.fr/)
- [Composer Documentation](https://getcomposer.org/doc/)

---

**Dernière mise à jour** : 14 mai 2026

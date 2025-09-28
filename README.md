# umbra-localization-service

Service d'internationalisation et traductions

## 🚀 Démarrage Rapide

### Prérequis
- Python 3.11+
- PostgreSQL 15+
- Redis 7+

### Installation
```bash
# Installer les dépendances
make install

# Copier la configuration
cp .env.example .env

# Lancer le service
make run
```

### Avec Docker
```bash
# Environnement complet
make docker-dev

# Vérifier la santé
curl http://localhost:5007/health
```

## 🧪 Tests

```bash
# Tests simples
make test

# Tests avec couverture
make test-cov

# Qualité du code
make lint
make format
```

## 📡 API

### Endpoints

- `GET /health` - Vérification de santé du service
- `GET /locales` - Liste des locales disponibles
- `GET /translations/<locale>` - Toutes les traductions pour une locale
- `GET /translations/<locale>/<key>` - Traduction spécifique pour une clé

### Format des Réponses

```json
{
  "success": true,
  "data": {...},
  "message": "Description",
  "error": null,
  "meta": null
}
```

Les locales et traductions sont chargées depuis `data/translations.json`,
ce qui permet de les maintenir facilement dans le dépôt.

## 🔧 Développement

### Structure du Projet
```
umbra-localization-service/
├── src/                 # Code source
├── tests/              # Tests
├── migrations/         # Migrations DB
├── .github/           # CI/CD et templates
└── docker-compose.yml # Environnement local
```

### Commandes Utiles
```bash
make help              # Voir toutes les commandes
make dev               # Mode développement
make docker-dev        # Environnement Docker
make test-cov          # Tests avec couverture
```

## 🚀 Déploiement

Le service est automatiquement déployé via GitHub Actions sur push vers `main`.

### Variables d'Environnement

Voir `.env.example` pour la liste complète des variables.

## 🤝 Contribution

1. Créer une issue avec le template Codex
2. Créer une branche `feature/ISSUE-XXX-description`
3. Développer avec tests
4. Créer une Pull Request

## 📄 Licence

MIT License - voir [LICENSE](LICENSE)

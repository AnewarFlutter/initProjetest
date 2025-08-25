# Frontend Vue.js Application

Une application Vue.js 3 moderne développée avec TypeScript, Vite et Pinia, incluant une configuration complète de qualité de code et un pipeline CI/CD.

## 🚀 Technologies Utilisées

- **Frontend**: Vue.js 3 (Composition API) + TypeScript
- **Build Tool**: Vite avec plugins Vue DevTools
- **State Management**: Pinia
- **Routing**: Vue Router 4
- **Testing**: Vitest + Vue Test Utils + jsdom
- **Quality**: ESLint + Prettier + Husky + lint-staged
- **CI/CD**: GitHub Actions (à venir)

## 📁 Structure du Projet

```
frontend/
├── public/                 # Assets statiques
├── src/
│   ├── assets/            # CSS et ressources
│   ├── components/        # Composants réutilisables
│   │   ├── __tests__/     # Tests unitaires
│   │   └── icons/         # Composants d'icônes
│   ├── router/            # Configuration du routeur
│   ├── stores/            # Stores Pinia (state management)
│   └── views/             # Pages de l'application
├── tests/                 # Configuration des tests
├── dist/                  # Build de production
└── coverage/              # Rapports de couverture de code
```

## 🛠️ Installation et Configuration

### Prérequis
- Node.js ^20.19.0 || >=22.12.0
- npm ou yarn

### Installation

```bash
# Cloner le projet
git clone <repository-url>
cd frontend

# Installer les dépendances
npm install

# Vérifier l'installation
npm run type-check
```

## 🏃‍♂️ Scripts Disponibles

### Développement

```bash
# Serveur de développement avec hot-reload
npm run dev
# ➜ http://localhost:5173

# Vérification TypeScript
npm run type-check

# Tests en mode watch
npm run test:unit -- --watch
```

### Quality Assurance

```bash
# Linting avec correction automatique
npm run lint

# Vérification du formatage
npm run format:check

# Correction du formatage
npm run format

# Tests unitaires avec couverture
npm run test:unit -- --coverage
```

### Production

```bash
# Build de production (avec type-check)
npm run build

# Prévisualisation du build
npm run preview

# Build uniquement (sans type-check)
npm run build-only
```

## 🧪 Tests et Qualité

### Tests Unitaires
- Framework: **Vitest** avec **Vue Test Utils**
- Environnement: **jsdom**
- Couverture: **v8 provider**

```bash
# Tous les tests
npm run test:unit

# Tests spécifiques
npm run test:unit -- HelloWorld.spec.ts

# Tests avec couverture détaillée
npm run test:unit -- --coverage --reporter=verbose
```

### Hooks Git (Husky + lint-staged)
Les hooks s'exécutent automatiquement sur `git commit` :
- ESLint avec correction automatique
- Prettier pour le formatage
- Support: `.vue`, `.js`, `.ts`, `.css`, `.json`, `.md`

### CI/CD avec GitHub Actions
Le pipeline GitHub Actions sera configuré pour remplacer le pipeline Azure DevOps :

**Simulation locale du pipeline** :
```bash
# Étapes complètes de validation
npm ci
npm run format:check
npm run lint  
npm run type-check
npm run test:unit -- --coverage
npm run build
```

**Workflow prévu** :
- Quality Gate (format, lint, types, tests)
- Build de production avec artefacts
- Tests E2E avec Playwright/Cypress (futur)

## 🎯 Fonctionnalités Implémentées

### Architecture
- **Routing SPA**: Navigation fluide entre pages
- **State Management**: Store counter avec Pinia
- **Composants modulaires**: Architecture par composants
- **Responsive Design**: Interface adaptative

### Pages et Composants
- **HomeView** (`/`): Page d'accueil avec informations Vue.js
- **AboutView** (`/about`): Page à propos simple
- **HelloWorld**: Composant avec props typées
- **TheWelcome**: Grille d'informations écosystème Vue

### State Management
- **useCounterStore**: Exemple store avec état, computed et actions

## 🔧 Configuration IDE Recommandée

### VSCode + Extensions
```json
{
  "recommendations": [
    "Vue.volar",
    "ms-vscode.vscode-typescript-next",
    "esbenp.prettier-vscode",
    "dbaeumer.vscode-eslint"
  ]
}
```

**Important**: Désactiver Vetur si installé (conflit avec Volar)

### Support TypeScript pour fichiers .vue
Le projet utilise `vue-tsc` au lieu de `tsc` pour le support TypeScript complet des fichiers `.vue`.

## 📊 Métriques et Monitoring

### Couverture de Code
- **Objectif**: >80% de couverture
- **Rapports**: HTML, JSON, Cobertura
- **Exclusions**: `node_modules/`, `dist/`, `*.d.ts`, fichiers de test

### Performance
```bash
# Analyser la taille du bundle
npm run build && ls -lh dist/

# Audit avec outils externes (recommandé)
npx lighthouse http://localhost:5173 --view
```

## 🚨 Dépannage

### Problèmes Courants

**Tests qui échouent**
```bash
# Vérifier la configuration jsdom
npm run test:unit -- --reporter=verbose
```

**Erreurs TypeScript**
```bash
# Diagnostic complet
npm run type-check
```

**Problèmes de formatage**
```bash
# Auto-fix complet
npm run format && npm run lint
```

**Build qui échoue**
```bash
# Debug du build
npm run build -- --debug
```

## 📝 Personnalisation

### Configuration Vite
Voir [Vite Configuration Reference](https://vite.dev/config/)

### Ajout de nouvelles pages
1. Créer le composant dans `src/views/`
2. Ajouter la route dans `src/router/index.ts`
3. Ajouter les liens de navigation si nécessaire

### Ajout de stores Pinia
1. Créer le store dans `src/stores/`
2. Utiliser la Composition API avec `defineStore`
3. Importer dans les composants avec `useStore()`

## 🤝 Contribution

1. Fork le projet
2. Créer une branche feature (`git checkout -b feature/amazing-feature`)
3. Commit les changements (`git commit -m 'Add amazing feature'`)
4. Push la branche (`git push origin feature/amazing-feature`)
5. Ouvrir une Pull Request

Les hooks git garantissent la qualité du code avant chaque commit.

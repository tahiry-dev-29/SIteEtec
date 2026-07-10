# 🎓 ETEC University — Frontend

**Plateforme de gestion universitaire** — Frontend React moderne pour la gestion des étudiants, enseignants, cours, notes, présences et administrations de l'École de Technologie et de Commerce (ETEC).

---

## ✨ Aperçu

| Section | Description |
|---------|-------------|
| 🏠 **Pages publiques** | Accueil, formations, actualités, contact, admissions |
| 🔐 **Authentification** | Login/register rôles : Admin · Enseignant · Étudiant |
| 🧑‍💼 **Dashboard Admin** | Gestion des utilisateurs, formations, notes, emplois du temps, actualités, slides |
| 👨‍🏫 **Dashboard Enseignant** | Cours, évaluations, ressources, notifications, messagerie |
| 👨‍🎓 **Dashboard Étudiant** | Cours en ligne, notes, emploi du temps, progression, quiz |
| 🌐 **i18n** | Multilingue : Français · Anglais · Malagasy |

---

## 🧱 Architecture

```
src/
├── assets/              # Images, icônes, fonts
├── components/          # Composants réutilisables
├── config/              # i18n, providers
├── context/             # React context (theme, langue)
├── feature/             # Modules métier (auth, news, events)
├── hooks/               # Custom hooks (useTranslation)
├── layouts/             # Layouts des dashboards
│   ├── DashbordAdmin/
│   ├── DashboardEnseignants/
│   └── DashboardEtud/
├── locales/             # Traductions (en, fr, mg)
├── pages/               # Pages publiques
├── routes/              # Configuration des routes
├── services/            # API client (axios, ApiService)
├── styles/              # CSS global
├── types/               # TypeScript types
└── utils/               # Fonctions utilitaires
```

---

## 🛠️ Stack Technique

| Technologie | Version |
|-------------|---------|
| [React](https://react.dev) | 19.2 |
| [Vite](https://vitejs.dev) | 8.0 |
| [TypeScript](https://www.typescriptlang.org) | ~5.8 |
| [Tailwind CSS](https://tailwindcss.com) | 4.3 |
| [React Router](https://reactrouter.com) | 7.18 |
| [Axios](https://axios-http.com) | 1.18 |
| [Framer Motion](https://www.framer.com/motion) | 12.40 |
| [i18next](https://www.i18next.com) | 26.3 |
| [Recharts](https://recharts.org) | 3.9 |
| [Lucide React](https://lucide.dev) | 1.21 |
| [ESLint](https://eslint.org) | 10.3 |

---

## 🚀 Démarrage Rapide

### Prérequis

- **Node.js** ≥ 22
- **pnpm** ≥ 9 (ou npm/yarn)
- Backend ETEC en cours d'exécution (voir [backend](../backend))

### Installation

```bash
# Cloner le projet
git clone https://github.com/tahiry-dev-29/SIteEtec.git
cd SIteEtec/frontend

# Installer les dépendances
pnpm install

# Lancer le serveur de développement
pnpm dev
```

### Scripts Disponibles

| Commande | Description |
|----------|-------------|
| `pnpm dev` | Lance le serveur de développement (port 5173) |
| `pnpm build` | Build de production dans `dist/` |
| `pnpm preview` | Prévisualisation du build |
| `pnpm lint` | Vérification ESLint |

### Configuration

```env
# .env.local
VITE_API_GATEWAY_URL=http://localhost:8090
```

---

## 🔌 API & Backend

Le frontend communique avec l'**API Gateway** Spring Boot (port `8090`) qui route vers les microservices backend.

### Services Connectés

| Service | Endpoint Gateway | Microservice |
|---------|-----------------|--------------|
| Authentification | `/auth/**` | `utilisateur` |
| Admins | `/api/admins` | `admin` |
| Étudiants | `/api/etudiants` | `etudiant` |
| Enseignants | `/api/enseignants` | `enseignant` |
| Cours en ligne | `/api/cours` | `coursenligne` |
| Actualités | `/api/actualites` | `actualite` |
| Notes | `/api/notes` | `note` |
| Emplois du temps | `/api/emploiDuTemps` | `empoiDuTemps` |
| + 20 autres services | … | … |

> 📖 Voir le [README du backend](../backend/README.md) pour la liste complète.

---

## 🌍 Internationalisation

Le projet supporte 3 langues via `i18next` :

| Langue | Fichier |
|--------|---------|
| 🇫🇷 Français | `src/locales/fr/common.json` |
| 🇬🇧 English | `src/locales/en/common.json` |
| 🇲🇬 Malagasy | `src/locales/mg/common.json` |

Le changement de langue se fait via le `LanguageSwitcher` dans la `TopBar`.

---

## 👨‍💻 Développement

### Conventions

- **Composants** : Fonctionnels avec hooks (`useState`, `useEffect`)
- **State management** : Context API + localStorage pour l'auth
- **API** : `ApiService.ts` centralise tous les appels axios
- **Routes** : Définies dans `src/routes/AppRoutes.tsx`
- **Styles** : Tailwind CSS utility-first + CSS modules si nécessaire

### Organisation des Dashboards

```
layouts/
├── DashbordAdmin/          # CRUD complet pour chaque entité
├── DashboardEnseignants/   # Cours, évaluations, ressources
└── DashboardEtud/          # Cours en ligne, notes, progression
```

---

## 🤝 Contribution

1. Crée une branche feature : `git checkout -b feat/ma-feature`
2. Commit avec [Conventional Commits](https://www.conventionalcommits.org)
3. Ouvre une Pull Request vers `main`

---

## 📄 Licence

Projet privé — ETEC University

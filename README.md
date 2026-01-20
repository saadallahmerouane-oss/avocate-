# Lawyer Management Mobile App

Application web progressive (PWA) de gestion pour avocats / cabinets juridiques, optimisée pour une expérience mobile-first.  
Permet de suivre les audiences, les tâches urgentes, les dossiers clients, le calendrier judiciaire, les documents et l'activité récente.

Projet généré à partir d'un design Figma → Code (via un outil type Figma Make / Builder.io / Locofy) puis optimisé manuellement pour les performances (lazy-loading, memoization, code-splitting, etc.).

**Lien Figma original** :  
https://www.figma.com/design/cHOyIFU99NcwQ4UuuWNZqv/Lawyer-Management-Mobile-App

## Aperçu

<img src="https://via.placeholder.com/480x800/0f172a/ffffff?text=App+Screenshot+Home" alt="Écran d'accueil" width="320" />
<!-- Remplace par de vraies captures d'écran quand tu en auras -->

**Fonctionnalités principales :**
- Tableau de bord avec audiences du jour et tâches urgentes
- Détails complets d’un dossier (timeline des audiences, documents, notes)
- Calendrier judiciaire interactif avec sessions par jour
- Navigation bottom-bar fixe (Home / Cases / Calendar / Fees)
- Design moderne, responsive, mobile-first (max-width 480px simulé)
- Thème sombre élégant avec accents dorés (#d4af37)

## Technologies utilisées

- **Framework** : React 18 + Vite
- **Styling** : Tailwind CSS 4 (via @tailwindcss/vite)
- **Composants UI** : shadcn/ui style + Radix UI primitives + Lucide React (icons)
- **Autres** : React Hook Form, date-fns, class-variance-authority, clsx, etc.
- **Optimisations appliquées** :
  - Lazy loading + Suspense pour écrans lourds
  - React.memo sur les composants réutilisables
  - useCallback / useMemo pour éviter re-renders inutiles
  - Code splitting automatique via Vite

## Prérequis

- Node.js ≥ 18
- npm ou pnpm (recommandé)

## Installation

```bash
# 1. Cloner le repository
git clone https://github.com/tonusername/lawyer-management-app.git
cd lawyer-management-app

# 2. Installer les dépendances
npm install
# ou
pnpm install

# Mode développement (avec HMR)
npm run dev
# → Ouvre http://localhost:5173 (ou le port indiqué)

# Build production (génère dist/)
npm run build

# Prévisualiser le build
npm run preview

src/
├── app/
│   ├── App.tsx                 # Point d'entrée + gestion tabs & états globaux
│   └── components/
│       ├── CourtHearingCard.tsx
│       ├── UrgentTaskItem.tsx
│       ├── NavigationBar.tsx
│       ├── DocumentItem.tsx
│       ├── HearingTimelineItem.tsx
│       ├── SessionItem.tsx
│       ├── CaseDetails.tsx     # Écran détail dossier (lazy)
│       └── CalendarScreen.tsx  # Calendrier + sessions (lazy)
├── main.tsx
└── styles/
    └── index.css               # Imports Tailwind + globals

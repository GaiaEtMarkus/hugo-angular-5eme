# Partie 5 : Projet Final - Évaluation Pratique

## 🎯 Objectifs de l'évaluation

Cette partie constitue l'**évaluation finale** du module Angular. Les étudiants doivent démontrer leur maîtrise de tous les concepts vus dans les 4 parties précédentes à travers :

1. **Un projet libre** utilisant tous les concepts du cours
2. **Une démonstration vidéo** de 15-20 minutes maximum
3. **Une présentation technique** de l'architecture Angular

---

## 📋 Projet Final - Cahier des charges

### **🔧 Concepts obligatoires à implémenter :**

#### **1. Architecture et Structure**
- [ ] **Architecture DDD** : Organisation en features 
- [ ] **Composants standalone** : Utilisation exclusive (sauf si vraiment vous êtes pas chaud)
- [ ] **Structure de fichiers** : Respect de la convention Angular
- [ ] **Repository Git** : Création d'un repo dédié au projet
- [ ] **Commits conventionnels** : Un commit par feature/fix/refact

#### **2. Authentification et Autorisations**
- [ ] **Système de login/register** : Formulaires réactifs avec validation
- [ ] **Gestion des rôles** : User et Admin
- [ ] **AuthGuard** : Protection des routes utilisateur
- [ ] **AdminGuard** : Protection des routes admin
- [ ] **Persistance de session** : localStorage ou sessionStorage

#### **3. Formulaires et Validation**
- [ ] **Reactive Forms** : Utilisation de FormBuilder, FormGroup, FormControl
- [ ] **Validation personnalisée** : Au moins 1 validator custom
- [ ] **Gestion d'erreurs** : Affichage des erreurs en temps réel
- [ ] **Types stricts** : Pas de `any`, typage correct

#### **4. Routing et Navigation**
- [ ] **Lazy Loading** : Implémentation obligatoire
- [ ] **Route Guards** : Auth et Admin guards fonctionnels
- [ ] **Navigation dynamique** : Menu qui s'adapte selon le rôle
- [ ] **Gestion des paramètres** : Routes avec paramètres

#### **5. Gestion d'État avec Signals (Angular 20+)**
- [ ] **Signals writable** : Implémentation dans les composants
- [ ] **Computed signals** : Utilisation obligatoire
- [ ] **Effects** : Au moins 1 effet implémenté
- [ ] **Services avec Signals** : Gestion d'état globale

#### **6. Composants Personnalisés**
- [ ] **Pipes personnalisés** : Au moins 2 pipes custom
- [ ] **Directives personnalisées** : Au moins 1 directive custom
- [ ] **Composants réutilisables** : Smart/Dumb components
- [ ] **Communication composants** : @Input, @Output, services

#### **7. HTTP et Intercepteurs**
- [ ] **HTTP Interceptors** : Implémentation obligatoire
- [ ] **Gestion d'erreurs HTTP** : Service centralisé
- [ ] **Simulation API** : Mock data avec délais
- [ ] **Loading states** : Indicateurs de chargement

#### **8. Interface Utilisateur**
- [ ] **Tailwind CSS** : Utilisation exclusive
- [ ] **Interface responsive** : Mobile-friendly
- [ ] **UX moderne** : Navigation intuitive, feedback utilisateur
- [ ] **Accessibility** : Bonnes pratiques d'accessibilité

#### **9. Qualité du Code**
- [ ] **ESLint strict** : Aucune erreur de linting
- [ ] **TypeScript strict** : Types corrects, pas de `any`
- [ ] **Code propre** : Noms explicites, fonctions courtes
- [ ] **Comments en anglais** : Documentation du code complexe

#### **10. Tests et Débogage**
- [ ] **Tests unitaires** : Au moins 3 tests (service, pipe, directive)
- [ ] **Tests d'intégration** : Au moins 1 test de composant
- [ ] **Console propre** : Pas d'erreurs ou de warnings
- [ ] **Performance** : Application réactive, pas de lags

---

## 🎥 Démonstration Vidéo (15-20 min max)

### **📱 Tests fonctionnels obligatoires :**

#### **1. Authentification (5 minutes)**
- [ ] **Register** : Créer un compte utilisateur
- [ ] **Login valide** : Connexion réussie
- [ ] **Login invalide** : Mauvais password → message d'erreur
- [ ] **Logout** : Déconnexion et redirection
- [ ] **Persistance** : Rafraîchir la page → rester connecté

#### **2. Autorisation et Guards (3 minutes)**
- [ ] **AuthGuard** : Accès refusé si non connecté → redirection login
- [ ] **AdminGuard** : Accès admin refusé si user normal
- [ ] **Navigation dynamique** : Menu qui change selon le rôle
- [ ] **Roles** : Démontrer user vs admin

#### **3. Fonctionnalités Métier (4 minutes)**
- [ ] **CRUD complet** : Create, Read, Update, Delete
- [ ] **Formulaires** : Validation en temps réel
- [ ] **Pipes personnalisés** : Transformation de données visible
- [ ] **Directives personnalisées** : Comportement custom visible

#### **4. Gestion d'État et Performance (3 minutes)**
- [ ] **Signals** : Démontrer la réactivité des computed signals
- [ ] **Effects** : Montrer un effet qui se déclenche
- [ ] **Persistence** : Données sauvegardées automatiquement
- [ ] **Loading states** : Indicateurs de chargement

#### **5. Interface et UX (2 minutes)**
- [ ] **Responsive** : Tester sur mobile/desktop
- [ ] **Feedback utilisateur** : Messages de succès/erreur
- [ ] **Navigation fluide** : Pas de bugs visuels
- [ ] **Accessibility** : Démontrer au moins 1 feature accessible

#### **6. Qualité Technique (3 minutes)**
- [ ] **Console propre** : Ouvrir les DevTools → pas d'erreurs
- [ ] **Tests** : Lancer `npm test` → tests passent
- [ ] **Linting** : Lancer `npm run lint` → pas d'erreurs
- [ ] **Build** : Lancer `npm run build` → build réussit

---

## 🏗️ Présentation Architecture Angular (5 min dans la vidéo)

### **📁 Fichiers clés à expliquer :**

#### **1. Point d'entrée**
- [ ] **`src/main.ts`** : Bootstrap de l'application
- [ ] **`src/app/app.config.ts`** : Configuration globale
- [ ] **`src/app/app.component.ts`** : Composant racine

#### **2. Routing et Navigation**
- [ ] **`src/app/app.routes.ts`** : Routes principales
- [ ] **`src/app/features/*/routes.ts`** : Routes par feature
- [ ] **Lazy Loading** : Comment ça fonctionne

#### **3. Architecture DDD**
- [ ] **`src/app/features/`** : Logique métier par domaine
- [ ] **`src/app/shared/`** : Composants réutilisables
- [ ] **`src/app/core/`** : Services globaux (si présent)

#### **4. Configuration**
- [ ] **`angular.json`** : Configuration du projet
- [ ] **`package.json`** : Dépendances et scripts
- [ ] **`tsconfig.json`** : Configuration TypeScript

#### **5. Styling et Assets**
- [ ] **`src/styles.scss`** : Styles globaux + Tailwind
- [ ] **`tailwind.config.js`** : Configuration Tailwind
- [ ] **`src/assets/`** : Ressources statiques

### **💡 Concepts à expliquer :**
- [ ] **Standalone Components** : Expliquer le concept
- [ ] **Dependency Injection** : Fonctionnement dans Angular
- [ ] **Change Detection** : Mécanisme de détection
- [ ] **Signals vs Observables** : Différences et avantages
- [ ] **Guards et Interceptors** : Rôle dans l'application

---

## 📊 Critères d'évaluation

### **Barème de notation (/20) :**

| Critère | Points | Détail |
|---------|--------|---------|
| **Architecture et Structure** | 4 pts | DDD, standalone, organisation |
| **Fonctionnalités Métier** | 4 pts | CRUD, auth, guards, forms |
| **Signals et État** | 3 pts | Writable, computed, effects |
| **Composants Personnalisés** | 3 pts | Pipes, directives, réutilisabilité |
| **Qualité du Code** | 2 pts | ESLint, TypeScript, tests |
| **Interface Utilisateur** | 2 pts | Tailwind, UX, responsive |
| **Démonstration Vidéo** | 2 pts | Clarté, exhaustivité, respect du temps |

### **Bonus possibles (+2 pts max) :**
- [ ] **Tests avancés** : Coverage > 80%
- [ ] **Performance** : Optimisations (OnPush, trackBy)
- [ ] **Fonctionnalités extras** : Drag & drop, animations, PWA
- [ ] **Documentation** : README complet, JSDoc

---

## 🚀 Suggestions de projets

### **💡 Idées d'applications (au choix) :**

1. **📝 TodoList avancée** : Étendre l'app du cours
2. **🛒 E-commerce** : Produits, panier, commandes
3. **📚 Gestion de bibliothèque** : Livres, emprunts, utilisateurs
4. **🎬 Netflix-like** : Films, favoris, playlists
5. **💰 Gestion de budget** : Transactions, catégories, stats
6. **🏥 Gestion d'hôpital** : Patients, médecins, rendez-vous
7. **🎓 Plateforme e-learning** : Cours, étudiants, notes
8. **🍕 Système de livraison** : Restaurants, commandes, livreurs

### **⚠️ Contraintes obligatoires :**
- **Minimum 3 entités** métier différentes
- **Au moins 2 rôles** utilisateur différents
- **Interface admin** pour la gestion
- **Données mock** réalistes et cohérentes

---

## 📅 Planning et Livraison

### **🗓️ Échéances :**
- **Durée** : 1 mois après les 4 premiers jours de cours (le dernier jour, vous pourrez finir en classe ceux qui sont en retard)
- **Livraison** : Code source + Vidéo de démonstration
- **Format vidéo** : MP4, qualité HD, son clair
- **Durée vidéo** : 15-20 minutes MAXIMUM

### **📦 Livrables :**
1. **Repository Git** : Code source complet avec historique de commits
2. **README.md** : Instructions d'installation et utilisation
3. **Vidéo de démonstration** : Tous les tests + présentation architecture
4. **Document technique** : Choix d'architecture et justifications (optionnel)

---

## 🎯 Conseils pour réussir

### **✅ Recommandations :**
- **Commencez simple** : Implémentez d'abord les fonctionnalités de base
- **Testez régulièrement** : Ne laissez pas les bugs s'accumuler
- **Documentez au fur et à mesure** : README et comments
- **Préparez la vidéo** : Script et répétition avant l'enregistrement
- **Vérifiez la checklist** : Tous les points doivent être validés

### **⚠️ Pièges à éviter :**
- **Trop d'ambition** : Fonctionnalités complexes qui cassent l'existant
- **Négligence du styling** : Interface brouillon = points perdus
- **Tests oubliés** : Les tests font partie de l'évaluation
- **Vidéo trop longue** : Respect strict des 20 minutes
- **Explications floues** : Soyez précis dans vos démonstrations

---

*🎓 **Objectif pédagogique :** Cette évaluation valide votre capacité à créer une application Angular complète, moderne et professionnelle en utilisant les dernières fonctionnalités du framework.*

*💡 **Conseil du mentor :** Prenez le temps de bien planifier votre projet. Une architecture solide au début vous fera gagner beaucoup de temps par la suite.*

---

**🚀 Bon projet et bonne chance !**

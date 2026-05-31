# Portfolio - Dieynaba Senghor

> Portfolio personnel d'une Future Cloud & DevOps Engineer passionnée par l'infrastructure cloud, l'automatisation et les pratiques DevOps.

![Portfolio Banner](https://images.unsplash.com/photo-1451187580459-43490279c0fa?auto=format&fit=crop&q=80&w=1400)

---

## 📋 Table des matières

- [À propos](#à-propos)
- [Fonctionnalités](#fonctionnalités)
- [Technologies](#technologies)
- [Installation](#installation)
- [Utilisation](#utilisation)
- [Structure du projet](#structure-du-projet)
- [Déploiement](#déploiement)
- [Contribution](#contribution)
- [Contact](#contact)
- [Licence](#licence)

---

## 🎯 À propos

Ce portfolio met en valeur mes compétences techniques en Cloud AWS, DevOps, administration système et développement web. Il présente mes projets, compétences et permet de me contacter pour des opportunités de stage ou d'alternance.

### Points forts

✨ **Design moderne** avec palette bordeaux/ivoire/or  
🌐 **Single Page Application (SPA)** avec React Router  
🔐 **Dashboard admin sécurisé** pour gérer les projets  
📱 **Responsive design** adapté à tous les écrans  
🚀 **Performance optimisée** avec React et Vite  
🎨 **Animations 3D** avec Three.js (sphère de particules)  

---

## ✨ Fonctionnalités

### Partie publique

- **Page d'accueil** : Présentation avec animation 3D et badges de compétences
- **Page Projets** : 
  - Projets Cloud & DevOps (section principale)
  - Projets secondaires (Réseaux, Systèmes, Web)
  - Fiches détaillées avec modal
  - Liens GitHub pour les projets open-source
- **Page Compétences** : Cartes organisées par domaine (Cloud, DevOps, Réseaux, Web)
- **Page Contact** : Informations de contact et réseaux sociaux
- **Téléchargement CV** : CV téléchargeable au format PDF

### Dashboard Admin

- **Authentification** : Connexion sécurisée par email/mot de passe
- **Gestion des projets** :
  - Créer un nouveau projet
  - Modifier un projet existant
  - Supprimer un projet
  - Organisation par catégories
- **Gestion du CV** :
  - Télécharger un CV (format PDF, max 5MB)
  - Remplacer le CV existant
  - Supprimer le CV
  - Aperçu du CV actuel

---

## 🛠 Technologies

### Frontend

- **React 18** - Bibliothèque UI moderne
- **Vite** - Build tool ultra-rapide
- **React Router DOM** - Navigation SPA
- **Three.js** - Animations 3D (sphère de particules)
- **Lucide React** - Icônes élégantes
- **CSS3** - Styling avec variables et animations

### Backend

- **Node.js 18** - Runtime JavaScript
- **Express.js** - Framework web
- **MongoDB** - Base de données NoSQL
- **Mongoose** - ODM pour MongoDB
- **Multer** - Upload de fichiers (CV)
- **CORS** - Gestion des requêtes cross-origin

### DevOps & Outils

- **Docker** - Conteneurisation
- **Docker Compose** - Orchestration des conteneurs
- **Jenkins** - Pipeline CI/CD
- **Git** - Contrôle de version
- **npm** - Gestionnaire de paquets

---

## 📦 Installation

### Prérequis

- **Node.js** 18 ou supérieur
- **MongoDB** 7 ou supérieur
- **npm** ou **yarn**

### Étapes d'installation

1. **Cloner le repository**

```bash
git clone https://github.com/votre-username/portfolio_perso.git
cd portfolio_perso
```

2. **Installer les dépendances du backend**

```bash
cd api
npm install
```

3. **Installer les dépendances du frontend**

```bash
cd ../ux_react
npm install
```

4. **Configuration des variables d'environnement**

Créez un fichier `.env` dans le dossier `api/` :

```env
PORT=21019
MONGODB_URI=mongodb://127.0.0.1:27017/portfolio_perso
CLIENT_ORIGIN=http://127.0.0.1:5173
```

Créez un fichier `.env` dans le dossier `ux_react/` :

```env
VITE_API_URL=http://127.0.0.1:21019/api
```

5. **Lancer MongoDB**

```bash
# Avec MongoDB installé localement
mongod

# Ou avec Docker
docker run -d -p 27017:27017 --name mongodb mongo:7
```

6. **Démarrer le serveur backend**

```bash
cd api
npm run dev:api
```

7. **Démarrer le serveur frontend**

```bash
cd ux_react
npm run dev:react
```

8. **Accéder à l'application**

- Frontend : http://localhost:5174
- Backend API : http://localhost:21019
- Admin : http://localhost:5174/admin

---

## 🚀 Utilisation

### Accès public

Naviguez librement sur les pages :
- **/** : Page d'accueil
- **/projects** : Liste des projets
- **/skills** : Compétences techniques
- **/contact** : Informations de contact

### Accès admin

1. Rendez-vous sur http://localhost:5174/admin
2. Connectez-vous avec les identifiants :
   - **Email** : `dieyna1801@gmail.com`
   - **Mot de passe** : `passer@1`

⚠️ **Important** : Changez ces identifiants en production !

### Gérer les projets

Dans le dashboard admin :
1. Cliquez sur **"Ajouter un projet"**
2. Remplissez le formulaire :
   - Titre du projet
   - Description longue
   - Ce que vous avez fait
   - Technologies (séparées par des virgules)
   - Lien GitHub (optionnel)
   - Catégorie (Cloud et DevOps, Réseaux, etc.)
3. Cliquez sur **"Ajouter"**

Pour modifier : cliquez sur **"Modifier"** sur une carte projet  
Pour supprimer : cliquez sur **"Supprimer"** (confirmation demandée)

### Gérer le CV

1. Dans le dashboard admin, section **"Curriculum Vitae"**
2. Cliquez sur **"Télécharger un CV (PDF)"**
3. Sélectionnez votre fichier PDF (max 5MB)
4. Le CV sera téléchargeable depuis la page d'accueil

---

## 📁 Structure du projet

```
portfolio_perso/
├── api/                          # Backend Express.js
│   ├── index.js                  # Point d'entrée API
│   ├── uploads/                  # Dossier CV uploadé
│   ├── package.json              # Dépendances backend
│   └── .env                      # Variables d'environnement backend
│
├── ux_react/                     # Frontend React
│   ├── src/
│   │   ├── main.jsx              # Point d'entrée React + Routes
│   │   ├── Layout.jsx            # Layout principal (header + footer)
│   │   ├── HomePage.jsx          # Page d'accueil
│   │   ├── ProjectsPage.jsx     # Page projets
│   │   ├── SkillsPage.jsx       # Page compétences
│   │   ├── ContactPage.jsx      # Page contact
│   │   ├── AdminPage.jsx        # Wrapper admin
│   │   ├── AdminLogin.jsx       # Formulaire de connexion
│   │   ├── AdminDashboard.jsx   # Dashboard de gestion
│   │   ├── Globe3D.jsx          # Animation 3D Three.js
│   │   ├── styles.css           # Styles globaux
│   │   └── admin-styles.css     # Styles admin
│   ├── public/
│   │   ├── logo.png              # Logo DS
│   │   └── logo-full.png         # Logo complet avec nom
│   ├── package.json              # Dépendances frontend
│   └── .env                      # Variables d'environnement frontend
│
├── docker-compose.yml            # Orchestration Docker
├── Dockerfile                    # Configuration Docker (si applicable)
├── Jenkinsfile                   # Pipeline CI/CD Jenkins
├── DEPLOIEMENT.md                # Guide de déploiement détaillé
├── README.md                     # Ce fichier
└── .gitignore                    # Fichiers ignorés par Git
```

---

## 🐳 Déploiement

Consultez le fichier **[DEPLOIEMENT.md](./DEPLOIEMENT.md)** pour des instructions détaillées sur :

- ✅ **Conteneurisation avec Docker**
- ✅ **Déploiement sur Vercel**
- ✅ **Automatisation avec Jenkins**

### Déploiement rapide avec Docker

```bash
# Construire et lancer tous les services
docker-compose up --build

# Accéder à l'application
# Frontend : http://localhost:5174
# Backend : http://localhost:21019
```

---

## 🤝 Contribution

Les contributions sont les bienvenues ! Si vous souhaitez améliorer ce portfolio :

1. **Fork** le projet
2. **Créez** une branche pour votre feature (`git checkout -b feature/AmazingFeature`)
3. **Commit** vos changements (`git commit -m 'Add some AmazingFeature'`)
4. **Push** sur la branche (`git push origin feature/AmazingFeature`)
5. **Ouvrez** une Pull Request

---

## 📧 Contact

**Dieynaba Senghor**  
Future Cloud & DevOps Engineer

- 📧 Email : contact@dieynaba-senghor.com
- 💼 LinkedIn : [linkedin.com/in/dieynaba-senghor](https://linkedin.com/in/dieynaba-senghor)
- 💻 GitHub : [github.com/dieynaba-senghor](https://github.com/dieynaba-senghor)
- 📍 Localisation : Dakar, Sénégal

---

## 📝 Licence

Ce projet est sous licence MIT. Voir le fichier [LICENSE](./LICENSE) pour plus de détails.

---

## 🎓 Parcours

- **2025 – 2026** : Formation Cloud AWS DevOps - Orange Digital Center
- **2022 – 2025** : Licence professionnelle en Réseaux informatiques - ISI Dakar

---

## 💡 Opportunités

Je recherche actuellement une opportunité en **stage** ou en **alternance** dans le domaine du :
- ☁️ Cloud AWS
- 🔧 DevOps & CI/CD
- 🐳 Conteneurisation (Docker, Kubernetes)
- ⚙️ Automatisation & Infrastructure as Code

N'hésitez pas à me contacter !

---

<div align="center">

**Fait avec ❤️ et React par Dieynaba Senghor**

⭐ Si ce projet vous plaît, pensez à lui donner une étoile !

</div>

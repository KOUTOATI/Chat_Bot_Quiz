# 🎯 Quiz Chatbot avec Gemini API

Un chatbot interactif qui génère et pose des quiz à l'utilisateur en utilisant l'API Gemini de Google.

## 📋 Table des matières

- [Aperçu](#aperçu)
- [Fonctionnalités](#fonctionnalités)
- [Technologies utilisées](#technologies-utilisées)
- [Architecture](#architecture)
- [Installation](#installation)
- [Configuration](#configuration)
- [Utilisation](#utilisation)
- [Structure du projet](#structure-du-projet)
- [API Endpoints](#api-endpoints)
- [Déploiement](#déploiement)
- [Contribuer](#contribuer)

## 🎨 Aperçu

Ce projet est un chatbot intelligent qui :
- Génère des questions de quiz sur différents sujets
- Interagit avec l'utilisateur de manière conversationnelle
- Évalue les réponses et donne un feedback immédiat
- Garde un historique de la conversation
- Calcule et affiche les scores

## ✨ Fonctionnalités

- 🤖 **Intelligence artificielle** : Utilise Gemini API pour générer des quiz personnalisés
- 💬 **Interface conversationnelle** : Chat fluide et intuitif
- 📊 **Suivi des scores** : Comptabilise les bonnes et mauvaises réponses
- 🎲 **Thèmes variés** : Quiz sur différents sujets (histoire, sciences, culture générale, etc.)
- 🔄 **Temps réel** : Réponses instantanées du chatbot
- 📱 **Responsive** : Fonctionne sur tous les appareils

## 🛠️ Technologies utilisées

### Backend
- **FastAPI** : Framework web Python moderne et rapide
- **Google Gemini API** : IA générative pour créer les quiz
- **Uvicorn** : Serveur ASGI pour FastAPI
- **Pydantic** : Validation des données
- **Python-dotenv** : Gestion des variables d'environnement

### Frontend
- **React** : Bibliothèque JavaScript pour l'interface utilisateur
- **Axios** : Client HTTP pour les requêtes API
- **CSS3** : Stylisation moderne et responsive

## 🏗️ Architecture

```
┌─────────────┐         ┌──────────────┐         ┌─────────────┐
│   React     │ ◄─────► │   FastAPI    │ ◄─────► │  Gemini API │
│  Frontend   │  HTTP   │   Backend    │  HTTP   │   (Google)  │
└─────────────┘         └──────────────┘         └─────────────┘
```

Le frontend React communique avec le backend FastAPI via des requêtes HTTP. Le backend utilise l'API Gemini pour générer les questions et évaluer les réponses.

## 📦 Installation

### Prérequis

- Python 3.9+
- Node.js 16+
- npm ou yarn
- Une clé API Google Gemini ([obtenir une clé](https://makersuite.google.com/app/apikey))

### Backend

1. **Cloner le repository**
```bash
git clone <votre-repo>
cd quiz-chatbot/backend
```

2. **Créer un environnement virtuel**
```bash
python -m venv venv
source venv/bin/activate  # Sur Windows: venv\Scripts\activate
```

3. **Installer les dépendances**
```bash
pip install -r requirements.txt
```

4. **Configurer les variables d'environnement**
```bash
cp .env.example .env
# Éditer .env et ajouter votre clé API Gemini
```

### Frontend

1. **Aller dans le dossier frontend**
```bash
cd ../frontend
```

2. **Installer les dépendances**
```bash
npm install
```

## ⚙️ Configuration

### Backend (.env)

Créez un fichier `.env` dans le dossier `backend/` :

```env
GEMINI_API_KEY=votre_clé_api_gemini
BACKEND_PORT=8000
ALLOWED_ORIGINS=http://localhost:3000
```

### Frontend

Le frontend est configuré pour se connecter au backend sur `http://localhost:8000`. Si nécessaire, modifiez l'URL dans `frontend/src/services/api.js`.

## 🚀 Utilisation

### Démarrer le Backend

```bash
cd backend
source venv/bin/activate  # Sur Windows: venv\Scripts\activate
python main.py
```

Le serveur démarre sur `http://localhost:8000`

### Démarrer le Frontend

Dans un nouveau terminal :

```bash
cd frontend
npm start
```

L'application s'ouvre sur `http://localhost:3000`

### Utiliser l'application

1. Ouvrez votre navigateur sur `http://localhost:3000`
2. Choisissez un thème de quiz ou laissez le chatbot vous proposer
3. Répondez aux questions dans le chat
4. Consultez votre score en temps réel
5. Demandez de nouveaux quiz quand vous voulez !

## 📁 Structure du projet

```
quiz-chatbot/
├── backend/
│   ├── main.py                 # Point d'entrée FastAPI
│   ├── requirements.txt        # Dépendances Python
│   ├── .env.example           # Template variables d'environnement
│   ├── .env                   # Variables d'environnement (git ignored)
│   └── README.md              # Documentation backend
│
├── frontend/
│   ├── public/
│   │   └── index.html
│   ├── src/
│   │   ├── components/
│   │   │   ├── ChatBox.js     # Composant de chat
│   │   │   ├── ChatBox.css    # Styles du chat
│   │   │   ├── Message.js     # Composant message
│   │   │   └── ScoreBoard.js  # Affichage du score
│   │   ├── services/
│   │   │   └── api.js         # Service API
│   │   ├── App.js             # Composant principal
│   │   ├── App.css            # Styles globaux
│   │   └── index.js           # Point d'entrée React
│   ├── package.json
│   └── README.md              # Documentation frontend
│
└── README.md                  # Ce fichier
```

## 🔌 API Endpoints

### POST /chat
Envoyer un message au chatbot

**Request:**
```json
{
  "message": "Je veux un quiz sur l'histoire",
  "conversation_history": []
}
```

**Response:**
```json
{
  "response": "Super ! Voici votre première question...",
  "conversation_history": [...],
  "score": {
    "correct": 0,
    "incorrect": 0,
    "total": 0
  }
}
```

### POST /reset
Réinitialiser la conversation

**Response:**
```json
{
  "message": "Conversation réinitialisée",
  "conversation_history": []
}
```

### GET /health
Vérifier l'état du serveur

**Response:**
```json
{
  "status": "healthy"
}
```

## 🌐 Déploiement

### Backend (Render / Railway / Heroku)

1. Créez un fichier `Procfile`:
```
web: uvicorn main:app --host 0.0.0.0 --port $PORT
```

2. Assurez-vous que `requirements.txt` est à jour

3. Configurez les variables d'environnement sur votre plateforme

### Frontend (Vercel / Netlify)

1. Build le projet:
```bash
npm run build
```

2. Déployez le dossier `build/` sur votre plateforme

3. Configurez l'URL du backend dans les variables d'environnement

## 🤝 Contribuer

Les contributions sont les bienvenues !

1. Fork le projet
2. Créez une branche (`git checkout -b feature/AmazingFeature`)
3. Commit vos changements (`git commit -m 'Add some AmazingFeature'`)
4. Push vers la branche (`git push origin feature/AmazingFeature`)
5. Ouvrez une Pull Request

## 📝 Améliorations futures

- [ ] Authentification utilisateur
- [ ] Sauvegarde des scores dans une base de données
- [ ] Mode multijoueur
- [ ] Différents niveaux de difficulté
- [ ] Export des résultats en PDF
- [ ] Support multilingue
- [ ] Personnalisation des thèmes visuels
- [ ] Mode hors-ligne avec questions pré-chargées

## 📄 Licence

Ce projet est sous licence MIT. Voir le fichier `LICENSE` pour plus de détails.

## 👨‍💻 Auteur

Votre Nom - [@votre_twitter](https://twitter.com/votre_twitter)

## 🙏 Remerciements

- Google pour l'API Gemini
- La communauté FastAPI
- La communauté React

---

**Note:** N'oubliez pas de garder votre clé API Gemini secrète et de ne jamais la commit dans Git !
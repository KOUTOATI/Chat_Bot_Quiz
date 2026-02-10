# Chat_Bot_Quiz
🤖 Chatbot de quiz interactif avec IA - FastAPI + React + Google Gemini API
# 🎯 Quiz Chatbot - AI-Powered Interactive Quiz Platform

Un chatbot intelligent qui génère et propose des quiz personnalisés sur n'importe quel sujet grâce à l'API Google Gemini.

## ✨ Fonctionnalités

- 💬 Chat conversationnel avec IA
- 📚 Génération automatique de quiz sur demande
- 🎚️ Niveaux de difficulté ajustables (facile, moyen, difficile)
- 📊 Système de scoring et feedback instantané
- 🔄 Interface temps réel avec WebSocket
- 🎨 Interface utilisateur moderne et responsive

## 🛠️ Stack Technique

- **Backend**: FastAPI, Python 3.10+
- **Frontend**: React.js, Axios
- **IA**: Google Gemini API
- **Base de données**: PostgreSQL (optionnel)
- **Containerisation**: Docker

## 📦 Dépôts

- [Backend (FastAPI)](lien-vers-repo-backend)
- [Frontend (React)](lien-vers-repo-frontend)

## 🚀 Démarrage rapide

Voir les README des dépôts backend et frontend pour les instructions d'installation.

## 👥 Contribution

Les contributions sont les bienvenues ! Consultez nos guidelines de contribution.

## 📄 Licence

MIT License
```

---

## 🔧 Pour le dépôt BACKEND

### Description courte
```
🔌 Backend API pour Quiz Chatbot - FastAPI + Google Gemini API
```

### Tags GitHub
```
fastapi, python, gemini-api, chatbot, quiz, api, websocket, ai, backend, rest-api

# 🔌 Quiz Chatbot - Backend API

API REST construite avec FastAPI pour alimenter le chatbot de quiz interactif.

## 🎯 Fonctionnalités

- ✅ Endpoints REST pour gestion des quiz
- ✅ WebSocket pour chat en temps réel
- ✅ Intégration Google Gemini API
- ✅ Validation des données avec Pydantic
- ✅ Documentation auto-générée (Swagger/OpenAPI)
- ✅ Support CORS pour le frontend React

## 📋 Prérequis

- Python 3.10+
- Clé API Google Gemini
- PostgreSQL (optionnel)

## 🚀 Installation
```bash
# Cloner le dépôt
git clone [url-du-repo]

# Créer environnement virtuel
python -m venv venv
source venv/bin/activate  # Linux/Mac
# ou
venv\Scripts\activate  # Windows

# Installer les dépendances
pip install -r requirements.txt

# Configurer les variables d'environnement
cp .env.example .env
# Éditer .env avec vos clés API

# Lancer le serveur
uvicorn app.main:app --reload
```

## 📚 Documentation API

Une fois lancé, accédez à :
- Swagger UI: http://localhost:8000/docs
- ReDoc: http://localhost:8000/redoc

## 🔗 Endpoints principaux
```
POST   /api/chat/message       - Envoyer un message au chatbot
POST   /api/quiz/generate      - Générer un nouveau quiz
POST   /api/quiz/answer        - Soumettre une réponse
GET    /api/quiz/{id}/score    - Obtenir le score
WS     /api/chat/ws/{session}  - WebSocket chat
```

## 🏗️ Structure du projet
```
backend/
├── app/
│   ├── api/          # Routes et endpoints
│   ├── core/         # Logique métier (Gemini client)
│   ├── models/       # Modèles Pydantic
│   ├── services/     # Services métier
│   └── main.py       # Point d'entrée
├── tests/
└── requirements.txt
```

## 🧪 Tests
```bash
pytest
```

## 🔒 Sécurité

- Ne jamais commiter le fichier `.env`
- Utiliser des variables d'environnement pour les secrets
- Valider toutes les entrées utilisateur

## 🤝 Contribution

1. Fork le projet
2. Créer une branche (`git checkout -b feature/AmazingFeature`)
3. Commit (`git commit -m 'Add AmazingFeature'`)
4. Push (`git push origin feature/AmazingFeature`)
5. Ouvrir une Pull Request

## 📝 Licence

MIT
```

---

## ⚛️ Pour le dépôt FRONTEND

### Description courte
```
🎨 Interface utilisateur React pour Quiz Chatbot - UI moderne et responsive
```

### Tags GitHub
```
react, javascript, chatbot, quiz, frontend, ui, gemini, axios, websocket, responsive

# 🎨 Quiz Chatbot - Frontend React

Interface utilisateur moderne et interactive pour le chatbot de quiz propulsé par IA.

## ✨ Fonctionnalités

- 💬 Interface de chat fluide et intuitive
- 🎯 Composants de quiz interactifs
- 📱 Design responsive (mobile, tablette, desktop)
- ⚡ Communication temps réel via WebSocket
- 🎨 UI/UX moderne avec animations
- 🌙 Mode sombre/clair (optionnel)

## 📋 Prérequis

- Node.js 16+
- npm ou yarn
- Backend API en cours d'exécution

## 🚀 Installation
```bash
# Cloner le dépôt
git clone [url-du-repo]

# Installer les dépendances
npm install
# ou
yarn install

# Configurer les variables d'environnement
cp .env.example .env
# Éditer .env avec l'URL de votre backend

# Lancer en développement
npm start
# ou
yarn start
```

L'application sera accessible sur http://localhost:3000

## 🏗️ Structure du projet
```
frontend/
├── src/
│   ├── components/   # Composants réutilisables
│   │   ├── Chat/    # Composants de chat
│   │   └── Quiz/    # Composants de quiz
│   ├── pages/       # Pages de l'application
│   ├── services/    # Appels API
│   ├── hooks/       # Hooks personnalisés
│   ├── context/     # Context API
│   └── utils/       # Utilitaires
├── public/
└── package.json
```

## 📦 Scripts disponibles
```bash
npm start          # Développement
npm run build      # Build production
npm test           # Tests
npm run eject      # Eject configuration
```

## 🔌 Configuration Backend

Dans `.env`:
```
REACT_APP_API_URL=http://localhost:8000/api
REACT_APP_WS_URL=ws://localhost:8000/api/chat/ws
```

## 🎨 Composants principaux

- **ChatContainer**: Gestion du chat
- **QuizContainer**: Gestion des quiz
- **QuestionCard**: Affichage des questions
- **ScoreDisplay**: Affichage des résultats

## 🧪 Tests
```bash
npm test
```

## 📱 Build pour production
```bash
npm run build
```

Les fichiers optimisés seront dans le dossier `build/`

## 🤝 Contribution

1. Fork le projet
2. Créer une branche feature
3. Commit vos changements
4. Push et ouvrir une PR

## 📝 Licence

MIT
```

---

## 🏷️ Topics/Tags recommandés pour GitHub

### Pour tous les dépôts:
```
quiz
chatbot
gemini-api
ai
machine-learning
education
interactive
learning-platform
```

### Spécifiques Backend:
```
fastapi
python
rest-api
websocket
pydantic
async
api-development
```

### Spécifiques Frontend:
```
react
reactjs
javascript
ui
ux
responsive-design
spa
single-page-app

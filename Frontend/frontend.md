# Frontend - Quiz Chatbot

Interface React pour le chatbot de quiz.

## 🚀 Démarrage rapide

### Installation

```bash
npm install
```

### Configuration

Créez un fichier `.env` (optionnel) pour configurer l'URL du backend :

```env
REACT_APP_API_URL=http://localhost:8000
```

Si non défini, l'URL par défaut est `http://localhost:8000`.

### Lancer l'application

```bash
npm start
```

L'application s'ouvre sur `http://localhost:3000`

## 📦 Scripts disponibles

### `npm start`
Lance l'application en mode développement

### `npm build`
Crée une version optimisée pour la production dans le dossier `build/`

### `npm test`
Lance les tests

### `npm eject`
⚠️ Opération irréversible qui expose la configuration

## 🏗️ Structure

```
src/
├── components/
│   ├── ChatBox.js         # Composant principal du chat
│   ├── ChatBox.css        # Styles du chat
│   ├── Message.js         # Affichage des messages
│   ├── Message.css        # Styles des messages
│   ├── ScoreBoard.js      # Affichage du score
│   └── ScoreBoard.css     # Styles du score
├── services/
│   └── api.js             # Service de communication avec le backend
├── App.js                 # Composant racine
├── App.css                # Styles globaux
├── index.js               # Point d'entrée
└── index.css              # Reset CSS
```

## 🎨 Personnalisation

### Couleurs principales

Modifiez les couleurs dans les fichiers CSS :

```css
/* Gradient principal */
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);

/* Couleurs du score */
.score-item.correct { border-left-color: #28a745; }  /* Vert */
.score-item.incorrect { border-left-color: #dc3545; }  /* Rouge */
```

### Messages de bienvenue

Modifiez le message initial dans `ChatBox.js` :

```javascript
useEffect(() => {
  setMessages([
    {
      role: 'assistant',
      content: 'Votre message personnalisé ici',
    },
  ]);
}, []);
```

## 🔌 API Integration

Le frontend communique avec le backend via `src/services/api.js` :

```javascript
import { sendMessage, resetConversation } from './services/api';

// Envoyer un message
const response = await sendMessage(message, conversationHistory);

// Réinitialiser
await resetConversation();
```

## 📱 Responsive Design

L'interface s'adapte automatiquement :
- 📱 Mobile : < 768px
- 💻 Desktop : ≥ 768px

## 🌐 Déploiement

### Vercel

```bash
npm install -g vercel
vercel
```

### Netlify

```bash
npm run build
# Glissez-déposez le dossier build/ sur Netlify
```

### Configuration des variables d'environnement

Sur votre plateforme de déploiement, configurez :

```
REACT_APP_API_URL=https://votre-backend.com
```

## 🧪 Tests

Pour tester l'interface sans le backend :

1. Modifiez `api.js` pour retourner des données mockées
2. Utilisez `npm test` pour lancer les tests unitaires

## 🐛 Dépannage

### Le chat ne se connecte pas au backend
- Vérifiez que le backend est lancé sur `http://localhost:8000`
- Vérifiez la console du navigateur pour les erreurs CORS
- Vérifiez `REACT_APP_API_URL` dans `.env`

### Les messages ne s'affichent pas
- Ouvrez la console du navigateur (F12)
- Vérifiez les erreurs JavaScript
- Vérifiez que le backend répond correctement

### Erreur "npm start" ne fonctionne pas
- Supprimez `node_modules/` et `package-lock.json`
- Réinstallez : `npm install`

## ✨ Fonctionnalités

- ✅ Chat en temps réel
- ✅ Historique de conversation
- ✅ Compteur de score dynamique
- ✅ Animations fluides
- ✅ Interface responsive
- ✅ Gestion des erreurs
- ✅ Indicateur de chargement
- ✅ Scroll automatique
- ✅ Reset de conversation

## 🎯 Améliorations futures

- [ ] Thèmes clair/sombre
- [ ] Synthèse vocale
- [ ] Reconnaissance vocale
- [ ] Émojis et réactions
- [ ] Partage de score sur réseaux sociaux
- [ ] Historique des quiz passés
- [ ] Mode hors-ligne
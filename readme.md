## TP: Créez Votre Application de Messagerie avec React Native 🎉

### Introduction

Bienvenue à ce TP amusant et éducatif. Aujourd'hui, nous allons ensemble construire une application de messagerie moderne en utilisant **React Native**, **Firebase**, **React Navigation** et **Gluestack UI**. Ce TP couvrira les bases de la configuration ainsi que la création de composants avancés et des fonctionnalités de navigation.

### Objectifs du TP 📋

1. Configurer un projet React Native de zéro.
2. Intégrer Firebase pour l’authentification et le stockage des messages.
3. Utiliser React Navigation pour une navigation intuitive.
4. Créer des interfaces attrayantes avec Gluestack UI.

### Documentation Pratique 📚

- [React Native](https://reactnative.dev/docs/getting-started)
- [React Navigation](https://reactnavigation.org/docs/getting-started)
- [Firebase pour React Native](https://rnfirebase.io/)
- [Console Firebase](https://console.firebase.google.com/)
- [Gluestack UI](https://gluestack-ui-docs.com)

### Pré-requis 👨‍💻

- Connaissance en JavaScript
- Environnement de développement configuré (Node.js, Android Studio/Xcode)

### Étapes de l'Exercice 🛠️

#### Étape 1: Initialiser le projet React Native

1. **Créer un nouveau projet React Native**

```bash
npx react-native init MyMessagingApp
cd MyMessagingApp
```

2. **Intégrer Firebase**

```bash
npm install @react-native-firebase/app @react-native-firebase/auth @react-native-firebase/firestore
```

3. **Configurer Firebase**
   - Suivre les instructions dans la [documentation officielle](https://rnfirebase.io/)

#### Étape 2: Installer React Navigation

```bash
npm install @react-navigation/native @react-navigation/native-stack @react-navigation/bottom-tabs
npm install react-native-screens react-native-safe-area-context react-native-gesture-handler react-native-reanimated
```

#### Étape 3: Ajouter Gluestack UI

```bash
npm install gluestack-ui
```

### Routes de l'Application 🌐

#### Stack Routes d'authentification
- **Connexion utilisateur**
- **Création d'un compte utilisateur**

#### Route de complétion de profile
- **Complétion de Profil**:
  - Vérifiez si le profil de l'utilisateur est complet, sinon, redirigez vers le formulaire de complétion.

#### Routes de l'application
- **Accueil**:
  - Listes des discussions
  - Listes des utilisateurs (connectés/hors ligne)
  - Page de la discussion
- **Paramètres**:
  - Listage des paramètres
  - Bouton de déconnexion
- **Notifications** (optionnel):
  - Gérer les notifications de nouveaux messages.

### Modèles de Données Firebase 🗃️

#### Utilisateurs

```json
{
  "users": {
    "userId": {
      "username": "string",
      "email": "string",
      "profileCompleted": "boolean",
      "status": "online/offline"
    }
  }
}
```

#### Discussions

```json
{
  "discussions": {
    "discussionId": {
      "participants": ["userId1", "userId2"],
      "lastMessage": {
        "text": "string",
        "timestamp": "date",
        "senderId": "userId"
      }
    }
  }
}
```

#### Messages

```json
{
  "messages": {
    "messageId": {
      "discussionId": "string",
      "senderId": "string",
      "text": "string",
      "timestamp": "date"
    }
  }
}
```

### Librairies Tierces Pratiques 🔧

- [Redux](https://redux.js.org/)
- [MobX](https://mobx.js.org/react-integration.html)
- [Lottie for React Native](https://github.com/lottie-react-native/lottie-react-native)
- 

### Liste des Tâches 📝

1. **Initialiser le Projet**:
   - Suivre les étapes d'installation de React Native, Firebase, React Navigation et Gluestack UI.
2. **Configurer les Routes**:
   - Créer les stacks et les routes de navigation.
3. **Développer les Composants d'Authentification**:
   - Construire les formulaires de connexion et d'inscription.
4. **Implémenter la Logique de Complétion du Profil**:
   - Créer le screen de complétion de profil.
5. **Créer les Composants pour l'Accueil**:
   - Listes des discussions et des utilisateurs.
6. **Ajouter les Pages de Discussion et de Paramètres**:
   - Développer les composants de messagerie et de paramètres.
7. **Intégrer les Notifications**:
   - Ajouter une gestion des notifications pour les nouveaux messages.
8. **Styliser l'Application**:
   - Utiliser Gluestack UI pour un design cohérent et attrayant.

### Ressources Supplémentaires 🌟

- [React Native Tutorial](https://www.youtube.com/watch?v=0-S5a0eXPoc)
- [Grafikart React Native Guide](https://www.youtube.com/watch?v=hhe6Xb4Em5U&list=PLjwdMgw5TTLUEOKPg5Z5TgwAOeWkjGL69)

Amusez-vous, soyez créatifs et explorez toutes les possibilités qu'offrent ces technologies. 🔥

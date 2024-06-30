# TP: Créez Votre Application de Messagerie avec React Native 🎉

## Introduction

Bienvenue dans ce TP où vous allez plonger dans le développement mobile avec React Native. 🌟 
Imaginez une application de messagerie élégante, performante et totalement fonctionnelle, le tout développé par vous ! 🎯

Durant ce TP, vous allez apprendre à configurer un projet complet sans utiliser Expo. Vous découvrirez comment intégrer Firebase pour gérer l'authentification et la base de données en temps réel, utiliser React Navigation pour une navigation fluide entre les différentes pages, et styliser votre application avec Gluestack UI pour une interface utilisateur moderne et intuitive.

Préparez-vous à relever ce défi et à enrichir vos compétences de développeur mobile. Chaque étape vous guidera pour construire une application de messagerie performante et bien structurée, en passant par les routes d'authentification jusqu'aux paramètres utilisateurs, en y ajoutant une pincée de créativité pour d'autres fonctionnalités.

Quel que soit votre niveau, vous allez apprendre beaucoup et surtout, créer une application sur laquelle vous pourrez être fier. 

Alors, préparez vos environnements de développement, et plongeons ensemble dans ce TP ! 🚀

[Firebase - Qu'est ce que c'est ?](https://docs.google.com/presentation/d/1w4eineukg0occS2LyFTOdvh60WSRqwHBuGdyFwrwxsI/edit#slide=id.g91accc5f5f_0_53)
## Objectifs du TP 📋

1. Maîtriser la configuration d'un projet React Native sans expo 💪
2. Découvrir la puissance de Firebase pour l'authentification et le stockage de données et de fichier 🔥
3. Naviguer entre les screens grâce à React Navigation 🧭
4. Créer une interface utilisateur réactive et moderne avec Gluestack UI 🎨

## Proposition de maquette
Pour rendre le projet un peu plus cool, voici les maquettes Figma du design de l'application pour vous inspirer: [Maquettes](https://www.figma.com/design/bV4n2yGOYxyisBcDk2pHB2/Messenger-App?m=dev&node-id=0-1&t=AZuadJYdEW5Ezz04-1)

## Documentation Pratique 📚

- [React Native](https://reactnative.dev/docs/getting-started)
- [React Navigation](https://reactnavigation.org/docs/getting-started)
- [Firebase pour React Native](https://rnfirebase.io/)
- [Console Firebase](https://console.firebase.google.com/)
- [Gluestack UI](https://gluestack-ui-docs.com)

## Cahier des charges 🛠️

### Contexte et besoin

Dans ce projet, vous allez développer une application de messagerie pour mobile en utilisant les technologies React Native, Firebase, React Navigation et Gluestack UI. L'application doit permettre aux utilisateurs de s'inscrire, de se connecter, de compléter leur profil, d'envoyer et recevoir des messages avec les différents utilisateurs inscrits. 

Voici la liste des fonctionnalités principales :

### Authentification

Utiliser Firebase Authentication pour créer un compte et vous authentifier

- Connexion utilisateur
- Création de compte utilisateur

### Complétion de Profil

Créer votre premier document sur Firestore pour enregistrer les données de l'utilisateur
- Complétion de profil

### Accueil

Créer les différent model de données sur firestore pour enregistrer les discussions et les messages

- Liste des discussions
  - Affichage des discussions actives

- Liste des utilisateurs (en ligne/hors ligne)
  - Affichage des utilisateurs avec leurs statut
  - Implémentation d'une petite fonction de recherche par nom d'utilisateur 

- Page de discussion
Utiliser la librairie [React native gifted chat](https://www.npmjs.com/package/react-native-gifted-chat) pour créer l'espace de chat
  - Envoi et réception de messages
- Historique des messages

### Paramètres

Liste des paramètres
- Gestion des paramètres utilisateur (update du profil)
- Dark mode light mode
- Bouton de déconnexion
- CGU
- Autres ...

## Routes de l'Application 🌐

Utilister react navigation afin de préparer les différents screens répartient en différentes Stack (groupe de routes) afin d'organiser votre architecture 
Nous utiliserons des Stack pour grouper les routes ainsi qu'un Drawer afin de naviguer entre les stacks

### Stack Routes d'authentification [AuthStack]
- **Connexion utilisateur**
- **Création d'un compte utilisateur**

### Route de complétion de profile
- **Complétion de Profil**:
  - Vérifiez si le profil de l'utilisateur est complet dans la db de firebase, sinon, redirigez vers le formulaire de complétion.

### Stack Routes de l'application [HomeStack contenant la Bottom Tab Navigator] 
- **Accueil**:
  - Listes des discussions
  - Listes des utilisateurs (connectés/hors ligne)
  - Page profile
  - Notifications
    
- **Notifications** (optionnel si le temps nous le permet):
  - Gérer les notifications de nouveaux messages.
    
### Stack Routes des Paramettres [SettingsStack] 
- **Paramètres**:
  - Listage des paramètres
  - Bouton de déconnexion
 

Petit schema afin de visualiser tout ça : [MindMapRouter](https://www.figma.com/board/OtO6FPY3oE2OMpuMiqsHmH/MindMap-Router-Messenger-App?node-id=0-1&t=gY8qnOVgXnlSdOO1-1)

## Modèles de Données Firestore 🗃️

### Utilisateurs

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

### Discussions

```json
{
  "threads": {
    "threadId": {
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

### Messages

```json
{
  "messages": {
    "messageId": {
      "threadId": "string",
      "senderId": "string",
      "text": "string",
      "timestamp": "date"
    }
  }
}
```


## Librairies Tierces Utiles :wrench:

Voici quelques outils supplémentaires pour booster votre développement :

- **Redux** - Pour une gestion d'état impeccable :control_knobs:
- **MobX** - Un autre allié de choix pour une gestion d'état efficace :toolbox:
- **Lottie for React Native** - Ajoutez une touche d'animation pour épater vos utilisateurs :movie_camera:

## Liste des Tâches :pencil:

1. **Initialiser le Projet** :white_check_mark:
   - Suivre les étapes d'installation de React Native, Firebase, React Navigation et Gluestack UI.

2. **Configurer les Routes** :map:
   - Créer les stacks et les routes de navigation.

3. **Développer les Composants d'Authentification** :closed_lock_with_key:
   - Construire les formulaires de connexion et d'inscription.

4. **Implémenter la Logique de Complétion du Profil** :bust_in_silhouette:
   - Créer l'écran de complétion de profil.

5. **Créer les Composants pour l'Accueil** :house:
   - Développer les listes des discussions et des utilisateurs.

6. **Ajouter les Pages de Discussion et de Paramètres** :speech_balloon::gear:
   - Créer les composants de messagerie et de paramètres.

7. **Intégrer les Notifications** :bell:
   - Ajouter une gestion des notifications pour les nouveaux messages.


**On pense à créer un trello pour lister ses tâches plus en détail et suivre l'avancé du projet évidement**  


## Ressources 🌟

- [Firebase react native](https://snowpact.com/blog/firebase-react-native)
- [Build a Realtime Chat App with React Native and Firebase](https://www.youtube.com/watch?v=Ov3Z3vD5zFw)

Amusez-vous, soyez créatifs et explorez toutes les possibilités que vous offre firebase 🔥

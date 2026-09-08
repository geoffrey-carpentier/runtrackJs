# Runtrack JavaScript

Ce dépôt regroupe plusieurs projets et exercices réalisés en JavaScript dans le cadre du Runtrack JS. 

## Contenu du dépôt

### `jour05` - Validation de formulaires
Exercice d'intégration et de logique JavaScript.
- Création de pages de `connexion.html` et `inscription.html`.
- Mise en place d'un système de validation asynchrone (temps réel) des champs de formulaire de bout en bout (email, mot de passe complexe, codes postaux, etc.).

### `bigjob` - Application de planification (Agenda)
Projet front-end complet mettant en pratique de nombreux concepts JS.
- Interface d'agenda/planning.
- Utilisation de **FullCalendar** pour l'affichage interactif.
- Système de connexion et gestion des sessions simulé via **localStorage**.
- Gestion asynchrone des utilisateurs et événements à partir de fichiers de données (JSON).
- Interface responsive (utilisant CSS/Tailwind/Bootstrap).

## Installation

Ces projets sont statiques et s'exécutent entièrement côté client.
1. Clonez le dépôt :
   ```bash
   git clone https://github.com/geoffrey-carpentier/runtrackJs.git
   ```
2. Pour chaque projet, ouvrez simplement le fichier `index.html` ou `connexion.html` dans votre navigateur.
*(Note : Pour le bigjob, certaines requêtes Fetch vers des fichiers JSON locaux peuvent nécessiter l'utilisation d'un serveur local type Live Server sous VS Code pour contourner les restrictions CORS).*

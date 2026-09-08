# Runtrack JavaScript

**Note** : Ce projet a été réalisé dans le cadre de ma formation de Développeur Web et Web Mobile (DWWM) au sein de La Plateforme.

Ce dépôt regroupe plusieurs projets et exercices réalisés en JavaScript dans le cadre du Runtrack JS. 

## Contenu du dépôt

### `jour05` - Validation de formulaires
Exercice d'intégration et de logique JavaScript en Vanilla JS.
- Création de pages `connexion.html` et `inscription.html`.
- Mise en place d'un système complet de validation asynchrone (temps réel) des champs de formulaire de bout en bout (email, mot de passe avec critères de sécurité, codes postaux, etc.).

### `jour06` - Intégration du framework Bootstrap
Découverte et intégration du framework CSS Bootstrap.
- Utilisation des classes utilitaires et composants prédéfinis de Bootstrap (grilles, boutons, alertes, etc.) pour structurer des pages responsives.

### `jour07` - Intégration du framework Materialize
Découverte et intégration du framework CSS Materialize.
- Utilisation des classes utilitaires pour structurer et styliser une page (`header`, `footer`, grilles).
- Intégration d'un formulaire stylisé avec des icônes.
- Initialisation et configuration d'un composant dynamique (Carousel) via JavaScript.

### `bigjob` - Application de planification (Agenda)
Projet front-end complet de type "Agenda/Planning", mettant en pratique de nombreux concepts JS avancés.
- Utilisation de la librairie **FullCalendar** pour l'affichage interactif des événements.
- Système de connexion et gestion des sessions utilisateur simulés via le **localStorage**.
- Gestion asynchrone des utilisateurs à partir de fichiers de données (`users.json`).
- Interface sécurisée et responsive.

## Installation

Ces projets sont statiques et s'exécutent entièrement côté client.
1. Clonez le dépôt sur votre machine :
   ```bash
   git clone https://github.com/geoffrey-carpentier/runtrackJs.git
   ```
2. Pour chaque projet, ouvrez simplement le fichier `index.html` (ou `connexion.html`) dans votre navigateur web.
*(Note : Pour le bigjob, le navigateur peut bloquer les requêtes Fetch locales (CORS) vers les fichiers JSON. Il est recommandé d'utiliser une extension comme Live Server sous VS Code).*

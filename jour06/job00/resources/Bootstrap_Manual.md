

# Bootstrap_Manual.md

## Table des matières

1. Introduction générale
2. Rappels fondamentaux : HTML, CSS, JavaScript, PHP, JSON, jQuery
3. Présentation de Bootstrap
4. Installation et mise en place de Bootstrap
5. Le système de grille (Grid System)
6. Les composants Bootstrap
7. Utilisation avancée : personnalisation, utilitaires, et bonnes pratiques
8. Intégration avec JavaScript, jQuery et AJAX (fetch, JSON)
9. Astuces, conseils et erreurs fréquentes
10. Mini-projets et exemples complets
11. Glossaire
12. Ressources et liens utiles

---

## 1. Introduction générale

Bootstrap est un **framework front-end** open-source, développé initialement par Twitter, qui permet de créer rapidement des sites web modernes, responsives et esthétiques. Il fournit un ensemble de **classes CSS prédéfinies**, de **composants réutilisables** (boutons, formulaires, cartes, modales, etc.) et de **plugins JavaScript** pour accélérer et simplifier le développement web.

### Pourquoi utiliser Bootstrap ?

- **Gain de temps** : Plus besoin de tout coder à la main, Bootstrap propose des solutions prêtes à l’emploi.
- **Responsive design** : Les sites s’adaptent automatiquement à tous les écrans (ordinateurs, tablettes, smartphones).
- **Cohérence visuelle** : Les composants partagent une même charte graphique, ce qui garantit une interface homogène.
- **Communauté et documentation** : Très populaire, Bootstrap dispose d’une documentation riche et d’une grande communauté.

### À qui s’adresse Bootstrap ?

- Aux débutants qui souhaitent créer rapidement des sites web professionnels.
- Aux développeurs confirmés qui veulent accélérer leur workflow.
- Aux équipes qui cherchent à standardiser l’apparence de leurs applications.

### Limites et inconvénients

- **Uniformisation** : Les sites Bootstrap peuvent se ressembler si on ne personnalise pas les styles.
- **Poids** : Ajouter Bootstrap peut alourdir le site si on n’utilise qu’une petite partie des fonctionnalités.
- **Dépendance** : On s’habitue à la facilité, au détriment parfois de la compréhension profonde du CSS natif.

------

------

# 2. Rappels fondamentaux : HTML, CSS, JavaScript, PHP, JSON, jQuery

## 2.1. HTML (HyperText Markup Language)

**HTML** est le langage de balisage qui structure le contenu d’une page web.  
Il définit les éléments (titres, paragraphes, images, liens, formulaires, etc.) qui seront affichés dans le navigateur.

**Exemple de base :**

````html
<!-- Un document HTML minimal -->
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Ma première page</title>
</head>
<body>
    <h1>Bienvenue sur mon site</h1> <!-- Titre principal -->
    <p>Ceci est un paragraphe.</p> <!-- Paragraphe -->
    <a href="https://getbootstrap.com/">Lien vers Bootstrap</a> <!-- Lien hypertexte -->
</body>
</html>
````

**Points clés à retenir :**

- Les balises HTML sont entourées de `<` et `>`.
- La structure de base : `<html>`, `<head>`, `<body>`.
- Les attributs (ex : `href`, `src`, `alt`) permettent de préciser le comportement ou l’apparence d’un élément.

---

## 2.2. CSS (Cascading Style Sheets)

**CSS** permet de styliser les éléments HTML : couleurs, tailles, marges, positionnement, etc.

**Exemple de base :**

````css
/* Sélecteur de balise */
h1 {
    color: #007bff; /* Bleu Bootstrap */
    text-align: center;
}

/* Sélecteur de classe */
.btn {
    background-color: #28a745; /* Vert Bootstrap */
    color: white;
    padding: 10px 20px;
    border-radius: 5px;
}
````

**Intégration dans HTML :**

````html
<!-- Lien vers une feuille de style externe -->
<link rel="stylesheet" href="styles.css">
<!-- Style interne -->
<style>
    p { font-size: 18px; }
</style>
````

**Points clés à retenir :**

- Les sélecteurs ciblent les éléments à styliser.
- Les propriétés définissent l’apparence.
- Bootstrap fournit des centaines de classes CSS prêtes à l’emploi.

---

## 2.3. JavaScript

**JavaScript** est le langage de programmation du web.  
Il permet de rendre les pages interactives : animations, formulaires dynamiques, requêtes serveur, etc.

**Exemple de base :**

````html
<!-- Script JavaScript intégré dans une page HTML -->
<button onclick="alert('Bonjour !')">Cliquez-moi</button>
<script>
    // Ceci est un commentaire JS
    function direBonjour() {
        alert("Bienvenue sur Bootstrap !");
    }
</script>
````

**Points clés à retenir :**

- JavaScript s’exécute côté client (dans le navigateur).
- Il permet de manipuler le DOM (Document Object Model) : modifier le contenu, réagir aux événements (clic, survol, etc.).
- Bootstrap utilise JavaScript pour certains composants dynamiques (modales, carrousels, etc.).

---

## 2.4. PHP (Hypertext Preprocessor)

**PHP** est un langage de script côté serveur.  
Il permet de générer dynamiquement du HTML, de gérer des bases de données, des formulaires, etc.

**Exemple de base :**

````php
<?php
// Affiche la date du jour
echo "<p>Aujourd'hui, nous sommes le " . date('d/m/Y') . "</p>";
?>
````

**Points clés à retenir :**

- PHP s’exécute sur le serveur, avant que la page ne soit envoyée au navigateur.
- Il est souvent utilisé pour les sites dynamiques (WordPress, forums, etc.).
- Bootstrap s’utilise principalement côté client, mais peut être intégré dans des projets PHP.

---

## 2.5. JSON (JavaScript Object Notation)

**JSON** est un format léger d’échange de données, très utilisé pour communiquer entre le navigateur et le serveur (API, AJAX).

**Exemple de base :**

````json
{
    "nom": "Dupont",
    "age": 30,
    "email": "dupont@example.com"
}
````

**Utilisation en JavaScript :**

````javascript
// Conversion d’un objet JS en JSON
let utilisateur = { nom: "Dupont", age: 30 };
let json = JSON.stringify(utilisateur); // '{"nom":"Dupont","age":30}'

// Conversion d’une chaîne JSON en objet JS
let obj = JSON.parse(json); // { nom: "Dupont", age: 30 }
````

---

## 2.6. jQuery

**jQuery** est une bibliothèque JavaScript qui simplifie la manipulation du DOM, la gestion des événements et les requêtes AJAX.

**Exemple de base :**

````html
<!-- Inclusion de jQuery depuis un CDN -->
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
<script>
    // Quand le document est prêt
    $(document).ready(function() {
        // Sélectionne tous les paragraphes et change leur couleur
        $("p").css("color", "red");
    });
</script>
````

**Points clés à retenir :**

- jQuery utilise la syntaxe `$()` pour sélectionner des éléments.
- Beaucoup de projets Bootstrap utilisent encore jQuery, même si Bootstrap 5 n’en dépend plus.

---

## 2.7. Fetch API

**Fetch API** est une interface moderne pour effectuer des requêtes HTTP asynchrones (remplaçant XMLHttpRequest).

**Exemple de base :**

````javascript
// Récupérer des données depuis une API
fetch('https://jsonplaceholder.typicode.com/users')
    .then(response => response.json()) // Conversion en JSON
    .then(data => {
        console.log(data); // Affiche les utilisateurs dans la console
    })
    .catch(error => {
        console.error('Erreur :', error);
    });
````

---

**Astuce :**  
Pour bien utiliser Bootstrap, il est essentiel de comprendre comment HTML structure la page, comment CSS la stylise, et comment JavaScript (ou jQuery) permet de la rendre interactive.  
PHP, JSON et Fetch sont utiles pour les interactions serveur, mais Bootstrap s’utilise principalement côté client.

------

------

## 3. Présentation de Bootstrap

### 3.1. Qu’est-ce que Bootstrap ?

**Bootstrap** est un framework front-end open-source, initialement développé par Twitter, qui vise à faciliter et accélérer la création de sites web modernes, responsives et cohérents.  
Il fournit :

- Un ensemble de **classes CSS** prêtes à l’emploi pour la mise en page, la typographie, les couleurs, etc.
- De nombreux **composants réutilisables** (boutons, cartes, formulaires, alertes, modales…).
- Des **plugins JavaScript** pour ajouter de l’interactivité (menus déroulants, carrousels, tooltips…).

> **Lien officiel** : [https://getbootstrap.com/](https://getbootstrap.com/)

---

### 3.2. Les objectifs de Bootstrap

- **Uniformiser** l’apparence des sites web, quelle que soit la plateforme ou le navigateur.
- **Accélérer** le développement grâce à des composants prêts à l’emploi.
- **Faciliter** la création de sites responsives, adaptés à tous les écrans.
- **Permettre la personnalisation** grâce à des variables CSS et des utilitaires.

---

### 3.3. Fonctionnalités principales

- **Système de grille (Grid System)** : pour organiser le contenu en colonnes et lignes, adaptables selon la taille de l’écran.
- **Composants UI** : boutons, barres de navigation, cartes, alertes, badges, modales, etc.
- **Utilitaires CSS** : classes pour gérer les marges, paddings, couleurs, alignements, etc.
- **Plugins JavaScript** : pour les éléments interactifs (modales, carrousels, dropdowns…).
- **Personnalisation** : possibilité de modifier les couleurs, la typographie, les espacements via des variables CSS ou SASS.

---

### 3.4. Les versions de Bootstrap

- **Bootstrap 3** : première version largement adoptée, introduit le responsive design.
- **Bootstrap 4** : passage à Flexbox, nouveaux composants, personnalisation accrue.
- **Bootstrap 5** : suppression de la dépendance à jQuery, adoption de CSS Grid, nouveaux utilitaires, amélioration de l’accessibilité.

> **À retenir** : Bootstrap 5 est la version recommandée pour les nouveaux projets.

---

### 3.5. Avantages de Bootstrap

- **Rapidité de développement** : mise en page et composants prêts à l’emploi.
- **Responsive design** : adaptation automatique à tous les écrans.
- **Documentation complète** : guides, exemples, API détaillée.
- **Communauté active** : nombreux thèmes, plugins, ressources externes.

---

### 3.6. Inconvénients de Bootstrap

- **Sites qui se ressemblent** : si on ne personnalise pas, le rendu peut être standardisé.
- **Poids** : inclure tout Bootstrap peut être lourd si on utilise peu de composants.
- **Courbe d’apprentissage** : nécessite de comprendre la logique des classes utilitaires et du système de grille.

---

### 3.7. Quand utiliser Bootstrap ?

- Pour des prototypes rapides ou des MVP (Minimum Viable Product).
- Pour des applications internes ou des back-offices.
- Pour des sites vitrines nécessitant une compatibilité multi-supports.
- Moins adapté pour des sites nécessitant une identité graphique très poussée sans personnalisation.

---

### 3.8. Exemples de composants Bootstrap

Voici quelques exemples de composants courants :

**Bouton Bootstrap :**

````html
<button class="btn btn-primary">Bouton principal</button>
<!--
.btn : classe de base pour les boutons
.btn-primary : style principal (bleu)
-->
````

**Carte Bootstrap :**

````html
<div class="card" style="width: 18rem;">
  <img src="image.jpg" class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">Titre de la carte</h5>
    <p class="card-text">Texte de la carte.</p>
    <a href="#" class="btn btn-success">Action</a>
  </div>
</div>
````

**Alerte Bootstrap :**

````html
<div class="alert alert-warning" role="alert">
  Ceci est une alerte de type warning !
</div>
````

---

**Astuce :**  
Pour explorer tous les composants, consulte la [documentation officielle Bootstrap](https://getbootstrap.com/docs/5.0/components/alerts/).

---


## 4. Installation et mise en place de Bootstrap

### 4.1. Les différentes méthodes d’installation

Bootstrap peut être intégré à un projet de plusieurs façons :

#### a) Utilisation via CDN (Content Delivery Network)

C’est la méthode la plus simple et la plus rapide pour débuter.  
Il suffit d’ajouter les liens vers les fichiers CSS et JS hébergés sur un serveur distant.

**Exemple :**
````html
<!-- Intégration du CSS Bootstrap via CDN -->
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">

<!-- Intégration du JS Bootstrap via CDN (nécessite Popper pour certains composants) -->
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
````

**Avantages :**

- Facile et rapide à mettre en place.
- Toujours à jour.
- Pas besoin de télécharger les fichiers.

**Inconvénients :**

- Dépendance à une connexion internet.
- Moins de personnalisation possible.

---

#### b) Téléchargement des fichiers

Tu peux télécharger Bootstrap sur le [site officiel](https://getbootstrap.com/docs/5.0/getting-started/download/) et inclure les fichiers dans ton projet.

**Exemple d’arborescence :**

```
/mon-projet
  /css
    bootstrap.min.css
  /js
    bootstrap.bundle.min.js
  index.html
```

**Intégration dans HTML :**

````html
<link rel="stylesheet" href="css/bootstrap.min.css">
<script src="js/bootstrap.bundle.min.js"></script>
````

---

#### c) Installation via npm (Node Package Manager)

Pour les projets plus avancés ou utilisant des outils modernes (Webpack, Gulp…), tu peux installer Bootstrap via npm.

**Commande à exécuter dans le terminal :**

```
npm install bootstrap
```

**Utilisation dans un fichier JS ou SCSS :**

````javascript
// Import du CSS Bootstrap dans un projet JS (ex : React, Vue)
import 'bootstrap/dist/css/bootstrap.min.css';
import 'bootstrap/dist/js/bootstrap.bundle.min.js';
````

---

#### d) Utilisation avec des frameworks (React, Vue, Angular…)

Bootstrap peut être intégré dans des frameworks modernes via des bibliothèques dédiées :

- **React** : [React-Bootstrap](https://react-bootstrap.github.io/)
- **Vue** : [BootstrapVue](https://bootstrap-vue.org/)
- **Angular** : [ng-bootstrap](https://ng-bootstrap.github.io/)

> Ces solutions permettent d’utiliser les composants Bootstrap sous forme de composants natifs du framework.

---

### 4.2. Structure de base d’une page Bootstrap

Voici un exemple de structure minimale pour démarrer avec Bootstrap :

````html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Ma page Bootstrap</title>
  <!-- Lien vers le CSS Bootstrap (CDN) -->
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>
  <div class="container">
    <h1 class="text-center mt-5">Bienvenue sur Bootstrap !</h1>
    <p class="lead">Ceci est un exemple de page utilisant Bootstrap 5.</p>
  </div>
  <!-- JS Bootstrap (CDN) -->
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
````

**Commentaires :**

- `<meta name="viewport" ...>` est indispensable pour le responsive design.
- `.container` centre et limite la largeur du contenu.
- Les classes utilitaires (`text-center`, `mt-5`, `lead`) facilitent la mise en forme.

---

### 4.3. Conseils pour bien démarrer

- **Toujours vérifier la version** de Bootstrap utilisée (les classes et composants peuvent changer d’une version à l’autre).
- **Lire la documentation officielle** pour chaque composant utilisé.
- **Utiliser les outils de développement** du navigateur pour tester le responsive (mode mobile/tablette).
- **Ne pas surcharger inutilement** le projet avec des fichiers inutilisés (préférer une installation personnalisée si besoin).

---

**Astuce :**  
Pour personnaliser Bootstrap (couleurs, polices…), il est possible d’utiliser les fichiers sources SASS/SCSS et de recompiler le framework selon tes besoins.

------
------

## 5. Le système de grille (Grid System)

Le **système de grille** est l’un des piliers de Bootstrap. Il permet de structurer et d’organiser le contenu d’une page en lignes et colonnes, tout en assurant une adaptation automatique à la taille de l’écran (responsive design).

---

### 5.1. Principe de fonctionnement

- La grille Bootstrap est basée sur **12 colonnes** par ligne.
- On utilise des classes pour définir la largeur des colonnes selon la taille de l’écran :  
  - `col-` (pour tous les écrans)
  - `col-sm-` (≥576px)
  - `col-md-` (≥768px)
  - `col-lg-` (≥992px)
  - `col-xl-` (≥1200px)
  - `col-xxl-` (≥1400px)
- Les lignes sont créées avec la classe `.row` et les colonnes avec `.col`.

---

### 5.2. Exemple de base

````html
<div class="container">
  <div class="row">
    <div class="col-6 col-md-4">
      <!-- Colonne 1 : occupe 6 colonnes sur mobile, 4 sur écran moyen -->
      Colonne 1
    </div>
    <div class="col-6 col-md-8">
      <!-- Colonne 2 : occupe 6 colonnes sur mobile, 8 sur écran moyen -->
      Colonne 2
    </div>
  </div>
</div>
````

**Commentaires :**

- `.container` centre le contenu et limite sa largeur.
- `.row` crée une ligne horizontale.
- `.col-6` : la colonne occupe 6/12 (soit 50%) de la largeur sur petits écrans.
- `.col-md-4` : la colonne occupe 4/12 (soit 33%) sur écrans moyens et plus.

---

### 5.3. Les points de rupture (breakpoints)

| Classe      | Taille minimale de l’écran |
|-------------|---------------------------|
| `.col-`     | 0px (tous écrans)         |
| `.col-sm-`  | ≥ 576px                   |
| `.col-md-`  | ≥ 768px                   |
| `.col-lg-`  | ≥ 992px                   |
| `.col-xl-`  | ≥ 1200px                  |
| `.col-xxl-` | ≥ 1400px                  |

**Astuce :**  
Utilise les breakpoints pour adapter la disposition de tes éléments selon le support (mobile, tablette, desktop).

---

### 5.4. Colonnes automatiques et personnalisées

- **Colonnes de taille égale** :  
  Utilise simplement `.col` sans chiffre pour répartir l’espace équitablement.

  ````html
  <div class="row">
    <div class="col">Colonne A</div>
    <div class="col">Colonne B</div>
    <div class="col">Colonne C</div>
  </div>
  ````

- **Colonnes de taille personnalisée** :  
  Additionne les valeurs pour atteindre 12.

  ````html
  <div class="row">
    <div class="col-3">25%</div>
    <div class="col-9">75%</div>
  </div>
  ````

---

### 5.5. Imbrication des grilles

Il est possible d’imbriquer des grilles pour des mises en page complexes.

````html
<div class="row">
  <div class="col-8">
    Colonne principale
    <div class="row">
      <div class="col-6">Sous-colonne 1</div>
      <div class="col-6">Sous-colonne 2</div>
    </div>
  </div>
  <div class="col-4">Colonne secondaire</div>
</div>
````

---

### 5.6. Alignement et espacement

- **Alignement vertical** :  
  Utilise les classes `.align-items-start`, `.align-items-center`, `.align-items-end` sur `.row`.
- **Alignement horizontal** :  
  Utilise `.justify-content-start`, `.justify-content-center`, `.justify-content-end`, `.justify-content-between`, `.justify-content-around`.
- **Espacement** :  
  Utilise les classes utilitaires de marges et paddings (`.m-2`, `.p-3`, etc.).

**Exemple :**

````html
<div class="row align-items-center justify-content-between">
  <div class="col-4">Gauche</div>
  <div class="col-4">Droite</div>
</div>
````

---

### 5.7. Exemples pratiques

**Disposition responsive simple :**

````html
<div class="container">
  <div class="row">
    <div class="col-12 col-md-8">Contenu principal</div>
    <div class="col-12 col-md-4">Sidebar</div>
  </div>
</div>
````

**Explication :**

- Sur mobile, chaque colonne prend toute la largeur.
- Sur écran moyen et plus, la première colonne prend 8/12 et la seconde 4/12.

---

### 5.8. Bonnes pratiques

- Toujours placer les `.col` dans une `.row`.
- S’assurer que la somme des colonnes dans une ligne n’excède pas 12.
- Tester le rendu sur différents écrans (utilise l’inspecteur de ton navigateur).

---

**Pour aller plus loin :**  
Consulte la [documentation officielle du système de grille Bootstrap](https://getbootstrap.com/docs/5.0/layout/grid/) pour découvrir toutes les options avancées (ordre, offset, gutter, etc.).

------
------

## 6. Les composants Bootstrap

Bootstrap propose une large gamme de **composants réutilisables** pour enrichir rapidement l’interface utilisateur d’un site web. Ces composants sont stylisés par défaut et peuvent être personnalisés via des classes CSS ou des options JavaScript.

---

### 6.1. Boutons

Les boutons sont essentiels pour les interactions utilisateur. Bootstrap fournit plusieurs styles et tailles.

**Exemple de base :**
````html
<button type="button" class="btn btn-primary">Principal</button>
<button type="button" class="btn btn-secondary">Secondaire</button>
<button type="button" class="btn btn-success">Succès</button>
<button type="button" class="btn btn-danger">Danger</button>
<button type="button" class="btn btn-warning">Avertissement</button>
<button type="button" class="btn btn-info">Info</button>
<button type="button" class="btn btn-light">Clair</button>
<button type="button" class="btn btn-dark">Sombre</button>
````

**Variantes :**

- `.btn-lg` pour un bouton large
- `.btn-sm` pour un bouton petit
- `.btn-outline-*` pour un bouton avec contour

---

### 6.2. Alertes

Les alertes permettent d’afficher des messages importants à l’utilisateur.

**Exemple :**

````html
<div class="alert alert-success" role="alert">
  Opération réussie !
</div>
<div class="alert alert-danger" role="alert">
  Une erreur est survenue.
</div>
````

---

### 6.3. Cartes (Cards)

Les cartes sont des conteneurs flexibles pour afficher du contenu (texte, images, liens…).

**Exemple :**

````html
<div class="card" style="width: 18rem;">
  <img src="image.jpg" class="card-img-top" alt="Image de la carte">
  <div class="card-body">
    <h5 class="card-title">Titre de la carte</h5>
    <p class="card-text">Voici un exemple de carte Bootstrap.</p>
    <a href="#" class="btn btn-primary">En savoir plus</a>
  </div>
</div>
````

---

### 6.4. Modales (Modals)

Les modales sont des fenêtres superposées pour afficher des informations ou des formulaires sans quitter la page.

**Exemple d’appel de modale :**

````html
<!-- Bouton pour ouvrir la modale -->
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
  Ouvrir la modale
</button>

<!-- Structure de la modale -->
<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">Titre de la modale</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Fermer"></button>
      </div>
      <div class="modal-body">
        Contenu de la modale.
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Fermer</button>
        <button type="button" class="btn btn-primary">Enregistrer</button>
      </div>
    </div>
  </div>
</div>
````

---

### 6.5. Barres de navigation (Navbar)

La barre de navigation permet de créer un menu responsive en haut de page.

**Exemple :**

````html
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">MonSite</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav">
        <li class="nav-item">
          <a class="nav-link active" aria-current="page" href="#">Accueil</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Fonctionnalités</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Tarifs</a>
        </li>
      </ul>
    </div>
  </div>
</nav>
````



---

### 6.6. Listes groupées (List group)

Pour afficher des listes stylisées et interactives.

**Exemple :**
````html
<ul class="list-group">
  <li class="list-group-item active" aria-current="true">Élément actif</li>
  <li class="list-group-item">Deuxième élément</li>
  <li class="list-group-item">Troisième élément</li>
</ul>
````

---

### 6.7. Progress bars

Pour afficher une progression (chargement, avancement…).

**Exemple :**

````html
<div class="progress">
  <div class="progress-bar" role="progressbar" style="width: 60%;" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100">60%</div>
</div>
````

---

### 6.8. Formulaires

Bootstrap facilite la création de formulaires élégants et accessibles.

**Exemple :**

````html
<form>
  <div class="mb-3">
    <label for="exampleInputEmail1" class="form-label">Adresse email</label>
    <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
    <div id="emailHelp" class="form-text">Nous ne partagerons jamais votre email.</div>
  </div>
  <div class="mb-3">
    <label for="exampleInputPassword1" class="form-label">Mot de passe</label>
    <input type="password" class="form-control" id="exampleInputPassword1">
  </div>
  <button type="submit" class="btn btn-primary">Envoyer</button>
</form>
````

---

### 6.9. Autres composants utiles

- **Badges** : `<span class="badge bg-primary">Nouveau</span>`
- **Breadcrumbs** (fil d’Ariane)
- **Pagination**
- **Spinners** (indicateurs de chargement)
- **Tooltips** (infobulles)
- **Collapse** (accordéons)

> Pour la liste complète et les options avancées, consulte la [documentation officielle Bootstrap - Composants](https://getbootstrap.com/docs/5.0/components/).

---

***Astuce :***  
Combine les composants entre eux pour créer des interfaces riches et interactives, tout en gardant une cohérence graphique.

---
---
---

## 7. Utilisation avancée : personnalisation, utilitaires, et bonnes pratiques

Bootstrap ne se limite pas à l’utilisation de composants prêts à l’emploi. Il offre de nombreuses possibilités de ***personnalisation*** et d’optimisation grâce à ses utilitaires et à ses outils avancés.

---

### 7.1. Personnalisation de Bootstrap

#### a) Surcharger les classes CSS

Tu peux ajouter tes propres règles CSS pour modifier l’apparence des composants Bootstrap.

````css
/* Exemple : personnaliser la couleur des boutons primaires */
.btn-primary {
  background-color: #6610f2; /* Violet personnalisé */
  border-color: #520dc2;
}
````

> Toujours placer les styles personnalisés **après** l’import de Bootstrap pour qu’ils prennent le dessus.

---

#### b) Utiliser les variables CSS et SASS

Bootstrap est construit avec SASS, ce qui permet de modifier facilement les couleurs, la typographie, les espacements, etc.

- [Liste des variables SASS Bootstrap](https://getbootstrap.com/docs/5.0/customize/sass/)
- Pour utiliser SASS, il faut recompiler Bootstrap avec tes propres variables.

**Exemple de modification d’une variable SASS :**

```scss
$primary: #6610f2; // Nouvelle couleur principale
@import "bootstrap";
```

---

#### c) Utiliser les thèmes Bootstrap

Il existe de nombreux thèmes gratuits ou payants pour personnaliser rapidement l’apparence de ton site.

- [Bootstrap Themes officiels](https://themes.getbootstrap.com/)
- [Bootswatch (thèmes gratuits)](https://bootswatch.com/)

---

### 7.2. Utilitaires Bootstrap

Bootstrap propose des **classes utilitaires** pour gérer rapidement l’espacement, l’alignement, la couleur, la visibilité, etc.

#### a) Espacement (marges et paddings)

- `.m-3` : marge sur tous les côtés
- `.mt-2` : marge en haut
- `.mb-4` : marge en bas
- `.p-1` : padding sur tous les côtés
- `.px-5` : padding horizontal

#### b) Couleurs

- `.text-primary`, `.bg-success`, `.text-danger`, etc.

#### c) Affichage et visibilité

- `.d-none` : cacher un élément
- `.d-block` : afficher en bloc
- `.d-md-none` : cacher sur écran moyen et plus

#### d) Alignement

- `.text-center`, `.align-items-center`, `.justify-content-end`, etc.

**Exemple d’utilisation combinée :**

````html
<div class="bg-warning text-center p-3 mb-4">
  Boîte centrée avec fond jaune, padding et marge basse
</div>
````

---

### 7.3. Bonnes pratiques

- **Ne surcharge pas inutilement** les classes Bootstrap : privilégie les utilitaires pour des ajustements rapides.
- **Structure bien ton HTML** : utilise les containers, rows et cols pour garder une mise en page claire.
- **Teste le responsive** sur différents appareils et tailles d’écran.
- **Commente ton code** pour faciliter la maintenance.
- **Garde ton code DRY** (Don’t Repeat Yourself) : réutilise les classes et composants.

---

### 7.4. Astuces et tips

- Utilise le [générateur de classes utilitaires](https://getbootstrap.com/docs/5.0/utilities/api/) pour créer tes propres utilitaires.
- Pour des performances optimales, n’inclus que les parties de Bootstrap dont tu as besoin (via SASS ou des outils comme PurgeCSS).
- Utilise les icônes [Bootstrap Icons](https://icons.getbootstrap.com/) pour enrichir tes interfaces.

---
---
---

## **8.** Intégration avec JavaScript, jQuery et AJAX (fetch, JSON)

*Bootstrap propose de nombreux composants interactifs qui nécessitent JavaScript pour fonctionner (modales, carrousels, tooltips, etc.).  
Depuis la version 5, Bootstrap n’a plus besoin de jQuery, mais il est utile de connaître les deux approches.*

---

### **8.1.** Utilisation des composants JavaScript Bootstrap

Pour activer les composants interactifs, il suffit d’inclure le fichier `bootstrap.bundle.min.js` (qui contient Popper pour les tooltips, dropdowns, etc.).

***Exemple : activer un tooltip***

````html
<!-- Bouton avec tooltip -->
<button type="button" class="btn btn-secondary" data-bs-toggle="tooltip" data-bs-placement="top" title="Info sur le bouton">
  Survolez-moi
</button>

<!-- Script d’activation (à placer après l’inclusion de Bootstrap JS) -->
<script>
  // Active tous les tooltips de la page
  document.addEventListener('DOMContentLoaded', function () {
    var tooltipTriggerList = [].slice.call(document.querySelectorAll('[data-bs-toggle="tooltip"]'));
    tooltipTriggerList.forEach(function (tooltipTriggerEl) {
      new bootstrap.Tooltip(tooltipTriggerEl);
    });
  });
</script>
````

---

### **8.2.** Utilisation avec jQuery (héritage Bootstrap 4 et projets existants)

Même si Bootstrap 5 ne dépend plus de jQuery, il est toujours possible d’utiliser jQuery pour manipuler le DOM ou déclencher des actions sur les composants.

***Exemple : ouvrir une modale avec jQuery***

````html
<!-- Bouton pour ouvrir la modale -->
<button id="openModal" class="btn btn-primary">Ouvrir la modale</button>

<!-- Modale Bootstrap -->
<div class="modal fade" id="myModal" tabindex="-1" aria-hidden="true">
  <div class="modal-dialog"><div class="modal-content">...</div></div>
</div>

<!-- Script jQuery -->
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
<script>
  $('#openModal').on('click', function() {
    $('#myModal').modal('show'); // Affiche la modale
  });
</script>
````

---

### **8.3.** AJAX avec Fetch API

Pour charger ou envoyer des données sans recharger la page, utilise la Fetch API (moderne) ou jQuery AJAX (héritage).

***Exemple : charger des données JSON et les afficher***

````html
<ul id="userList" class="list-group"></ul>

<script>
  // Récupère des utilisateurs fictifs via une API publique
  fetch('https://jsonplaceholder.typicode.com/users')
    .then(response => response.json())
    .then(users => {
      const list = document.getElementById('userList');
      users.forEach(user => {
        // Crée un élément de liste pour chaque utilisateur
        const li = document.createElement('li');
        li.className = 'list-group-item';
        li.textContent = user.name + ' (' + user.email + ')';
        list.appendChild(li);
      });
    })
    .catch(error => {
      alert('Erreur lors du chargement des utilisateurs');
    });
</script>
````

---

### **8.4.** AJAX avec jQuery (pour projets existants)

***Exemple : requête AJAX avec jQuery***

````javascript
$.ajax({
  url: 'https://jsonplaceholder.typicode.com/users',
  method: 'GET',
  dataType: 'json'
}).done(function(users) {
  users.forEach(function(user) {
    $('#userList').append('<li class="list-group-item">' + user.name + ' (' + user.email + ')</li>');
  });
}).fail(function() {
  alert('Erreur lors du chargement des utilisateurs');
});
````

---

### **8.5.** Manipulation dynamique des composants Bootstrap

Tu peux créer, modifier ou supprimer dynamiquement des composants Bootstrap avec JavaScript ou jQuery.

***Exemple : ajouter une alerte dynamiquement***

````javascript
function showAlert(message, type = 'success') {
  // Crée une alerte Bootstrap et l’ajoute au DOM
  const alert = document.createElement('div');
  alert.className = `alert alert-${type} alert-dismissible fade show`;
  alert.role = 'alert';
  alert.innerHTML = `
    ${message}
    <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Fermer"></button>
  `;
  document.body.prepend(alert);
  // Retire l’alerte après 3 secondes
  setTimeout(() => alert.remove(), 3000);
}
````

---

****Astuce :***  
Pour tous les composants interactifs, consulte la [documentation officielle Bootstrap - JavaScript](https://getbootstrap.com/docs/5.0/getting-started/javascript/) pour découvrir les méthodes, options et événements disponibles.

---
---
---

## **9.** Astuces, conseils et erreurs fréquentes

Ce chapitre rassemble des **astuces pratiques**, des **conseils de pro** et les **erreurs courantes** à éviter pour bien maîtriser Bootstrap et gagner du temps au quotidien.

---

### **9.1.** Astuces pour aller plus loin

- **Utilise la documentation officielle** : [https://getbootstrap.com/docs/5.0/](https://getbootstrap.com/docs/5.0/)  
  Elle est très complète, avec des exemples interactifs et des explications détaillées pour chaque composant.
- **Teste le responsive dès le début** : Utilise l’outil d’inspection de ton navigateur (F12) pour simuler différents appareils et tailles d’écran.
- **Combine les classes utilitaires** : Les classes comme `.mt-3`, `.text-center`, `.d-flex` peuvent être combinées pour ajuster rapidement l’apparence sans écrire de CSS personnalisé.
- **Personnalise Bootstrap avec SASS** : Si tu veux un design unique, modifie les variables SASS avant de compiler Bootstrap.
- **Utilise les icônes Bootstrap** : [Bootstrap Icons](https://icons.getbootstrap.com/) propose des centaines d’icônes vectorielles faciles à intégrer.
- **Purge le CSS pour alléger ton site** : Utilise des outils comme [PurgeCSS](https://purgecss.com/) pour supprimer les classes inutilisées et réduire la taille de tes fichiers CSS en production.

---

### **9.2.** Conseils pour de bonnes pratiques

- **Structure ton HTML** : Respecte la hiérarchie `.container > .row > .col` pour une mise en page propre et responsive.
- **Commente ton code** : Explique les parties complexes ou personnalisées pour faciliter la maintenance.
- **N’utilise pas trop de classes personnalisées** : Privilégie les utilitaires Bootstrap pour garder un code léger et cohérent.
- **Teste sur plusieurs navigateurs** : Même si Bootstrap gère la compatibilité, il est toujours bon de vérifier le rendu sur Chrome, Firefox, Edge, Safari, etc.
- **Sois attentif à l’accessibilité** : Utilise les attributs ARIA, les balises sémantiques et veille à la lisibilité des couleurs.

---

### **9.3.** Erreurs fréquentes à éviter

- **Oublier la balise `<meta name="viewport">`** : Sans elle, le responsive ne fonctionne pas correctement sur mobile.
- **Oublier d’inclure le JS Bootstrap** : Certains composants (modales, dropdowns, carrousels…) ne fonctionnent pas sans le fichier JS.
- **Mélanger des versions différentes** : Ne mélange pas des fichiers CSS/JS de Bootstrap 4 et 5 dans le même projet.
- **Surcharger inutilement le CSS** : Trop de styles personnalisés peuvent casser la cohérence et la maintenance.
- **Ignorer les messages d’erreur de la console** : Ils donnent souvent des indices précieux sur les problèmes de scripts ou de dépendances manquantes.
- **Ne pas vérifier la somme des colonnes** : Dans une `.row`, la somme des colonnes doit idéalement faire 12 pour éviter des problèmes d’alignement.

---

### **9.4.** Liens utiles pour progresser

- [Cheat Sheet Bootstrap 5](https://getbootstrap.com/docs/5.0/examples/cheatsheet/)
- [Bootstrap Build (éditeur visuel de thèmes)](https://bootstrap.build/)
- [Bootsnipp (exemples de snippets Bootstrap)](https://bootsnipp.com/)
- [Stack Overflow (aide communautaire)](https://stackoverflow.com/questions/tagged/bootstrap-5)

---

**Astuce finale :**  
N’hésite pas à t’inspirer des exemples de la documentation et à expérimenter dans un bac à sable ([CodePen](https://codepen.io/), [JSFiddle](https://jsfiddle.net/), etc.) pour progresser plus vite !

---
---
---

## **10.** Mini-projets et exemples complets

Dans ce chapitre, tu trouveras des **exemples concrets** et des **mini-projets** pour mettre en pratique les notions vues précédemment. Chaque exemple est commenté pour t’aider à comprendre la logique et la structure du code.

---

### **10.1.** Exemple 1 : Page d’accueil responsive simple

**Objectif :** Créer une page d’accueil avec une barre de navigation, un jumbotron, trois cartes et un pied de page.

````html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Accueil Bootstrap</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>
  <!-- Barre de navigation -->
  <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
    <div class="container">
      <a class="navbar-brand" href="#">MonSite</a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item"><a class="nav-link active" href="#">Accueil</a></li>
          <li class="nav-item"><a class="nav-link" href="#">À propos</a></li>
          <li class="nav-item"><a class="nav-link" href="#">Contact</a></li>
        </ul>
      </div>
    </div>
  </nav>

  <!-- Jumbotron -->
  <div class="container my-5">
    <div class="p-5 mb-4 bg-light rounded-3">
      <div class="container-fluid py-5">
        <h1 class="display-5 fw-bold">Bienvenue sur Bootstrap !</h1>
        <p class="col-md-8 fs-4">Ce site est un exemple de page responsive réalisée avec Bootstrap 5.</p>
        <button class="btn btn-primary btn-lg" type="button">En savoir plus</button>
      </div>
    </div>

    <!-- Cartes -->
    <div class="row">
      <div class="col-md-4 mb-4">
        <div class="card h-100">
          <img src="https://picsum.photos/300/200?random=1" class="card-img-top" alt="Image 1">
          <div class="card-body">
            <h5 class="card-title">Carte 1</h5>
            <p class="card-text">Description de la première carte.</p>
            <a href="#" class="btn btn-outline-primary">Action</a>
          </div>
        </div>
      </div>
      <div class="col-md-4 mb-4">
        <div class="card h-100">
          <img src="https://picsum.photos/300/200?random=2" class="card-img-top" alt="Image 2">
          <div class="card-body">
            <h5 class="card-title">Carte 2</h5>
            <p class="card-text">Description de la deuxième carte.</p>
            <a href="#" class="btn btn-outline-primary">Action</a>
          </div>
        </div>
      </div>
      <div class="col-md-4 mb-4">
        <div class="card h-100">
          <img src="https://picsum.photos/300/200?random=3" class="card-img-top" alt="Image 3">
          <div class="card-body">
            <h5 class="card-title">Carte 3</h5>
            <p class="card-text">Description de la troisième carte.</p>
            <a href="#" class="btn btn-outline-primary">Action</a>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- Pied de page -->
  <footer class="bg-primary text-white text-center py-3">
    &copy; 2025 MonSite - Tous droits réservés
  </footer>

  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
````

**Explications :**

- La structure utilise `.container`, `.row`, `.col-md-4` pour la grille responsive.
- Les composants utilisés : navbar, jumbotron (simulé avec une `div`), cards, footer.
- Les images sont générées aléatoirement via [picsum.photos](https://picsum.photos/).

---

### 10.2. Exemple 2 : Formulaire interactif avec validation

**Objectif :** Créer un formulaire de contact avec validation Bootstrap.

````html
<form class="container my-5 needs-validation" novalidate>
  <div class="mb-3">
    <label for="nom" class="form-label">Nom</label>
    <input type="text" class="form-control" id="nom" required>
    <div class="invalid-feedback">
      Veuillez saisir votre nom.
    </div>
  </div>
  <div class="mb-3">
    <label for="email" class="form-label">Adresse email</label>
    <input type="email" class="form-control" id="email" required>
    <div class="invalid-feedback">
      Veuillez saisir une adresse email valide.
    </div>
  </div>
  <div class="mb-3">
    <label for="message" class="form-label">Message</label>
    <textarea class="form-control" id="message" rows="4" required></textarea>
    <div class="invalid-feedback">
      Veuillez saisir un message.
    </div>
  </div>
  <button class="btn btn-success" type="submit">Envoyer</button>
</form>

<script>
// Validation Bootstrap personnalisée
(function () {
  'use strict'
  var forms = document.querySelectorAll('.needs-validation')
  Array.prototype.slice.call(forms).forEach(function (form) {
    form.addEventListener('submit', function (event) {
      if (!form.checkValidity()) {
        event.preventDefault()
        event.stopPropagation()
      }
      form.classList.add('was-validated')
    }, false)
  })
})()
</script>
````

**Explications :**

- Les classes `.needs-validation` et `.invalid-feedback` permettent d’afficher des messages d’erreur si les champs ne sont pas remplis correctement.
- Le script JS active la validation native du navigateur avec le style Bootstrap.

---

### 10.3. Exemple 3 : Utilisation d’une modale et d’une progress bar

**Objectif :** Afficher une modale au clic sur un bouton et faire progresser une barre de progression.

````html
<div class="container my-5">
  <button class="btn btn-info mb-3" data-bs-toggle="modal" data-bs-target="#infoModal">Afficher la modale</button>
  <div class="progress mb-3">
    <div id="progressBar" class="progress-bar" role="progressbar" style="width: 25%;" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100">25%</div>
  </div>
  <button class="btn btn-primary" onclick="incrementProgress()">Augmenter</button>
</div>

<!-- Modale Bootstrap -->
<div class="modal fade" id="infoModal" tabindex="-1" aria-labelledby="infoModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="infoModalLabel">Information</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Fermer"></button>
      </div>
      <div class="modal-body">
        Ceci est une modale Bootstrap déclenchée par un bouton.
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Fermer</button>
      </div>
    </div>
  </div>
</div>

<script>
function incrementProgress() {
  // Récupère la barre de progression
  var bar = document.getElementById('progressBar');
  var current = parseInt(bar.getAttribute('aria-valuenow'));
  var next = Math.min(current + 10, 100);
  bar.style.width = next + '%';
  bar.setAttribute('aria-valuenow', next);
  bar.textContent = next + '%';
}
</script>
````

**Explications :**

- Le bouton déclenche une modale Bootstrap.
- Un autre bouton augmente la valeur de la barre de progression de 10% à chaque clic.

---

### 10.4. Conseils pour tes propres mini-projets

- Commence par dessiner la structure de ta page (header, contenu, footer).
- Utilise la grille Bootstrap pour organiser tes sections.
- Ajoute progressivement les composants (cartes, formulaires, modales…).
- Teste le rendu sur mobile et desktop.
- Consulte la [documentation officielle Bootstrap](https://getbootstrap.com/docs/5.0/getting-started/introduction/) pour explorer d’autres exemples.

---



## 11. Glossaire

Voici un **glossaire** des principaux termes et concepts rencontrés dans l’univers de Bootstrap et du développement web :

---

- **API** : Interface de Programmation d’Application, ensemble de fonctions permettant à des applications de communiquer entre elles.
- **Bootstrap** : Framework front-end open-source pour créer des sites web responsives et modernes rapidement.
- **Breakpoints** : Points de rupture définissant les tailles d’écran où la mise en page change pour s’adapter (ex : `sm`, `md`, `lg`…).
- **CDN (Content Delivery Network)** : Réseau de serveurs permettant de distribuer rapidement des fichiers (CSS, JS…) partout dans le monde.
- **Classe CSS** : Mot-clé utilisé dans le HTML pour appliquer des styles prédéfinis à un ou plusieurs éléments.
- **Colonne (col)** : Élément de la grille Bootstrap, utilisé pour organiser le contenu horizontalement.
- **Composant** : Élément réutilisable de l’interface utilisateur (bouton, carte, modale, etc.).
- **Container** : Élément Bootstrap qui centre et limite la largeur du contenu.
- **DOM (Document Object Model)** : Représentation structurée d’une page web, manipulable via JavaScript.
- **Flexbox** : Module CSS pour créer des mises en page flexibles et responsives.
- **Framework** : Ensemble d’outils et de conventions facilitant le développement d’applications.
- **Grid System** : Système de grille à 12 colonnes de Bootstrap pour organiser le contenu.
- **Jumbotron** : Ancien composant Bootstrap pour mettre en avant un contenu (remplacé par des utilitaires dans Bootstrap 5).
- **jQuery** : Bibliothèque JavaScript simplifiant la manipulation du DOM et les requêtes AJAX.
- **JSON (JavaScript Object Notation)** : Format léger d’échange de données, utilisé notamment pour les API.
- **Modale (Modal)** : Fenêtre superposée à la page, utilisée pour afficher des informations ou des formulaires.
- **npm (Node Package Manager)** : Gestionnaire de paquets pour JavaScript, utilisé pour installer Bootstrap et d’autres bibliothèques.
- **Responsive** : Qualifie un site web qui s’adapte automatiquement à la taille de l’écran.
- **Row** : Ligne de la grille Bootstrap, contenant des colonnes.
- **SASS/SCSS** : Préprocesseur CSS permettant d’utiliser des variables, des fonctions et des imports dans les feuilles de style.
- **Tooltip** : Infobulle affichée au survol ou au focus d’un élément.
- **Utilitaire** : Classe Bootstrap permettant d’appliquer rapidement un style ou un comportement (ex : `.mt-3`, `.text-center`).

---

**Astuce :**  
N’hésite pas à revenir à ce glossaire pour clarifier un terme rencontré dans la documentation ou dans le code.

---


 ## 12. Ressources et liens utiles

Pour aller plus loin avec Bootstrap et le développement web, voici une sélection de **ressources incontournables** :

---

### Utiles (Perso)

- [Liste d'API publiques](https://free-apis.github.io/#/)
- [SVG Vector and Icons](https://www.svgrepo.com/logo.svg)
- [...]
### Documentation officielle

- [Documentation Bootstrap 5 (fr)](https://getbootstrap.com/docs/5.0/getting-started/introduction/)
- [Bootstrap 5 Components](https://getbootstrap.com/docs/5.0/components/alerts/)
- [Bootstrap 5 Layout](https://getbootstrap.com/docs/5.0/layout/grid/)

---

### Outils et générateurs

- [Bootstrap Build (éditeur visuel de thèmes)](https://bootstrap.build/)
- [Bootswatch (thèmes gratuits)](https://bootswatch.com/)
- [Bootstrap Icons (icônes officielles)](https://icons.getbootstrap.com/)
- [Bootstrap CheatSheet (récapitulatif des classes)](https://getbootstrap.com/docs/5.0/examples/cheatsheet/)
- [PurgeCSS (optimisation CSS)](https://purgecss.com/)

---

### Exemples et inspiration

- [Bootsnipp (exemples de snippets Bootstrap)](https://bootsnipp.com/)
- [CodePen (bac à sable pour tester du code)](https://codepen.io/)
- [JSFiddle (tester et partager du code)](https://jsfiddle.net/)

---

### Communauté et entraide

- [Stack Overflow (questions/réponses Bootstrap)](https://stackoverflow.com/questions/tagged/bootstrap-5)
- [Forum officiel Bootstrap (en anglais)](https://github.com/twbs/bootstrap/discussions)

---

### Autres frameworks et outils complémentaires

- [React-Bootstrap (Bootstrap pour React)](https://react-bootstrap.github.io/)
- [BootstrapVue (Bootstrap pour Vue.js)](https://bootstrap-vue.org/)
- [ng-bootstrap (Bootstrap pour Angular)](https://ng-bootstrap.github.io/)

---

### Pour apprendre et progresser

- [MDN Web Docs (HTML, CSS, JS)](https://developer.mozilla.org/fr/)
- [OpenClassrooms - Cours Bootstrap](https://openclassrooms.com/fr/courses/5664271-creez-des-sites-web-responsives-avec-bootstrap-4)
- [Grafikart - Tutoriels Bootstrap](https://www.grafikart.fr/tutoriels/bootstrap)

---

***Astuce finale :***  
N’hésite pas à explorer ces ressources, à expérimenter et à t’inspirer des exemples pour progresser rapidement et efficacement avec Bootstrap !

---

***THAT'S ALL FOLKS !***

# ANNEXES


LISTE DES EMOTICONES



### **😃 Émoticônes : smiley**
 ````
😀 😃 😁 😂 🤣 😃 😄 😅 😆 😉 😊 😋 😎 😍 🥰 😘 😗 😙 😚 🙂 🤗 🤩🥳 🤔 🤨 😐 😑 😶 🙄 😏 😣 😥 😮 🤐 😯 😪 😫 😴 😌 😛 😜 😝 🤤 😒 😓🥲😔 😕 🙃 🤑 😲 ☹ 🙁 😖 😞 😟🥹😤 😢 😭 😦 😧 😨 😩 🤯 😬 😰 😱 😳 🤪 😵 😡 😠 🤬 😷 🤒 🤕 🤢 🤮 🤧 😇 🤠 🤥 🤫 🤭 🧐 🤓 😈 👿 🤡 👹 👺 💀 ☠ 👻 👽 👾 🤖 💩 😺 😸 😹 😻 😼 😽 🙀 😿 😾 🙈 🙉 🙊 🫠☺️ 🤪 🥴 🥺 😶‍🌫️ 🫥 🫣 🥱 🤔 🫡  🤨 😮‍💨 😤 🫤 😕 😵‍💫 🫨 🥶 🥵 🥸
```` 

---

### **👫 Émoticônes : personnages**
 ````
👶 👧 🧒 👦 👩 🧑 👨 👵 🧓 👴 👲 👳‍♀️ 👳‍♂️ 🧕 👮‍♀️ 👮‍♂️ 👷‍♀️ 👷‍♂️ 💂‍♀️ 💂‍♂️ 🕵️‍♀️ 🕵️‍♂️ 👩‍⚕️ 👨‍⚕️ 👩‍🌾 👨‍🌾 👩‍🍳 👨‍🍳 👩‍🎓 👨‍🎓 👩‍🎤 👨‍🎤 👩‍🏫 👨‍🏫 👩‍🏭 👨‍🏭 👩‍💻 👨‍💻 👩‍💼 👨‍💼 👩‍🔧 👨‍🔧 👩‍🔬 👨‍🔬 👩‍🎨 👨‍🎨 👩‍🚒 👨‍🚒 👩‍✈️ 👨‍✈️ 👩‍🚀 👨‍🚀 👩‍⚖️ 👨‍⚖️ 👰 🤵 👸 🤴 🤶 🎅 🧙‍♀️ 🧙‍♂️ 🧝‍♀️ 🧝‍♂️ 🧛‍♀️ 🧛‍♂️ 🧟‍♀️ 🧟‍♂️ 🧞‍♀️ 🧞‍♂️ 🧜‍♀️ 🧜‍♂️ 🧚‍♀️ 🧚‍♂️ 👼 🤰 🤱 🙇‍♀️ 🙇‍♂️ 💁‍♀️ 💁‍♂️ 🙅‍♀️ 🙅‍♂️ 🙆‍♀️ 🙆‍♂️ 🙋‍♀️ 🙋‍♂️ 🤦‍♀️ 🤦‍♂️ 🤷‍♀️ 🤷‍♂️ 🙎‍♀️ 🙎‍♂️ 🙍‍♀️ 🙍‍♂️ 💇‍♀️ 💇‍♂️ 💆‍♀️ 💆‍♂️ 🧖‍♀️ 🧖‍♂️ 💅 🤳 💃 🕺 👯‍♀️ 👯‍♂️ 🕴 🚶‍♀️ 🚶‍♂️ 👫 👭 👬 💑 👩‍❤️‍👩 👨‍❤️‍👨 💏 👩‍❤️‍💋‍👩 👨‍❤️‍💋‍👨 👪 👨‍👩‍👧 👨‍👩‍👧‍👦 👨‍👩‍👦‍👦 👨‍👩‍👧‍👧 👩‍👩‍👦 👩‍👩‍👧 👩‍👩‍👧‍👦 👩‍👩‍👦‍👦 👩‍👩‍👧‍👧 👨‍👨‍👦 👨‍👨‍👧 👨‍👨‍👧‍👦 👨‍👨‍👦‍👦 👨‍👨‍👧‍👧 👩‍👦 👩‍👧 👩‍👧‍👦 👩‍👦‍👦 👩‍👧‍👧 👨‍👦 👨‍👧 👨‍👧‍👦 👨‍👦‍👦 👨‍👧‍👧 🗣 👤 👥🫂
 ````
---


### **👍Émoticônes : gestes et corps**
 ````
🤳 💪 👈 👉 ☝ 👆 🖕 👇 ✌ 🤞 🖖 🤘 🤙 🖐 ✋ 👌 👍 👎 ✊ 👊 🤛 🤜 🤚 👋 🤟 ✍ 👏 👐 🙌 🤲 🙏 🤝 💅 👂 👃🦻 🦶 🦵 🦿 🦾 🫶 🫳 🫴 🫱 🫲 🫸 🫷 🫰 🤘 🤙 🤌 🤏 🫵 👣 👀 👁 👁️‍🗨️ 🧠 👅 👄🫀 🫁 🩸 🦠 🦷 🦴 🫦 
 ````
 ---
 
### **💘 Émoticônes : sentiments et émotions**
 ````
💋 💘 💝 💖 💗 💓 💞 💕 💌 ❣ 💔 ❤ 🧡 💛 💚 💙 💜 🖤 🧡 🩵 🤎 🩶 🤍 🩷 ❤️‍🩹 💔 ❤️‍🔥 💟
💤 💢 💣 💥 💦 💨 💫 💬 🗨 🗯 💭 🕳
 ````
---

### **👗 Émoticônes : vêtements et accessoires de mode**
 ````
👓 🕶 👔 👕 👖 🧣 🧤 🧥 🧦 👗 👘 👙 👚 👛 👜 👝 🛍 🎒 👞 👟 👠 👡 👢 👑 👒 🎩 🎓 🧢 ⛑ 📿 💄 💍 💎
 ````
---

### **⚽️ Émoticônes : sport et activités**
 ````
⚽️ 🏀 🏈 ⚾️ 🎾 🏐 🏉 🎱 🏓 🏸 🥅 🏒 🏑 🏏 ⛳️ 🏹 🎣 🥊 🥋 🎽 ⛸ 🥌 🛷 🎿 ⛷ 🏂 🏋️‍♀️ 🏋🏻‍♀️ 🏋🏼‍♀️ 🏋🏽‍♀️ 🏋🏾‍♀️ 🏋🏿‍♀️ 🏋️‍♂️ 🏋🏻‍♂️ 🏋🏼‍♂️ 🏋🏽‍♂️ 🏋🏾‍♂️ 🏋🏿‍♂️ 🤼‍♀️ 🤼‍♂️ 🤸‍♀️ 🤸🏻‍♀️ 🤸🏼‍♀️ 🤸🏽‍♀️ 🤸🏾‍♀️ 🤸🏿‍♀️ 🤸‍♂️ 🤸🏻‍♂️ 🤸🏼‍♂️ 🤸🏽‍♂️ 🤸🏾‍♂️ 🤸🏿‍♂️ ⛹️‍♀️ ⛹🏻‍♀️ ⛹🏼‍♀️ ⛹🏽‍♀️ ⛹🏾‍♀️ ⛹🏿‍♀️ ⛹️‍♂️ ⛹🏻‍♂️ ⛹🏼‍♂️ ⛹🏽‍♂️ ⛹🏾‍♂️ ⛹🏿‍♂️ 🤺 🤾‍♀️ 🤾🏻‍♀️ 🤾🏼‍♀️ 🤾🏾‍♀️ 🤾🏾‍♀️ 🤾🏿‍♀️ 🤾‍♂️ 🤾🏻‍♂️ 🤾🏼‍♂️ 🤾🏽‍♂️ 🤾🏾‍♂️ 🤾🏿‍♂️ 🏌️‍♀️ 🏌🏻‍♀️ 🏌🏼‍♀️ 🏌🏽‍♀️ 🏌🏾‍♀️ 🏌🏿‍♀️ 🏌️‍♂️ 🏌🏻‍♂️ 🏌🏼‍♂️ 🏌🏽‍♂️ 🏌🏾‍♂️ 🏌🏿‍♂️ 🏇 🏇🏻 🏇🏼 🏇🏽 🏇🏾 🏇🏿 🧘‍♀️ 🧘🏻‍♀️ 🧘🏼‍♀️ 🧘🏽‍♀️ 🧘🏾‍♀️ 🧘🏿‍♀️ 🧘‍♂️ 🧘🏻‍♂️ 🧘🏼‍♂️ 🧘🏽‍♂️ 🧘🏾‍♂️ 🧘🏿‍♂️ 🏄‍♀️ 🏄🏻‍♀️ 🏄🏼‍♀️ 🏄🏽‍♀️ 🏄🏾‍♀️ 🏄🏿‍♀️ 🏄‍♂️ 🏄🏻‍♂️ 🏄🏼‍♂️ 🏄🏽‍♂️ 🏄🏾‍♂️ 🏄🏿‍♂️ 🏊‍♀️ 🏊🏻‍♀️ 🏊🏼‍♀️ 🏊🏽‍♀️ 🏊🏾‍♀️ 🏊🏿‍♀️ 🏊‍♂️ 🏊🏻‍♂️ 🏊🏼‍♂️ 🏊🏽‍♂️ 🏊🏾‍♂️ 🏊🏿‍♂️ 🤽‍♀️ 🤽🏻‍♀️ 🤽🏼‍♀️ 🤽🏽‍♀️ 🤽🏾‍♀️ 🤽🏿‍♀️ 🤽‍♂️ 🤽🏻‍♂️ 🤽🏼‍♂️ 🤽🏽‍♂️ 🤽🏾‍♂️ 🤽🏿‍♂️ 🚣‍♀️ 🚣🏻‍♀️ 🚣🏼‍♀️ 🚣🏽‍♀️ 🚣🏾‍♀️ 🚣🏿‍♀️ 🚣‍♂️ 🚣🏻‍♂️ 🚣🏼‍♂️ 🚣🏽‍♂️ 🚣🏾‍♂️ 🚣🏿‍♂️ 🧗‍♀️ 🧗🏻‍♀️ 🧗🏼‍♀️ 🧗🏽‍♀️ 🧗🏾‍♀️ 🧗🏿‍♀️ 🧗‍♂️ 🧗🏻‍♂️ 🧗🏼‍♂️ 🧗🏽‍♂️ 🧗🏾‍♂️ 🧗🏿‍♂️ 🚵‍♀️ 🚵🏻‍♀️ 🚵🏼‍♀️ 🚵🏽‍♀️ 🚵🏾‍♀️ 🚵🏿‍♀️ 🚵‍♂️ 🚵🏻‍♂️ 🚵🏼‍♂️ 🚵🏽‍♂️ 🚵🏾‍♂️ 🚵🏿‍♂️ 🚴‍♀️ 🚴🏻‍♀️ 🚴🏼‍♀️ 🚴🏽‍♀️ 🚴🏾‍♀️ 🚴🏿‍♀️ 🚴‍♂️ 🚴🏻‍♂️ 🚴🏼‍♂️ 🚴🏽‍♂️ 🚴🏾‍♂️ 🚴🏿‍♂️ 🏆 🥇 🥈 🥉 🏅 🎖 🏵 🎗 🎫 🎟 🎪 🤹‍♀️ 🤹🏻‍♀️ 🤹🏼‍♀️ 🤹🏽‍♀️ 🤹🏾‍♀️ 🤹🏿‍♀️ 🤹‍♂️ 🤹🏻‍♂️ 🤹🏼‍♂️ 🤹🏽‍♂️ 🤹🏾‍♂️ 🤹🏿‍♂️ 🎭 🎨 🎬 🎤 🎧 🎼 🎹 🥁 🎷 🎺 🎸 🎻 🎲 🎯 🎳 🎮 🎰
````
---

### **🐶🌴 Émoticônes : animaux et plantes**
 ````
🐶 🐱 🐭 🐹 🐰 🦊 🐻 🐼 🐨 🐯 🦁 🐮 🐷 🐽 🐸 🐵 🙈 🙉 🙊 🐒 🐔 🐧 🐦 🐤 🐣 🐥 🦆 🦅 🦉 🦇 🐺 🐗 🐴 🦄 🐝 🐛 🦋 🐌 🐚 🐞 🐜 🦗 🕷 🕸 🦂 🐢 🐍 🦎 🦖 🦕 🐙 🦑 🦐 🦀 🐡 🐠 🐟 🐬 🐳 🐋 🦈 🐊 🐅 🐆 🦓 🦍 🐘 🦏 🐪 🐫 🦒 🐃 🐂 🐄 🐎 🐖 🐏 🐑 🐐 🦌 🐕 🐩 🐈 🐓 🦃 🕊 🐇 🐁 🐀 🐿 🦔 🐾 🐉 🐲 🌵 🎄 🌲 🌳  🌴 🌱 🌿 ☘️ 🍀 🎍 🎋 🍃 🍂 🍁 🍄 🌾 💐 🌷 🌹 🥀 🌺 🌸 🌼 🌻🏵️ 🪻 🌼 🪹 🪺 🪨 ⛰️ 🏔️🦝 🐻‍❄️ 🦓 🫎 🦮 🦫 🦨 🦦 🪽 🪶  🦩 🦚 🦪 🪸
````
---

### **🍏🥂 Émoticônes : nourriture et boissons**
 ````
🍏 🍎 🍐 🍊 🍋 🍌 🍉 🍇 🍓 🍈 🍒 🍑 🍍 🥥 🥝 🍅 🍆 🥑 🥦 🥒 🌶 🌽 🥕 🥔 🍠 🥐 🍞 🥖 🥨 🧀 🥚 🍳 🥞 🥓 🥩 🍗 🍖 🌭 🍔 🍟 🍕 🥪 🥙 🌮 🌯 🥗 🥘 🥫 🍝 🍜 🍲 🍛 🍣 🍱 🥟 🍤 🍙 🍚 🍘 🍥 🥠 🍢 🍡 🍧 🍨 🍦 🥧 🍰 🎂 🍮 🍭 🍬 🍫 🍿 🍩 🍪 🌰 🥜 🍯 🥛 🍼 ☕️ 🍵 🥤 🍶 🍺 🍻 🥂 🍷 🥃 🍸 🍹 🍾 🥄 🍴 🍽 🥣 🥡 🥢🌶️ 🫚 🫑 🧄 🫔  🧊 🫖
````
---

### **🌍 Émoticônes : lieux et bâtiments**
 ````
🌍 🌎 🌏 🌐 🗺 🗾 🏔 ⛰ 🌋 🗻 🏕 🏖 🏜 🏝 🏞 🏟 🏛 🏗 🏘 🏚 🏠 🏡 🏢 🏣 🏤 🏥 🏦 🏨 🏩 🏪 🏫 🏬 🏭 🏯 🏰 💒 🗼 🗽 ⛪ 🕌 🕍 ⛩ 🕋 ⛲ ⛺ 🌁 🌃 🏙 🌄 🌅 🌆 🌇 🌉 ♨ 🌌 🎠 🎡 🎢 💈 🎪🗿
 ````
 ---

### **🚗 Émoticônes : transport**
 ````
🚂 🚃 🚄 🚅 🚆 🚇 🚈 🚉 🚊 🚝 🚞 🚋 🚌 🚍 🚎 🚐 🚑 🚒 🚓 🚔 🚕 🚖 🚗 🚘 🚙 🚚 🚛 🚜 🚲 🛴 🛹 🛵 🚏 🛣 🛤 🛢 ⛽ 🚨 🚥 🚦 🛑 🚧 ⚓ ⛵ 🛶 🚤  🛳 ⛴ 🛥 🚢 ✈ 🛩 🛫 🛬 💺 🚁 🚟 🚠 🚡 🛰 🚀 🛸🛟 🧭 🛞 🦽 🦼 🩼 🏍️ 🛶 🧳
 ````
 --- 


### **🌞 Émoticônes : ciel et météo**
 ````
🌑 🌒 🌓 🌔 🌕 🌖 🌗 🌘 🌙 🌚 🌛 🌜 🌡 ☀ 🌝 🌞 ⭐ 🌟 🌠 ☁ ⛅ ⛈ 🌤  🌥 🌦 🌧 🌨 🌩 🌪 🌫 🌬 🌀 🌈 🌂 ☂ ☔ ⛱ ⚡ ❄ ☃ ⛄ ☄ 🔥 💧 🌊🌋 🏜️ 🏞️ 🏝️ 🏖️ 🌅 🌄 🫧 ✨ 💫 ☄️ 🕳️ 🌌 🪐
 ````
 --- 

### **🛒🎁 Émoticônes : objets**
 ````
⌚️ 📱 📲 💻  ⌨️ 🖥 🖨 🖱 🖲 🕹 🗜  💽 💾 💿 📀 📼 📷 📸 📹 🎥 📽 🎞 📞 ☎️ 📟 📠 📺. 📻 🎙 🎚 🎛 ⏱ ⏲ ⏰ 🕰 ⌛️ ⏳ 📡 🔋 🔌 💡 🔦 🕯 🗑 🛢 💸 💵 💴 💶 💷 💰 💳 💎 ⚖️ 🔧 🔨 ⚒ 🛠 ⛏ 🔩 ⚙️ ⛓ 🔫 💣 🔪 🗡 ⚔️ 🛡 🚬 ⚰️ ⚱️ 🏺 🔮 📿 💈 ⚗️ 🔭 🔬 🕳 💊 💉 🌡 🚽 🚰 🚿 🛁 🛀 🛀🏻 🛀🏼 🛀🏽 🛀🏾 🛀🏿 🛎  🔑 🗝 🚪 🛋 🛏 🛌 🖼 🛍 🛒 🎁 🎈 🎏 🎀 🎊 🎉 🎎 🏮 🎐 ✉️ 📩 📨 📧 💌 📥 📤 📦 🏷 📪 📫 📬 📭 📮 📯 📜 📃 📄 📑 📊 📈 📉 🗒 🗓 📆 📅 📇 🗃 🗳 🗄 📋 📁 📂 🗂 🗞 📰 📓 📔 📒 📕 📗 📘 📙 📚 📖 🔖 🔗 📎 🖇 📐 📏 📌 📍 ✂️ 🖊 🖋 ✒️ 🖌 🖍 📝 ✏️ 🔍 🔎 🔏 🔐 🔒 🔓
 ````
 ------

### **▶️ Symboles**
 ````
☮️ ✝️ ☪️ 🕉 ☸️ ✡️ 🔯 🕎 ☯️ ☦️ 🛐 ⛎ ♈️ ♉️ ♊️ ♋️ ♌️ ♍️ ♎️ ♏️ ♐️ ♑️ ♒️ ♓️ 🆔 ⚛️ 🉑 ☢️ ☣️ 📴 📳 🈶 🈚️ 🈸 🈺 🈷️ ✴️ 🆚 💮 🉐 ㊙️ ㊗️ 🈴 🈵 🈹 🈲 🅰️ 🅱️ 🆎 🆑 🅾️ 🆘 ❌ ⭕️ 🛑 ⛔️ 📛 🚫💯 💢 ♨️ 🚷 🚯 🚳 🚱 🔞 📵 🚭 ❗️ ❕ ❓ ❔ ‼️ ⁉️ 🔅 🔆 〽️ ⚠️ 🚸 🔱 ⚜️ 🔰 ♻️ ✅ 🈯️ 💹 ❇️ ✳️ ❎ 🌐 💠 Ⓜ️ 🌀 💤 🏧 🚾 ♿️ 🅿️ 🈳 🈂️ 🛂 🛃 🛄 🛅 🚹 🚺 🚼 🚻 🚮 🎦 📶 🈁 🔣 ℹ️ 🔤 🔡 🔠 🆖 🆗 🆙 🆒 🆕 🆓 0️⃣ 1️⃣ 2️⃣ 3️⃣ 4️⃣ 5️⃣ 6️⃣ 7️⃣ 8️⃣ 9️⃣ 🔟 🔢 #️⃣ *️⃣ ⏏️ ▶️ ⏸ ⏯ ⏹ ⏺ ⏭ ⏮ ⏩ ⏪ ⏫ ⏬ ◀️ 🔼 🔽 ➡️ ⬅️ ⬆️ ⬇️ ↗️ ↘️ ↙️ ↖️ ↕️ ↔️ ↪️ ↩️ ⤴️ ⤵️ 🔀 🔁 🔂 🔄 🔃 🎵 🎶 ➕ ➖ ➗ ✖️ 💲 💱 ™️ ©️ ®️ 〰️ ➰ ➿ 🔚 🔙 🔛 🔝 🔜 ✔️ ☑️ 🔘 ⚪️ ⚫️ 🔴 🔵 🔺 🔻 🔸 🔹 🔶 🔷 🔳🟥 🟧 🟨 🟩 🟦 🟪 🟫 🔲 ▪️ ▫️ ◾️ ◽️ ◼️ ◻️ ⬛️ ⬜️ 🔈 🔇 🔉 🔊 🔔 🔕 📣 📢 👁‍🗨 💬 💭 🗯 ♠️ ♣️ ♥️ ♦️ 🃏 🎴 🀄️ 🕐 🕑 🕒 🕓 🕔 🕕 🕖 🕗 🕘 🕙 🕚 🕛 🕜 🕝 🕞 🕟 🕠 🕡 🕢 🕣 🕤 🕥 🕦 🕧
 ````
 ---
 
### **🚩 Drapeaux**
````

🏳️ 🏴 🏴‍☠️ 🏁 🚩 🏳️‍🌈 🇦🇫 🇦🇽 🇦🇱 🇩🇿 🇦🇸 🇦🇩 🇦🇴 🇦🇮 🇦🇶 🇦🇬 🇦🇷 🇦🇲 🇦🇼 🇦🇺 🇦🇹 🇦🇿 🇧🇸 🇧🇭 🇧🇩 🇧🇧 🇧🇾 🇧🇪 🇧🇿 🇧🇯 🇧🇲 🇧🇹 🇧🇴 🇧🇦 🇧🇼 🇧🇷 🇮🇴 🇻🇬 🇧🇳 🇧🇬 🇧🇫 🇧🇮 🇰🇭 🇨🇲 🇨🇦 🇮🇨 🇨🇻 🇧🇶 🇰🇾 🇨🇫 🇹🇩 🇨🇱 🇨🇳 🇨🇽 🇨🇨 🇨🇴 🇰🇲 🇨🇬 🇨🇩 🇨🇰 🇨🇷 🇨🇮 🇭🇷 🇨🇺 🇨🇼 🇨🇾 🇨🇿 🇩🇰 🇩🇯 🇩🇲 🇩🇴 🇪🇨 🇪🇬 🇸🇻 🇬🇶 🇪🇷 🇪🇪 🇪🇹 🇪🇺 🇫🇰 🇫🇴 🇫🇯 🇫🇮 🇫🇷 🇬🇫 🇵🇫 🇹🇫 🇬🇦 🇬🇲 🇬🇪 🇩🇪 🇬🇭 🇬🇮 🇬🇷 🇬🇱 🇬🇩 🇬🇵 🇬🇺 🇬🇹 🇬🇬 🇬🇳 🇬🇼 🇬🇾 🇭🇹 🇭🇳 🇭🇰 🇭🇺 🇮🇸 🇮🇳 🇮🇩 🇮🇷 🇮🇶 🇮🇪 🇮🇲 🇮🇱 🇮🇹 🇯🇲 🇯🇵 🎌 🇯🇪 🇯🇴 🇰🇿 🇰🇪 🇰🇮 🇽🇰 🇰🇼 🇰🇬 🇱🇦 🇱🇻 🇱🇧 🇱🇸 🇱🇷 🇱🇾 🇱🇮 🇱🇹 🇱🇺 🇲🇴 🇲🇰 🇲🇬 🇲🇼 🇲🇾 🇲🇻 🇲🇱 🇲🇹 🇲🇭 🇲🇶 🇲🇷 🇲🇺 🇾🇹 🇲🇽 🇫🇲 🇲🇩 🇲🇨 🇲🇳 🇲🇪 🇲🇸 🇲🇦 🇲🇿 🇲🇲 🇳🇦 🇳🇷 🇳🇵 🇳🇱 🇳🇨 🇳🇿 🇳🇮 🇳🇪 🇳🇬 🇳🇺 🇳🇫 🇰🇵 🇲🇵 🇳🇴 🇴🇲 🇵🇰 🇵🇼 🇵🇸 🇵🇦 🇵🇬 🇵🇾 🇵🇪 🇵🇭 🇵🇳 🇵🇱 🇵🇹 🇵🇷 🇶🇦 🇷🇪 🇷🇴 🇷🇺 🇷🇼 🇼🇸 🇸🇲 🇸🇦 🇸🇳 🇷🇸 🇸🇨 🇸🇱 🇸🇬 🇸🇽 🇸🇰 🇸🇮 🇬🇸 🇸🇧 🇸🇴 🇿🇦 🇰🇷 🇸🇸 🇪🇸 🇱🇰 🇧🇱 🇸🇭 🇰🇳 🇱🇨 🇵🇲 🇻🇨 🇸🇩 🇸🇷 🇸🇿 🇸🇪 🇨🇭 🇸🇾 🇹🇼 🇹🇯 🇹🇿 🇹🇭 🇹🇱 🇹🇬 🇹🇰 🇹🇴 🇹🇹 🇹🇳 🇹🇷 🇹🇲 🇹🇨 🇹🇻 🇻🇮 🇺🇬 🇺🇦 🇦🇪 🇬🇧 🏴 🇺🇸 🇺🇾 🇺🇿 🇻🇺 🇻🇦 🇻🇪 🇻🇳 🇼🇫 🇪🇭 🇾🇪 🇿🇲 🇿🇼
````

 # To be continued...>
## Booki – Maquette HTML/CSS accessible et responsive

Ici : https://argoflash.github.io/P2-OC-mentor/

Ce projet est une **intégration front‑end de la page d’accueil Booki**, réalisée en HTML, CSS et un tout petit peu de JavaScript vanilla pour gérer des états d’interface (onglets et filtres).

L’objectif est de reproduire fidèlement la maquette fournie, tout en appliquant de **bonnes pratiques d’accessibilité (WAVE / WCAG)** et un comportement **responsive jusqu’à 320&nbsp;px de large**.

---

### 1. Contenu du projet

- `index.html` : structure de la page (header, recherche, filtres, listes d’hébergements, section “Les plus populaires”, activités et footer).
- `style.css` : mise en forme complète, responsive design, gestion des couleurs, des grilles et des états (hover, actif, etc.).
- JavaScript inclus à la fin de `index.html` pour :
  - **Gérer l’onglet actif** (“Hébergements” / “Activités”) et déplacer la barre bleue.
  - **Rendre les filtres cliquables** (état actif bleu en toggle).

Le site est entièrement statique : **aucun build, aucun framework, aucune dépendance**.

---

### 2. Lancer le projet en local

1. Cloner ou télécharger ce dépôt sur votre machine.
2. Ouvrir le dossier dans votre explorateur de fichiers.
3. **Double‑cliquer sur `index.html`** pour l’ouvrir dans votre navigateur.

> Aucune installation de dépendances n’est nécessaire : tout est géré côté navigateur.

---

### 3. Principales fonctionnalités visuelles

- **Header / Navigation**
  - Logo Booki.
  - Onglets `Hébergements` et `Activités` avec **barre bleue dynamique** suivant l’onglet cliqué.
  - Sur mobile, le logo est centré et les onglets passent sur une ligne en dessous.

- **Bloc de recherche**
  - Champ de saisie pré‑rempli avec `Marseille, France`.
  - Icône de localisation à gauche.
  - Bouton **“Rechercher”** :
    - Affiche le texte sur desktop.
    - Devient un **bouton rond bleu avec une loupe blanche** en dessous de 470&nbsp;px (jusqu’à 320&nbsp;px).

- **Filtres**
  - Filtres cliquables (`Économique`, `Familial`, `Romantique`, `Nos pépites`).
  - Au clic, le filtre passe en **bleu** (état `.active`), clic de nouveau pour le désactiver.
  - Sur les très petits écrans (&lt; 470&nbsp;px), les filtres passent en **colonne** pour garder une bonne lisibilité.

- **Hébergements / Les plus populaires / Activités**
  - Cartes d’hébergements avec image, titre, texte de prix et **notation par étoiles**.
  - Colonne “Les plus populaires” synchronisée en hauteur avec la zone des hébergements et cartes verticalement étirées.
  - Grille d’activités sur 4 colonnes, qui passe à 2 colonnes puis 1 colonne sur les largeurs plus faibles.

---

### 4. Accessibilité (WAVE / WCAG)

Le projet a été travaillé avec l’extension **WAVE** en tête :

- **Structure sémantique**
  - Utilisation de `header`, `main`, `section`, `aside`, `footer`.
  - Titres hiérarchisés (`h1`, `h2`, `h3`) pour faciliter la navigation clavier/lecteur d’écran.

- **Couleurs et contrastes**
  - Texte principal en `#1d1d1d`, texte secondaire en `#4a4a4a` pour un **contraste AA** sur fond clair.
  - Icônes de filtres et étoile “Les plus populaires” en bleu foncé `#003399` pour passer les vérifications WAVE.
  - Étoiles de notation :
    - Pleines : bleu `#0065fc`.
    - Vides : gris `#737373`, plus foncé pour un contraste suffisant même à petite taille.

- **Images et alternatives**
  - Toutes les images disposent d’un attribut `alt` **descriptif** et cohérent avec le contenu de la carte.

- **Interactions clavier / lecteurs d’écran**
  - Boutons des filtres et de la recherche sont de vrais éléments `<button>`.
  - Les états visuels (onglets actifs, filtres actifs) sont portés par des classes et ne perturbent pas la navigation clavier.

---

### 5. Responsive design

Le layout est pensé pour fonctionner du **grand écran** au **mobile 320&nbsp;px** :

- **≥ 1024&nbsp;px**
  - Grille principale à deux colonnes (`Hébergements` / `Les plus populaires`).  
  - Grille d’hébergements sur 3 colonnes, activités sur 4 colonnes.

- **Entre 768&nbsp;px et 1024&nbsp;px**
  - Passage à une seule colonne pour le contenu principal, popularités remontées au‑dessus sur tablette.
  - Grilles d’hébergements/activités adaptées (2 colonnes).

- **≤ 768&nbsp;px**
  - Navigation en colonne, logo centré, contenu full‑width.
  - Grilles à 1 colonne pour une lecture confortable.

- **≤ 470&nbsp;px**
  - Bouton de recherche transformé en **loupe seule**.
  - Filtres empilés en colonne, barre d’information plus espacée des sections.

- **≤ 375&nbsp;px**
  - Barre bleue des onglets positionnée **sous** l’onglet actif pour coller à la maquette mobile.

---

### 6. Technologies utilisées

- **HTML5** : structure sémantique et accessibilité de base.
- **CSS3** : Flexbox, Grid, media queries, variables CSS.
- **JavaScript vanilla** : quelques listeners pour gérer les états actifs (onglets, filtres), sans framework.

---

### 7. Pistes d’amélioration possibles

- Implémenter un **vrai filtrage** des cartes d’hébergements selon les filtres sélectionnés.
- Ajouter une navigation clavier enrichie (gestion focus visuel personnalisé sur les filtres, etc.).
- Extraire le JS dans un fichier dédié (`main.js`) si le projet grossit.
- Ajouter des **tests d’accessibilité automatisés** (axe, pa11y, etc.).

---

### 8. Auteur

Projet réalisé à partir d’une maquette Booki, avec un travail particulier sur :  
**l’accessibilité, le responsive design et la propreté du code HTML/CSS.**



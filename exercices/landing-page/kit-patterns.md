# Kit de patterns - les recettes CSS du projet

Ce kit rassemble les dix mises en page et composants dont vous avez besoin pour la landing page. Chaque recette utilise les classes et les tokens des fichiers de départ (`depart/`) : vous pouvez la coller dans votre `styles.css` et elle fonctionne. Toutes reprennent ce que le support explique au chapitre 6 ; la référence de section est indiquée à chaque fois.

## La règle du kit

Copier est autorisé. Ne pas comprendre ne l'est pas.

Chaque ligne que vous reprenez doit pouvoir être expliquée en une phrase. En soutenance, le jury pointera une ligne au hasard de votre CSS et vous demandera ce qu'elle fait et ce qui se passerait si on la retirait. Le test à faire vous-même avant : dans les DevTools, décochez la propriété et regardez. Si vous savez prédire le résultat, vous avez compris.

Trois habitudes pour bien utiliser ce kit :

1. **Collez au bon endroit.** Votre `styles.css` est organisé en sections (tokens, base, composants, media queries). Une recette de composant va dans la partie composants, jamais au-dessus des tokens ni en dessous de la media query.
2. **Adaptez ce qui est marqué "à adapter".** Ce sont en général deux ou trois valeurs : un espacement, une largeur minimale, une taille de police. Le reste est de la mécanique.
3. **Une recette à la fois.** Collez, sauvegardez, regardez le résultat à 375 px et à 1440 px, puis passez à la suivante. Si vous collez tout d'un coup, vous ne saurez pas d'où vient le problème.

Ce que le kit ne contient pas, volontairement : le mode sombre et le focus visible, déjà écrits dans `depart/styles.css` (vérifiez qu'ils y sont toujours), et les animations, qui relèvent du palier 3 (support, section 6.8).

---

## Recette 1 - Le header : logo à gauche, navigation à droite (6.3 et 6.5)

**Quand** : toujours, c'est le premier bloc de la page.

**HTML attendu** (celui du fichier de départ) :

```html
<header class="header">
  <a class="header__logo" href="#">Nom du produit</a>
  <nav class="header__nav" aria-label="Navigation principale">
    <a href="#features">Fonctionnalités</a>
    <a href="#temoignages">Témoignages</a>
    <a href="#faq">FAQ</a>
  </nav>
</header>
```

**CSS** :

```css
.header {
  display: flex;                    /* les enfants se rangent en ligne */
  flex-wrap: wrap;                  /* sur mobile, la nav passe dessous si elle manque de place */
  justify-content: space-between;   /* logo à gauche, nav à droite */
  align-items: center;              /* alignés verticalement */
  gap: var(--espace-m);
  padding: var(--espace-m);
  border-bottom: 1px solid var(--couleur-bordure);
  position: sticky;                 /* reste visible au défilement */
  top: 0;
  background-color: var(--couleur-fond);   /* sinon le contenu passe dessous en transparence */
  z-index: 100;
}

.header__logo {
  font-family: var(--police-titres);
  font-size: 1.25rem;
  font-weight: 700;
  color: var(--couleur-texte);
  text-decoration: none;
}

.header__nav {
  display: flex;            /* la nav est elle-même une rangée */
  flex-wrap: wrap;
  gap: var(--espace-m);     /* 16 px : trois liens tiennent sur une ligne à 375 px */
}

.header__nav a {
  color: var(--couleur-texte-doux);
  text-decoration: none;
  padding: var(--espace-s) 0;   /* zone cliquable plus haute : cible tactile */
}

.header__nav a:hover {
  color: var(--couleur-primaire);
}
```

**À adapter** : le `gap` de la nav (si vous l'augmentez ou ajoutez un lien, vérifiez à 375 px que la nav ne passe pas sur deux lignes), la taille du logo, le `padding` du header en grand écran via la media query de la recette 10.

**Piège** : si le header est sticky mais que vous oubliez `background-color`, il devient transparent au défilement et le texte de la page passe au travers. Autre piège : trois liens tiennent sur mobile grâce à `flex-wrap`, pas besoin de menu burger (qui demanderait du JavaScript ou un détournement de case à cocher, interdits tous les deux).

---

## Recette 2 - Le hero : tout centré, promesse en gros (6.3)

**Quand** : la première section de `<main>`.

**CSS** :

```css
.hero {
  display: flex;
  flex-direction: column;     /* les enfants s'empilent */
  align-items: center;        /* centrés horizontalement */
  justify-content: center;    /* centrés verticalement dans la hauteur mini */
  gap: var(--espace-m);
  text-align: center;
  min-height: 60vh;           /* 60 % de la hauteur de l'écran */
  padding: var(--espace-xl) var(--espace-m);
  background-color: var(--couleur-surface);
}

.hero__titre {
  font-size: 2rem;
  max-width: 20ch;    /* 20 caractères par ligne maximum : le titre respire */
}

.hero__soustitre {
  color: var(--couleur-texte-doux);
  max-width: 55ch;    /* au-delà de 75 caractères, l'oeil perd la ligne */
}
```

Et dans la media query, en bas du fichier :

```css
@media (min-width: 768px) {
  .hero__titre {
    font-size: 3rem;
  }
}
```

**À adapter** : `min-height`, les deux `max-width` en `ch`, la taille desktop du titre.

**Piège** : une image hero au-dessus de la ligne de flottaison ne doit **pas** avoir `loading="lazy"` : elle doit se charger tout de suite. Réservez le lazy aux images plus bas (recette 9).

---

## Recette 3 - La grille de cartes responsive, sans media query (6.4)

**Quand** : la section features, et toute rangée de cartes ou de logos.

**HTML attendu** :

```html
<section class="features" id="features">
  <h2>Titre de section</h2>
  <div class="features__grille">
    <article class="carte">...</article>
    <article class="carte">...</article>
    <article class="carte">...</article>
  </div>
</section>
```

**CSS** :

```css
.features {
  max-width: var(--largeur-contenu);
  margin: 0 auto;                       /* le bloc est centré dans la page */
  padding: var(--espace-xl) var(--espace-m);
}

.features h2 {
  margin-bottom: var(--espace-l);
  text-align: center;
}

.features__grille {
  display: grid;
  /* Autant de colonnes que la largeur le permet, chacune d'au moins 250 px :
     1 colonne sur mobile, 2 sur tablette, 3 ou 4 sur desktop, sans media query */
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: var(--espace-l);
}
```

**À adapter** : la largeur minimale des cartes (250 px : à 375 px d'écran il n'y a de place que pour une colonne, c'est voulu).

**Piège** : si la valeur du `minmax` dépasse la largeur de l'écran mobile (par exemple 400 px), la grille déborde et vous avez un défilement horizontal à 375 px. Restez sous 300 px.

---

## Recette 4 - La carte : contenu empilé, lien poussé en bas (6.3)

**Quand** : chaque `<article class="carte">` de la grille.

**HTML attendu** :

```html
<article class="carte">
  <img class="carte__image" src="images/point-fort-1.webp" alt="Description utile" width="600" height="338" loading="lazy">
  <h3 class="carte__titre">Point fort</h3>
  <p class="carte__texte">Une phrase d'explication.</p>
  <a class="carte__lien" href="#">En savoir plus sur ce point fort</a>
</article>
```

**CSS** :

```css
.carte {
  display: flex;
  flex-direction: column;     /* on empile, et on pourra pousser le lien en bas */
  gap: var(--espace-s);
  padding: var(--espace-l);
  background-color: var(--couleur-surface);
  border: 1px solid var(--couleur-bordure);
  border-radius: var(--rayon);
}

.carte__image {
  width: 100%;
  aspect-ratio: 16 / 9;       /* toutes les images de cartes ont la même forme */
  object-fit: cover;          /* l'image remplit la zone sans se déformer */
  border-radius: var(--rayon);
}

.carte__texte {
  color: var(--couleur-texte-doux);
}

.carte__lien {
  margin-top: auto;   /* la marge automatique absorbe l'espace restant :
                         le lien se colle en bas, quelle que soit la longueur des textes */
  color: var(--couleur-primaire);
  font-weight: 600;
}
```

**À adapter** : le `padding`, l'`aspect-ratio` si vos images sont carrées (`1 / 1`). La classe `carte__titre` n'a pas de règle ici : elle est posée pour que vous puissiez styler le titre de la carte (taille, couleur) sans toucher à tous les `h3` de la page.

**Piège** : sans `flex-direction: column` sur la carte, `margin-top: auto` ne fait rien. Les deux vont ensemble.

---

## Recette 5 - La preuve sociale : chiffres clés et témoignage (6.3)

**Quand** : la section `preuve`. Choisissez une des deux formes, ou les deux.

**HTML des chiffres clés** :

```html
<section class="preuve" id="temoignages">
  <h2>Ils nous font confiance</h2>
  <div class="preuve__chiffres">
    <div class="chiffre">
      <p class="chiffre__valeur">12 000</p>
      <p class="chiffre__legende">utilisateurs actifs</p>
    </div>
    <!-- deux ou trois chiffres de plus -->
  </div>
</section>
```

**HTML d'un témoignage** (la citation et son auteur restent liés, c'est le rôle de `figure`) :

```html
<figure class="temoignage">
  <blockquote class="temoignage__texte">
    <p>Une phrase de témoignage, courte et concrète.</p>
  </blockquote>
  <figcaption class="temoignage__auteur">Prénom N., rôle ou situation</figcaption>
</figure>
```

**CSS** :

```css
.preuve {
  max-width: var(--largeur-contenu);
  margin: 0 auto;
  padding: var(--espace-xl) var(--espace-m);
  text-align: center;
}

.preuve__chiffres {
  display: flex;
  flex-wrap: wrap;              /* les chiffres passent à la ligne sur mobile */
  justify-content: center;
  gap: var(--espace-l);
  margin-top: var(--espace-l);
}

.chiffre {
  min-width: 140px;
}

.chiffre__valeur {
  font-family: var(--police-titres);
  font-size: 2.5rem;
  color: var(--couleur-primaire);
  line-height: 1;
}

.chiffre__legende {
  color: var(--couleur-texte-doux);
}

.temoignage {
  max-width: 55ch;
  margin: var(--espace-l) auto 0;
  padding: var(--espace-l);
  background-color: var(--couleur-surface);
  border-radius: var(--rayon);
}

.temoignage__texte {
  font-family: var(--police-titres);
  font-size: 1.25rem;
}

.temoignage__auteur {
  margin-top: var(--espace-m);
  color: var(--couleur-texte-doux);
  font-size: 0.9rem;
}
```

**À adapter** : la taille des chiffres, la couleur d'accent.

**Piège** : une rangée de logos partenaires suit la même recette que `.preuve__chiffres` (flex, wrap, centré) ; chaque logo est une `<img>` avec un `alt` qui donne le nom de la marque, et une hauteur fixe (`height: 40px; width: auto`) pour aligner des logos de proportions différentes.

---

## Recette 6 - La FAQ en accordéon natif (6.9)

**Quand** : la section FAQ. Zéro JavaScript, accessible au clavier d'origine.

**HTML attendu** :

```html
<section class="faq" id="faq">
  <h2>Questions fréquentes</h2>
  <details class="faq__item">
    <summary class="faq__question">Première question ?</summary>
    <p class="faq__reponse">La réponse.</p>
  </details>
  <!-- au moins trois questions -->
</section>
```

**CSS** :

```css
.faq {
  max-width: 700px;
  margin: 0 auto;
  padding: var(--espace-xl) var(--espace-m);
}

.faq h2 {
  margin-bottom: var(--espace-l);
}

.faq__item {
  border-bottom: 1px solid var(--couleur-bordure);
}

.faq__question {
  display: flex;
  justify-content: space-between;   /* question à gauche, indicateur à droite */
  align-items: center;
  gap: var(--espace-m);
  padding: var(--espace-m) 0;       /* hauteur confortable : cible tactile */
  font-weight: 600;
  cursor: pointer;
  list-style: none;                 /* masque le triangle par défaut */
}

.faq__question::-webkit-details-marker {
  display: none;                    /* même chose pour Safari */
}

/* On remplace le triangle par un indicateur : sans lui, rien ne dit que ça s'ouvre */
.faq__question::after {
  content: "+";
  font-size: 1.5rem;
  color: var(--couleur-primaire);
  transition: transform 0.2s ease;
}

.faq__item[open] .faq__question::after {
  transform: rotate(45deg);         /* le + devient une croix */
}

.faq__reponse {
  padding-bottom: var(--espace-m);
  color: var(--couleur-texte-doux);
}
```

**À adapter** : le symbole de l'indicateur, la largeur maximale de la section.

**Piège** : si vous masquez le triangle sans ajouter d'indicateur, l'accordéon devient invisible en tant qu'accordéon. Testez au clavier : Tab jusqu'à la question, puis Entrée ou Espace pour ouvrir.

---

## Recette 7 - Le bouton et ses quatre états (6.6 et styleguide)

**Quand** : l'appel à l'action du hero, et la page styleguide qui doit montrer les quatre états.

Deux balises pour un même style : dans la landing, l'appel à l'action est un **lien** (`<a class="btn btn--primaire" href="#">`) parce qu'il emmène quelque part. Dans le styleguide, pour montrer l'état disabled, utilisez un vrai **bouton** (`<button class="btn btn--primaire" disabled>`) : un lien ne peut pas être désactivé, un bouton si.

**HTML du styleguide** :

```html
<div class="sg-rangee">
  <a class="btn btn--primaire" href="#">Default</a>
  <a class="btn btn--primaire" href="#">Hover (survolez-moi)</a>
  <a class="btn btn--primaire" href="#">Focus (Tab jusqu'ici)</a>
  <button class="btn btn--primaire" type="button" disabled>Disabled</button>
</div>
```

**CSS** (remplace le `.btn` du fichier de départ) :

```css
.btn {
  display: inline-block;
  padding: var(--espace-s) var(--espace-l);
  min-height: 44px;                 /* cible tactile : jamais moins */
  border: none;                     /* un <button> a une bordure par défaut, pas un <a> */
  border-radius: var(--rayon);
  font: inherit;                    /* un <button> n'hérite pas de la police, on le force */
  font-weight: 600;
  text-decoration: none;
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.btn--primaire {
  background-color: var(--couleur-primaire);
  color: var(--couleur-fond);       /* blanc sur bleu en clair, sombre sur bleu clair en sombre :
                                       le contraste tient dans les deux modes */
}

.btn--primaire:hover {
  background-color: var(--couleur-primaire-hover);
}

.btn--primaire:focus-visible {
  outline: 3px solid var(--couleur-texte);   /* un outline bleu autour d'un bouton bleu serait invisible */
  outline-offset: 2px;
}

.btn:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}
```

**À adapter** : rien d'obligatoire. Vous pouvez ajouter un `.btn--secondaire` (fond transparent, bordure primaire) sur le même modèle.

**Piège** : `color: #ffffff` en dur sur le bouton casse le contraste en mode sombre, où la couleur primaire s'éclaircit. Passez par le token, c'est tout l'intérêt.

---

## Recette 8 - Le footer (6.3)

**Quand** : le dernier bloc de la page.

**HTML attendu** :

```html
<footer class="footer">
  <p class="footer__mentions">Nom du produit - projet étudiant EFREI, 2026</p>
  <nav class="footer__liens" aria-label="Liens de pied de page">
    <a href="#">Mentions légales</a>
    <a href="#">Contact</a>
    <a href="#">Instagram</a>
  </nav>
</footer>
```

**CSS** :

```css
.footer {
  display: flex;
  flex-wrap: wrap;                  /* mentions et liens se superposent sur mobile */
  justify-content: space-between;
  align-items: center;
  gap: var(--espace-m);
  padding: var(--espace-l) var(--espace-m);
  border-top: 1px solid var(--couleur-bordure);
  color: var(--couleur-texte-doux);
  font-size: 0.9rem;
}

.footer__liens {
  display: flex;
  flex-wrap: wrap;
  gap: var(--espace-m);
}

.footer__liens a {
  color: inherit;                   /* même couleur que le texte du footer */
  padding: var(--espace-s) 0;       /* cible tactile */
}
```

**À adapter** : le contenu, pas la mécanique. Comme `carte__titre`, la classe `footer__mentions` est un crochet BEM sans règle : elle attend votre style si vous en voulez un.

**Piège** : des liens qui ne mènent nulle part (`href="#"`) sont tolérés dans ce projet fictif, mais leur texte doit rester explicite : "Mentions légales", pas "ici".

---

## Recette 9 - Les images : format, alt, dimensions, lazy (5.7)

**Quand** : chaque image de la page.

```html
<!-- Image porteuse de sens : alt descriptif, dimensions déclarées, lazy si elle est sous la ligne de flottaison -->
<img src="images/equipe-en-atelier.webp"
     alt="Trois étudiants autour d'une table, en train de trier des vêtements"
     width="800" height="533"
     loading="lazy">

<!-- Image décorative : alt vide, volontairement -->
<img src="images/motif.svg" alt="" width="200" height="200" loading="lazy">

<!-- Logo en SVG : le nom de la marque dans le alt -->
<img src="images/logo-partenaire.svg" alt="Ville de Villejuif" height="40" width="120">
```

Et dans le CSS de base (déjà dans le fichier de départ) :

```css
img {
  max-width: 100%;    /* une image ne déborde jamais de son conteneur */
  height: auto;
}
```

**À adapter** : tout, ce sont vos images.

**Pièges** : `width` et `height` déclarés en HTML évitent que la page saute pendant le chargement ; ils ne fixent pas la taille affichée, le CSS garde la main. Exportez depuis Figma en WebP (photos) ou SVG (logos, icônes), à la taille réellement affichée : une photo de 4000 px pour une carte de 300 px pèse dix fois trop. Nommez les fichiers en kebab-case, sans accent ni espace.

---

## Recette 10 - La media query unique et le conteneur centré (5.3)

**Quand** : une seule fois, en bas du fichier. Si les recettes précédentes sont en place, il ne reste presque rien à adapter pour le desktop : la grille et les flex ont fait le travail.

```css
@media (min-width: 768px) {
  .hero__titre {
    font-size: 3rem;
  }

  .hero {
    padding: var(--espace-xl) var(--espace-l);
  }

  .header__nav {
    gap: var(--espace-xl);
  }
}
```

**Piège** : tout ce qui est écrit **avant** la media query vaut pour le mobile. Si vous écrivez d'abord des styles desktop puis essayez de les "défaire" pour mobile, vous n'êtes plus en mobile-first et vous doublez votre travail. Si une règle ne s'applique pas sur desktop, vérifiez qu'elle est bien à l'intérieur des accolades du `@media`.

---

## Les trois réflexes de débogage

**1. La page s'affiche sans aucun style.** Le CSS n'est pas chargé. DevTools, onglet Network, rechargez : une ligne `styles.css` en rouge avec un 404 signifie que le chemin dans `<link rel="stylesheet" href="...">` est faux, ou que le fichier ne s'appelle pas exactement comme ça (majuscule, accent, extension `.css.txt`). Vérifiez aussi que vous passez par Live Server et non par un double-clic sur le fichier.

**2. Une règle ne s'applique pas.** DevTools, onglet Elements, cliquez sur l'élément : dans le panneau Styles, votre règle est-elle listée ? Si elle est absente, le sélecteur ne correspond pas (faute de frappe dans le nom de classe, en HTML ou en CSS ; `.carte-titre` et `.carte__titre` ne sont pas la même classe). Si elle est barrée, une autre règle gagne : cherchez laquelle, elle est juste au-dessus.

**3. Un défilement horizontal apparaît à 375 px.** Quelque chose est plus large que l'écran. Suspects habituels, dans l'ordre : une largeur fixe en pixels (`width: 600px` sur un bloc), un `minmax` trop grand dans la grille, une image sans `max-width: 100%`, un mot très long sans espace (une URL), un `padding` ajouté à un élément déjà en `width: 100%` sans `box-sizing: border-box`. Dans les DevTools, survolez les éléments de haut en bas : celui dont la boîte bleue dépasse à droite est le coupable.

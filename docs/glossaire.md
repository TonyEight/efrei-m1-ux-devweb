# Glossaire - Développement web pour designers UX

Les mots que vous entendrez pendant le module, avec l'équivalent Figma quand il existe. À relire avant chaque quiz. Le support de cours détaille chacun d'eux ; ce glossaire sert de pense-bête.

| Mot | Ce que c'est | Côté Figma |
|---|---|---|
| Balise | Une étiquette qui délimite un morceau de contenu : `<p>`, `<h1>`, `<header>` | Un calque nommé |
| Attribut | Une précision sur une balise : `class`, `href`, `alt`, `src` | Une propriété du calque |
| Sémantique | Le sens porté par une balise : un `<header>` dit "en-tête", une `<div>` ne dit rien | Le nommage des calques |
| DOM | L'arbre des éléments de la page tel que le navigateur le voit, visible dans Elements | Le panneau des calques |
| Box model | Contenu, padding, bordure, margin : les quatre couches de tout élément | Le padding de l'auto layout et l'espacement entre frames |
| Padding | L'espace intérieur entre le contenu et la bordure | Padding de l'auto layout |
| Margin | L'espace extérieur entre l'élément et ses voisins | Gap ou distance entre frames |
| Display | La façon dont un élément s'affiche : block (empile), inline (coule), flex, grid | Le type de frame |
| Flexbox | La mise en page en ligne ou en colonne d'éléments qui se suivent | Auto layout |
| Grid | La mise en page en grille à deux dimensions | Layout grid |
| Gap | L'espace entre les enfants d'un flex ou d'un grid | Gap de l'auto layout |
| Media query | Une condition : "si l'écran fait au moins 768 px, applique ces styles" | Une frame de taille différente |
| Breakpoint | La largeur à laquelle une media query s'applique | Les largeurs de vos frames (375, 1440) |
| Mobile-first | Écrire d'abord le CSS du mobile, puis ajouter ce qui change en grand | Dessiner la frame mobile d'abord |
| Viewport | La zone visible de la page dans le navigateur | La frame |
| Variable CSS, token | Une valeur nommée et réutilisée : `--couleur-primaire` | Variables et styles Figma |
| `:root` | L'élément racine de la page, où l'on déclare les variables globales | La collection de variables |
| Sélecteur | Ce qui désigne les éléments qu'une règle CSS va styler : `.carte`, `p`, `.nav a` | Sélectionner tous les calques d'un nom |
| Classe | Une étiquette libre posée sur un élément pour le cibler en CSS | Un nom de composant ou de calque |
| Pseudo-classe | Un état : `:hover`, `:focus-visible`, `:disabled` | Les variants d'un composant |
| Spécificité | La règle qui décide quel style gagne quand deux règles se contredisent | Pas d'équivalent |
| BEM | Une convention de nommage des classes : `.carte`, `.carte__titre`, `.btn--primaire` | Bloc / élément / variant dans le nommage des composants |
| Focus | L'élément qui recevra la prochaine action clavier, signalé par un contour | L'état focus d'un composant |
| Alt | Le texte de remplacement d'une image, lu par les lecteurs d'écran | Une annotation dans la spec |
| Contraste | Le rapport de luminosité entre un texte et son fond : 4,5:1 minimum | Le plugin de contraste |
| Lecteur d'écran | Un logiciel qui lit la page à voix haute : VoiceOver, NVDA, Narrateur | Pas d'équivalent |
| Lighthouse | L'outil d'audit intégré aux DevTools : performance, accessibilité, bonnes pratiques, SEO | Pas d'équivalent |
| WebP, SVG | Les formats d'image modernes : WebP pour les photos, SVG pour les logos et icônes | Les formats d'export |
| Lazy loading | Charger une image seulement quand on s'approche d'elle : `loading="lazy"` | Pas d'équivalent |
| details / summary | Les balises natives de l'accordéon, sans JavaScript | Un composant accordéon avec variant ouvert / fermé |
| prefers-color-scheme | La media query qui détecte le mode clair ou sombre du système | Les modes de variables |
| Kebab-case | `mon-fichier.html` : minuscules, tirets, sans espace ni accent | Le nommage des exports |
| DevTools | Les outils de développement du navigateur : F12 | Le Dev Mode |
| Live Server | L'extension VS Code qui affiche votre page et la recharge à chaque sauvegarde | La prévisualisation |

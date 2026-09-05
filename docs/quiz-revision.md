# Questions de révision

La banque de questions des quiz du module, sans les réponses. Les quiz notés des séances 3 et 4 portent sur ce qui a été fait en séance ; ces questions vous disent à quoi ressemble ce qu'on vous demandera. Réviser, c'est relire le support et retrouver la réponse dans votre propre code.

## Séance 1 - quiz formatif (non noté)

1. Internet et le web, c'est la même chose ?
   a) Oui, ce sont deux noms pour la même chose
   b) Non : le web est un service qui circule sur internet, comme le mail
   c) Non : internet est une partie du web
2. À quoi sert le DNS ?
   a) À chiffrer la connexion
   b) À traduire un nom de domaine en adresse IP
   c) À stocker les pages web
3. Un code de réponse HTTP 404 signifie :
   a) Tout s'est bien passé
   b) La ressource demandée n'existe pas
   c) Le serveur est en panne
4. Dans le modèle client / serveur, le navigateur est :
   a) Le client
   b) Le serveur
   c) L'hébergeur
5. Quel langage décrit la structure et le sens du contenu d'une page ?
   a) HTML
   b) CSS
   c) JavaScript
6. Quel langage décrit la présentation : couleurs, polices, mise en page ?
   a) HTML
   b) CSS
   c) JavaScript
7. Dans les DevTools, quel onglet montre le poids des fichiers chargés par la page ?
   a) Elements
   b) Styles
   c) Network
8. Le box model d'un élément est composé de :
   a) Contenu, padding, bordure, margin
   b) Largeur et hauteur seulement
   c) Police et couleur

## Séances 1 et 2 - matière du quiz noté 1

1. Dans HTTPS, que signifie le S ?
   a) Simple
   b) Sécurisé : la connexion est chiffrée
   c) Serveur
2. Qui transforme le HTML et le CSS en une page affichée à l'écran ?
   a) Le serveur
   b) Le navigateur
   c) VS Code
3. Laquelle de ces balises est sémantique ?
   a) `<div>`
   b) `<span>`
   c) `<header>`
4. Combien de `<h1>` une page doit-elle contenir ?
   a) Un seul
   b) Un par section
   c) Autant qu'on veut
5. À quoi sert `<meta name="viewport" content="width=device-width, initial-scale=1">` ?
   a) À charger les polices
   b) À adapter l'affichage à la largeur de l'écran, indispensable pour le responsive
   c) À traduire la page
6. Votre fichier CSS ne s'applique pas. Quel onglet des DevTools vous dit s'il a été trouvé ?
   a) Styles
   b) Network
   c) Console
7. Que fait `box-sizing: border-box` ?
   a) Inclut le padding et la bordure dans la largeur déclarée
   b) Supprime les marges
   c) Centre l'élément
8. Quel sélecteur cible les éléments qui ont la classe `carte` ?
   a) `carte`
   b) `.carte`
   c) `#carte`
9. Que signifie un attribut `alt=""` vide sur une image ?
   a) L'image est cassée
   b) L'image est décorative et doit être ignorée par les lecteurs d'écran
   c) On a oublié de le remplir
10. Où déclare-t-on les variables CSS pour qu'elles soient disponibles dans toute la page ?
   a) Dans `body`
   b) Dans `:root`
   c) Dans le `<head>`

## Séance 3 - matière du quiz noté 2

1. Dans un header en flexbox, pour placer le logo à gauche et la navigation à droite :
   a) `justify-content: space-between`
   b) `align-items: center`
   c) `flex-wrap: wrap`
2. `display: flex` s'écrit :
   a) Sur chaque enfant à aligner
   b) Sur le parent des éléments à aligner
   c) Sur les deux
3. `grid-template-columns: repeat(auto-fit, minmax(250px, 1fr))` produit :
   a) Autant de colonnes que possible d'au moins 250 px, qui se partagent l'espace
   b) Exactement 250 colonnes
   c) Une seule colonne de 250 px
4. Mobile-first signifie :
   a) On cache le contenu sur mobile
   b) On code la version ordinateur d'abord
   c) Le CSS de base vise le mobile, les media queries `min-width` ajoutent ce qui change en grand écran
5. Pour faire un accordéon accessible sans JavaScript :
   a) Une `<div>` avec `onclick`
   b) `<details>` et `<summary>`
   c) Un `<select>`
6. Le ratio de contraste minimum pour du texte courant (WCAG niveau AA) :
   a) 3:1
   b) 4,5:1
   c) 10:1
7. `outline: none` sur les liens, sans remplacement :
   a) Est une bonne pratique esthétique
   b) Supprime le focus visible et rend la navigation clavier impossible à suivre
   c) N'a aucun effet
8. Quelle part du poids d'une page web représentent généralement les images ?
   a) Environ 10 %
   b) 60 à 70 %
   c) Moins de 1 %
9. `@media (prefers-color-scheme: dark)` :
   a) Force le mode sombre pour tous
   b) Applique des styles quand l'utilisateur a choisi le mode sombre dans son système
   c) Ajoute un bouton de bascule
10. Le RGESN est :
   a) Un référentiel d'accessibilité
   b) Un référentiel d'éco-conception des services numériques
   c) Une norme HTML

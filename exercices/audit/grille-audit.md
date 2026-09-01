# Grille d'audit - accessibilité et éco-conception

Utilisée en séance 3 pour l'audit croisé entre binômes, et comme trame du rapport d'audit individuel. Chaque critère se note OK / à corriger / KO, avec une phrase de constat. Un bon audit cite ce qu'il a observé ("le focus est invisible sur les liens du footer"), pas des généralités.

## 1. Structure et sémantique (DevTools, onglet Elements)

- [ ] La page utilise header, nav, main, section/article, footer (pas une soupe de div)
- [ ] Un seul h1, hiérarchie de titres logique sans saut (h1 puis h2 puis h3)
- [ ] Les liens ont un texte explicite (pas de "cliquez ici")
- [ ] Les champs de formulaire ont un label associé

## 2. Accessibilité

- [ ] Contrastes texte/fond suffisants (pastille couleur des DevTools Chrome : ratio 4,5:1 minimum pour le texte courant)
- [ ] Navigation clavier : tout élément interactif est atteignable avec Tab, dans un ordre logique
- [ ] Focus visible sur chaque élément interactif (jamais de outline: none sans remplacement)
- [ ] Toutes les images ont un alt : descriptif si porteur de sens, vide (alt="") si décoratif
- [ ] La page reste utilisable avec un zoom à 200 %
- [ ] Les accordéons details/summary s'ouvrent au clavier (Entrée ou Espace)
- [ ] Le mode sombre conserve des contrastes suffisants

## 3. Responsive (DevTools, mode responsive)

- [ ] Aucun défilement horizontal à 375 px
- [ ] Le contenu reste lisible et hiérarchisé à 375 px comme à 1440 px
- [ ] Les cibles tactiles font au moins 44 x 44 px sur mobile
- [ ] Les images ne débordent jamais de leur conteneur

## 4. Éco-conception et performance (DevTools, onglet Network, puis Lighthouse)

- [ ] Poids total de la page raisonnable (viser moins de 1 Mo pour ce projet)
- [ ] Images aux formats modernes (WebP, AVIF, SVG) et dimensionnées à leur usage
- [ ] loading="lazy" sur les images sous la ligne de flottaison
- [ ] Pas de ressource inutile chargée (police non utilisée, image cachée en CSS)
- [ ] 2 familles de polices maximum
- [ ] Score Lighthouse : lancer l'audit (onglet Lighthouse) et relever les scores performance et accessibilité

## 5. Qualité du code

- [ ] Aucune couleur ou taille en dur : tout passe par les variables CSS de :root
- [ ] Nommage BEM cohérent
- [ ] Zéro JavaScript, zéro float, zéro framework CSS
- [ ] Fichiers nommés en kebab-case

## Restitution

Pour l'audit croisé (séance 3) : listez les 3 correctifs prioritaires pour le binôme audité, du plus grave au moins grave.

Pour le rapport individuel (après la séance 4) : 1 à 2 pages sur le code généré par IA pendant l'atelier ou sur un site réel de votre choix. Structure attendue : contexte, constats par famille (avec preuves), 3 recommandations priorisées, et ce que vous en retenez en tant que designer.

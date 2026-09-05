# Projet fil rouge - Landing page et mini design system

Projet noté, en binôme, mené sur les séances 2 à 4 du cours. Coefficient : 50 % de la note finale.

## Le pitch

Vous êtes designers dans une jeune équipe produit. Votre mission : inventer un produit ou service fictif et construire sa page d'atterrissage (landing page) en HTML et CSS, accompagnée de son mini design system. Le thème est totalement libre : application mobile, marque, festival, service étudiant, association, jeu... Choisissez un sujet qui vous amuse, vous allez passer trois séances dessus.

À la fin, vous présenterez votre produit en soutenance comme si vous pitchiez à des investisseurs, démo à l'appui.

## Les livrables

Un dossier de projet contenant :

1. **`index.html` + `styles.css`** : la landing page. Structure minimale attendue :
   - un header avec logo (texte ou image) et navigation
   - une section hero : promesse principale, sous-titre, bouton d'appel à l'action
   - une section features : au moins 3 points forts du produit, présentés en grille de cartes
   - une section preuve sociale : témoignages, chiffres clés ou logos partenaires
   - une FAQ : au moins 3 questions, en accordéon
   - un footer : liens, mentions, réseaux sociaux
2. **`styleguide.html`** : la page design system. Le minimum obligatoire tient en trois blocs :
   - vos couleurs : une pastille par token, avec le nom de la variable
   - vos typographies : les deux familles et les niveaux de titres
   - le bouton dans ses quatre états : default, hover, focus, disabled
   En bonus, valorisé dans le critère "design tokens et styleguide" : la carte hors contexte, l'échelle d'espacements, les rayons.
3. **Le pitch de soutenance** : 5 minutes, démo en direct (responsive et mode sombre inclus), plus un enseignement tiré des audits croisés.

## Les contraintes techniques (imposées)

Le thème est libre, la technique ne l'est pas :

| # | Contrainte | Pourquoi |
|---|---|---|
| 1 | HTML sémantique : header, nav, main, section, footer, hiérarchie de titres correcte, un seul h1 | Lecteurs d'écran, SEO, lisibilité du code |
| 2 | Mise en page en flexbox et grid exclusivement (pas de float) | Le standard actuel, miroir de l'auto layout Figma |
| 3 | Responsive mobile-first : irréprochable à 375 px et à 1440 px | La majorité de vos utilisateurs sont sur mobile |
| 4 | Design tokens en variables CSS dans `:root` | La base d'un design system maintenable |
| 5 | FAQ en accordéon avec details / summary | De l'interactivité native, accessible, sans script |
| 6 | Mode sombre via prefers-color-scheme | Le cas d'usage roi des variables CSS |
| 7 | Accessibilité : contrastes suffisants, focus visible, alt sur toutes les images, labels sur les champs | 15 % de la population, et la loi |
| 8 | Éco-conception : images aux formats modernes (WebP/AVIF ou SVG), poids total de page raisonnable, loading="lazy" sous la ligne de flottaison | Sobriété et performance |
| 9 | Zéro JavaScript | Tout est faisable en CSS moderne, prouvez-le |
| 10 | Nommage BEM pour les classes, fichiers en kebab-case | Le vocabulaire commun avec les développeurs |

Autorisé : Google Fonts (2 familles maximum), images libres de droits (Unsplash, unDraw), icônes SVG, et les recettes du fichier `kit-patterns.md` de ce dossier, à condition de pouvoir expliquer chaque ligne que vous reprenez.
Interdit : frameworks CSS (Bootstrap, Tailwind), gabarits ou thèmes tout faits, code généré par IA pour les livrables des séances 2 et 3 (l'atelier IA de la séance 4 a ses propres règles).

## Le socle et les paliers

Vous n'avez pas besoin de tout réussir pour réussir. Le projet est construit en trois paliers ; visez le premier avant de penser au deuxième.

**Le socle** : ce qu'un binôme sans aucune expérience du code peut atteindre en suivant les séances et en utilisant les fichiers de départ et le kit de patterns. Un socle propre vaut environ 60 points sur 100.

- `index.html` contient les six sections demandées, avec les bonnes balises et un seul h1 ; la page se lit correctement sans CSS
- header en flexbox, grille de cartes en grid, aucun défilement horizontal à 375 px, une media query pour les grands écrans
- FAQ en details / summary qui s'ouvre et se ferme
- couleurs et typographies définies en variables dans `:root`, aucune couleur en dur ; le mode sombre fourni dans le fichier de départ fonctionne
- focus visible conservé, alt sur toutes les images, contrastes du texte courant vérifiés dans les DevTools
- images en WebP ou SVG, page sous 1 Mo
- styleguide avec les couleurs, les typographies et le bouton en états default et hover
- pitch fait, démo qui fonctionne

**Le palier 2** (autour de 80 points) : les quatre états du bouton dont focus et disabled, cibles tactiles de 44 px, page utilisable au zoom 200 %, navigation clavier complète dans un ordre logique, `loading="lazy"` sur les images basses, indicateur visuel sur l'accordéon, section preuve sociale et footer complets, nommage BEM cohérent partout.

**Le palier 3** (vers 100) : `prefers-reduced-motion` respecté, une animation ou un scroll-snap discret, score Lighthouse accessibilité de 95 ou plus, styleguide qui documente aussi la carte et les espacements, pitch qui relie vos choix aux utilisateurs.

Le socle est vérifié en fin de séance 2 (HTML et tokens) et en fin de séance 3 (mise en page) : si vous n'y êtes pas, dites-le, c'est prévu et on vous aide.

## Le déroulé

**Avant la séance 2** (1 heure) : constituez votre binôme, choisissez votre concept, esquissez la landing page (papier ou Figma). Le concept est validé en début de séance 2. Un bon concept se décrit en une phrase, a une cible identifiable et trois points forts évidents ; si vous hésitez entre deux idées, prenez celle dont vous pouvez écrire les textes le plus vite.

**Séance 2 - Fondations** : squelette HTML sémantique complet de la landing page, définition des design tokens dans `:root`, début du styleguide. Revue croisée de la sémantique en fin de séance.

**Entre les séances 2 et 3** (2 heures) : terminez le squelette si besoin, écrivez vos vrais contenus (titres, textes, questions de la FAQ, témoignages), choisissez et exportez vos images en format moderne. Arriver en séance 3 avec du contenu réel change tout : on met en page ce qui existe.

**Séance 3 - Mise en page et web responsable** : layout flexbox/grid, responsive, accordéon FAQ. En fin de séance, audit croisé entre binômes avec la grille du dossier `exercices/audit/` : vous repartez avec une liste de correctifs.

**Entre les séances 3 et 4** (3 heures, le principal temps de travail personnel du module) : appliquez les correctifs d'audit, finalisez le styleguide, vérifiez le mode sombre, préparez et répétez le pitch de 5 minutes avec la démo.

**Séance 4 - Finitions et soutenance** : atelier IA (générer une variante d'une section avec un outil de vibe coding, puis auditer le code produit et décider de l'intégrer ou non, en justifiant), puis soutenances.

## Le barème (sur 100)

| Critère | Points | Ce qu'on regarde |
|---|---|---|
| Sémantique HTML | 20 | Balises appropriées, hiérarchie de titres, structure lisible |
| Mise en page et responsive | 25 | Flexbox/grid maîtrisés, mobile-first, aucun débordement horizontal, breakpoints pertinents |
| Accessibilité | 20 | Contrastes, focus visible, alt, labels, navigation clavier complète, zoom 200 % |
| Éco-conception et performance | 15 | Poids de page, formats d'images, lazy loading, sobriété des choix |
| Design tokens et styleguide | 10 | Variables CSS cohérentes, états des composants documentés, mode sombre fonctionnel |
| Soutenance | 10 | Clarté du pitch, qualité de la démo, réponse aux questions |

### Comment chaque critère est noté

Trois niveaux par critère. Le niveau "socle" correspond au socle décrit plus haut : un binôme qui l'atteint partout obtient environ 60 points (12 + 15 + 12 + 9 + 6 + 6).

| Critère (points) | Insuffisant | Socle | Maîtrise |
|---|---|---|---|
| Sémantique HTML (20) | Soupe de div, plusieurs h1 ou aucun, titres dans le désordre : 0 à 8 | Six sections avec les bonnes balises, un h1, hiérarchie correcte, quelques div superflues : 9 à 15 | Balises justes partout, figure et blockquote pour le témoignage, nav secondaire, page parfaite sans CSS : 16 à 20 |
| Mise en page et responsive (25) | Débordement à 375, ou float, ou grille absente : 0 à 10 | Header flex, grille grid, rien ne déborde, une media query fonctionnelle, quelques maladresses en grand écran : 11 à 19 | Fluide à toutes les largeurs, `auto-fit` compris et adapté, hero et sections soignés aux deux tailles, sticky maîtrisé : 20 à 25 |
| Accessibilité (20) | Focus supprimé, alt manquants, contraste insuffisant sur le texte courant : 0 à 8 | Focus visible, alt présents, contrastes du texte courant corrects, ordre clavier logique : 9 à 15 | Cibles 44 px, zoom 200 % impeccable, contrastes vérifiés dans les deux modes, alt rédigés avec soin : 16 à 20 |
| Éco-conception et performance (15) | Images en PNG ou JPEG de plusieurs Mo, page lourde : 0 à 6 | WebP ou SVG, page sous 1 Mo, deux polices maximum : 7 à 11 | Images dimensionnées à l'usage, `loading="lazy"` sous la ligne de flottaison, choix de sobriété visibles et assumés dans le pitch : 12 à 15 |
| Design tokens et styleguide (10) | Couleurs en dur, mode sombre cassé, styleguide absent ou vide : 0 à 4 | Tokens complets dans `:root`, mode sombre du départ fonctionnel, styleguide avec couleurs, typos, bouton default et hover : 5 à 7 | Quatre états documentés, mode sombre adapté à la palette, carte et espacements dans le styleguide : 8 à 10 |
| Soutenance (10) | Pas de démo ou démo qui casse sans reprise, incapacité à expliquer une ligne : 0 à 4 | Pitch clair, démo aux deux tailles et en sombre, réponse correcte à la question de code : 5 à 7 | Pitch qui relie les choix aux utilisateurs, enseignement de l'audit formulé, vocabulaire juste, réponses précises : 8 à 10 |

Pénalités : -5 points par contrainte technique contournée, c'est-à-dire non tentée ou remplacée par ce qui est interdit : JavaScript présent, float pour la mise en page, framework CSS, gabarit tout fait. Une contrainte tentée mais imparfaite (un contraste un peu faible, une media query maladroite) n'est pas pénalisée : elle est simplement notée dans son critère. Un site magnifique qui viole les contraintes perdra face à un site simple qui les respecte toutes.

## Conseils d'équipe

- Commencez moche : structure d'abord, décoration ensuite. Un HTML sémantique bien pensé se style facilement ; l'inverse est un enfer.
- Testez au fil de l'eau dans les DevTools en mode responsive, pas à la fin.
- Le mode sombre coûte 10 lignes si vos couleurs sont toutes en variables, une réécriture complète sinon. C'est un détecteur de tokens bien faits.
- Volez comme des artistes : inspirez-vous des landing pages que vous admirez (Stripe, Linear, Figma), auditez-les dans les DevTools, comprenez leurs choix.
- Répartissez-vous le travail par sections, pas par langage : chacun fait le HTML et le CSS de ses sections, vous partagez les tokens.

## Questions fréquentes

- **"On doit tout apprendre par coeur ?"** Non. Vous devez savoir lire, reconnaître et chercher. Le support et MDN sont ouverts pendant les ateliers et le seront toute votre carrière. Les quiz portent sur ce qui a été fait en séance.
- **"Pourquoi pas Webflow, Framer ou WordPress ?"** Ce sont d'excellents outils de production. Ils ne vous apprennent pas à lire le code qu'ils génèrent. Dans quatre semaines, vous saurez juger ce qu'ils produisent.
- **"Pourquoi zéro JavaScript alors qu'il y en a partout ?"** Parce que c'est un autre cours, et parce que le CSS moderne fait déjà beaucoup. Vous apprenez ici à reconnaître ce qui nécessite du JavaScript, pour le spécifier à un développeur, pas à l'écrire.
- **"Est-ce qu'on peut utiliser le Dev Mode de Figma ?"** Oui pour lire les valeurs (espacements, couleurs, tailles). Non pour copier le CSS généré tel quel : il produit souvent des positions absolues et des largeurs fixes, exactement ce qu'on vous demande d'éviter.
- **"Est-ce qu'on peut demander de l'aide à une IA entre les séances ?"** Pour comprendre un message d'erreur, une propriété, une notion : oui, et c'est une bonne pratique. Pour écrire les livrables des séances 2 et 3 : non, c'est la règle de ce projet, et vous devrez expliquer chaque ligne en soutenance.
- **"Ça compte pour notre portfolio ?"** Oui, si vous le voulez : une landing propre et accessible avec son styleguide est un bon projet de portfolio. Le palier 3 mentionne le déploiement sur GitHub Pages, gratuit.
- **"Il faut un Mac ?"** Non. Tout ce qui est utilisé fonctionne sur Mac, Windows et Linux. Les raccourcis diffèrent (Cmd et Ctrl), le guide d'installation les donne.
- **"Qu'est-ce que je fais si je suis largué ?"** Vous le dites, dès que ça arrive, à votre binôme puis à l'intervenant. Le module est construit avec un socle atteignable par tout le monde et un kit de recettes. Personne n'est laissé sur le bord de la route s'il le dit.

## Ressources

- Fichiers de départ dans `depart/` (squelette commenté, tokens pré-câblés, styleguide vide)
- Kit de patterns dans `kit-patterns.md` : les recettes CSS du projet (header, hero, grille, carte, accordéon, bouton, footer), à adapter à vos tokens
- Grille d'audit dans `../audit/grille-audit.md`
- Glossaire dans `../../docs/glossaire.md` et questions de révision dans `../../docs/quiz-revision.md`
- Le support de cours, chapitres 5 à 8
- MDN pour toute question de syntaxe : https://developer.mozilla.org/fr/

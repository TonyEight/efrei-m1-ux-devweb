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
2. **`styleguide.html`** : la page design system. Elle documente :
   - vos design tokens : couleurs, typographies, espacements, rayons (définis en variables CSS et affichés visuellement)
   - vos composants avec tous leurs états : au minimum le bouton (default, hover, focus, disabled) et la carte
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

Autorisé : Google Fonts (2 familles maximum), images libres de droits (Unsplash, unDraw), icônes SVG.
Interdit : frameworks CSS (Bootstrap, Tailwind), code généré par IA pour les livrables des séances 2 et 3 (l'atelier IA de la séance 4 a ses propres règles).

## Le déroulé

**Avant la séance 2** : constituez votre binôme, choisissez votre concept, esquissez la landing page (papier ou Figma). Le concept est validé en début de séance 2.

**Séance 2 - Fondations** : squelette HTML sémantique complet de la landing page, définition des design tokens dans `:root`, début du styleguide. Revue croisée de la sémantique en fin de séance.

**Séance 3 - Mise en page et web responsable** : layout flexbox/grid, responsive, accordéon FAQ. En fin de séance, audit croisé entre binômes avec la grille du dossier `exercices/audit/` : vous repartez avec une liste de correctifs.

**Entre les séances 3 et 4** : appliquez les correctifs d'audit, finalisez le styleguide, ajoutez le mode sombre si ce n'est pas fait.

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

Pénalités : -5 points par contrainte technique non respectée (JavaScript présent, float utilisé, framework CSS...). Un site magnifique qui viole les contraintes perdra face à un site simple qui les respecte toutes.

## Conseils d'équipe

- Commencez moche : structure d'abord, décoration ensuite. Un HTML sémantique bien pensé se style facilement ; l'inverse est un enfer.
- Testez au fil de l'eau dans les DevTools en mode responsive, pas à la fin.
- Le mode sombre coûte 10 lignes si vos couleurs sont toutes en variables, une réécriture complète sinon. C'est un détecteur de tokens bien faits.
- Volez comme des artistes : inspirez-vous des landing pages que vous admirez (Stripe, Linear, Figma), auditez-les dans les DevTools, comprenez leurs choix.
- Répartissez-vous le travail par sections, pas par langage : chacun fait le HTML et le CSS de ses sections, vous partagez les tokens.

## Ressources

- Fichiers de départ dans `depart/` (squelette commenté, tokens pré-câblés, styleguide vide)
- Grille d'audit dans `../audit/grille-audit.md`
- Le support de cours, chapitres 5 à 8
- MDN pour toute question de syntaxe : https://developer.mozilla.org/fr/

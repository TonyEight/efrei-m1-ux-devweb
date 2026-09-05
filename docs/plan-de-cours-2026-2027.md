# EFREI - M1 UX Design - Développement Web
## Plan de cours 2026-2027 - 14 heures

Public : étudiants M1 UX Design, non développeurs.
Format : 4 séances de 3h30 (adaptable en 7 séances de 2h en coupant aux articulations théorie / atelier).
Fil rouge : projet "Landing page et mini design system", en binôme, sans back-end et sans JavaScript.
Parti pris : le JavaScript est traité en littératie (comprendre, reconnaître, spécifier), jamais en écriture.

Documents associés : `guide-installation.md` (préparation du poste, envoyé aux étudiants avant la séance 1), `glossaire.md` et `quiz-revision.md` (matériel de révision), `../exercices/landing-page/README.md` (énoncé du projet fil rouge). Les notes d'animation de l'intervenant sont conservées hors de ce dépôt.

---

## Le projet fil rouge en bref

Chaque binôme invente un produit ou service fictif (appli, marque, festival, service étudiant...) et livre :

1. **Une landing page** : hero, features, preuve sociale, FAQ, footer.
2. **Une page styleguide** : les design tokens en variables CSS et les composants documentés avec leurs états (default, hover, focus, disabled).

Contraintes techniques imposées (le thème reste totalement libre) :
- HTML sémantique (header, nav, main, section, footer, hiérarchie de titres)
- mise en page flexbox et grid, responsive mobile-first (375 px et 1440 px minimum)
- design tokens en variables CSS
- un accordéon FAQ en details / summary (zéro JS)
- mode sombre via prefers-color-scheme
- exigences accessibilité (contrastes, focus visible, alt, labels) et éco-conception (poids des images, formats modernes)
- aucun JavaScript

---

## Avant la séance 1 - Préparer le poste de travail

L'installation de l'environnement (Chrome, VS Code, extension Live Server) se fait à la maison, pas en séance. Le guide `guide-installation.md` est envoyé avec la convocation à J-7, avec un rappel à J-2. Il contient un test de bon fonctionnement en 8 étapes et un plan B sans installation (vscode.dev) pour les postes verrouillés.

Aucune séance ne dépend d'un poste installé avant la séance 2 : l'atelier de la séance 1 se fait entièrement dans le navigateur.

## Séance 1 - Comprendre le web et lire le code (3h30)

| Durée | Séquence | Contenu (chapitres du support) |
|---|---|---|
| 0h10 | Accueil | Présentation du cours et du dispositif d'évaluation ; sondage d'entrée en 3 questions (expérience du code, aisance avec les fichiers et dossiers, état de l'installation), qui sert à composer les binômes |
| 1h05 | Théorie | Internet vs web, HTTP, client/serveur, les 3 domaines, rôles de HTML/CSS/JS (chap. 1 à 3). Les sections 1.4 et 1.5 sont survolées |
| 0h25 | Démo outillée | DevTools : elements, styles, box model, network, mode responsive (chap. 4.2). VS Code est montré trois minutes, pas installé |
| 1h15 | Atelier 1 | "Autopsie" d'un site réel en binôme, dans le navigateur uniquement : structure sémantique, box model, poids, responsive. Restitution éclair de 1 minute par binôme |
| 0h10 | Clôture | Quiz formatif (non noté) + annonce du fil rouge |
| 0h25 | Mise en route | Vérification des installations faites à la maison avec la checklist du guide, dépannage en circulant, entraide entre binômes. Objectif de sortie : au moins un poste fonctionnel par binôme |

Sortie attendue : chaque étudiant a inspecté un vrai site dans les DevTools et sait y lire une structure HTML, un box model et un poids de page ; chaque binôme dispose d'un poste prêt pour la séance 2.

Travail pour la séance 2 : chaque binôme vient avec un concept de produit fictif et une maquette rapide (papier ou Figma) de sa landing page. Les postes non fonctionnels sont réparés en autonomie avec le guide, ou passent en plan B.

## Séance 2 - HTML sémantique et premiers styles (3h30)

| Durée | Séquence | Contenu |
|---|---|---|
| 1h00 | Théorie | Structure d'une page, sémantique, box model, display, sélecteurs (chap. 5, 6.1, 6.2, 6.6) |
| 0h20 | Lancement projet | Brief détaillé, contraintes, barème ; validation express des concepts par l'intervenant |
| 1h55 | Atelier 2 | Squelette HTML sémantique complet de la landing page + définition des tokens en variables CSS (début du styleguide) |
| 0h15 | Revue croisée | Chaque binôme audite la sémantique d'un autre binôme avec une mini checklist |

Sortie attendue (le socle de la séance) : un `index.html` complet et sémantique, lisible sans CSS, les tokens de couleur et de typographie remplis dans `:root`, la page styleguide qui affiche au moins les couleurs. Un binôme qui n'y est pas en fin de séance est identifié et accompagné avant la séance 3.

Travail pour la séance 3 : terminer le squelette HTML si besoin, écrire les contenus réels (titres, textes, questions de la FAQ), choisir et exporter les images en format moderne. Compter 2 heures par binôme.

## Séance 3 - Mise en page moderne et web responsable (3h30)

| Durée | Séquence | Contenu |
|---|---|---|
| 0h10 | Quiz noté 1 | 10 questions sur les acquis des séances 1 et 2 |
| 1h00 | Théorie | Flexbox et grid en miroir de l'auto layout Figma, responsive mobile-first, interactivité sans JS (chap. 6.3 à 6.5, 6.9) |
| 0h40 | Théorie | Web responsable : accessibilité (EAA, RGAA, gestes du designer) et éco-conception (RGESN, sobriété) (chap. 7) |
| 1h20 | Atelier 3 | Mise en page complète de la landing (flexbox/grid), responsive, accordéon FAQ details/summary ; mode sombre pour les plus avancés |
| 0h20 | Audit croisé | Chaque binôme audite un autre binôme : navigation clavier, contrastes, alt, Lighthouse. Chacun repart avec sa liste de correctifs |

Sortie attendue (le socle de la séance) : header en flexbox, grille de cartes en grid, FAQ en accordéon fonctionnel, aucun défilement horizontal à 375 px, mode sombre vérifié. Le styleguide montre le bouton dans ses états.

Travail pour la séance 4 : appliquer les correctifs d'audit, finaliser le styleguide, préparer le pitch de 5 minutes. Compter 3 heures par binôme. C'est le principal temps de travail hors séance du module : il est annoncé dès la séance 2.

## Séance 4 - IA, finitions et évaluation (3h30)

| Durée | Séquence | Contenu |
|---|---|---|
| 0h10 | Quiz noté 2 | 10 questions sur les acquis de la séance 3 |
| 0h40 | Théorie | Vibe coding et vibe design : paysage 2026, limites du code généré, rôle du designer (chap. 9) |
| 1h00 | Atelier 4 | "Prompter puis auditer" : générer une section ou une variante de sa landing avec un outil IA, puis auditer le code produit (sémantique, accessibilité, éco) ; intégrer ou rejeter en justifiant |
| 1h25 | Soutenances | Pitch produit de 5 minutes par binôme : démo de la landing (dont mode sombre et responsive), styleguide, un enseignement tiré des audits |
| 0h15 | Clôture | Collaboration design-dev (chap. 10 en synthèse), modalités de remise du rapport individuel |

Si l'effectif dépasse environ 16 binômes : soutenances ramenées à 3 minutes ou remplacées par un dépôt vidéo + QCM final de 30 minutes.

---

## Dispositif d'évaluation

| Épreuve | Poids | Modalité |
|---|---|---|
| Projet fil rouge (binôme) | 50 % | Landing page + styleguide + soutenance, grille critériée ci-dessous |
| Rapport d'audit individuel | 30 % | 1 à 2 pages : audit du code généré par IA en séance 4 ou d'un site réel, avec la grille du chap. 7.3. Remise une semaine après la séance 4 |
| Quiz notés + participation | 20 % | Quiz des séances 3 et 4 (2 x 7,5 %) + implication en atelier (5 %) |

### Grille du projet fil rouge (sur 100)

| Critère | Points |
|---|---|
| Sémantique HTML (structure, hiérarchie, balises appropriées) | 20 |
| Mise en page flexbox/grid et responsive mobile-first | 25 |
| Accessibilité (contrastes, focus, alt, labels, clavier) | 20 |
| Éco-conception et performance (poids, formats d'images, sobriété) | 15 |
| Design tokens et styleguide (variables CSS, états des composants, mode sombre) | 10 |
| Soutenance (clarté du pitch, qualité de la démo) | 10 |

Le rapport individuel garantit une note personnelle derrière le travail de binôme ; les quiz assurent le rappel espacé des notions.

Le projet définit un socle explicite (ce qui garantit la moyenne) et des paliers au-delà, détaillés dans l'énoncé du projet. Les pénalités ne s'appliquent qu'aux contraintes non tentées ou volontairement contournées (JavaScript, framework CSS, float), jamais à une contrainte tentée et mal exécutée, qui est notée dans son critère.

Charge de travail hors séance, annoncée aux étudiants dès la séance 1 : environ 1 heure avant la séance 2 (concept et maquette), 2 heures avant la séance 3, 3 heures avant la séance 4, puis 2 heures pour le rapport individuel. Soit 8 heures environ par étudiant sur le module.

### Alignement objectifs / évaluation

- Comprendre le fonctionnement du web : quiz + séance 1
- Lire et produire du HTML/CSS sémantique et moderne : projet fil rouge
- Concevoir accessible et sobre : critères dédiés du projet + rapport d'audit
- Utiliser l'IA en gardant le contrôle qualité : atelier 4 + rapport d'audit
- Collaborer avec les développeurs : styleguide (tokens, états) + vocabulaire évalué en soutenance

Ratio global : environ 40 % théorie, 45 % pratique, 15 % évaluation.

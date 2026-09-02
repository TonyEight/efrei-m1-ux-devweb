# Préparer son poste de travail avant la séance 1

Ce guide s'adresse aux étudiants du M1 UX Design pour le cours de développement web. Il vous prend 20 à 30 minutes, à faire chez vous avant la première séance, avec une bonne connexion. Nous n'écrirons pas de code en séance 1, mais nous vérifierons ensemble que tout fonctionne : un poste prêt, c'est une séance 2 qui démarre sans perdre une minute.

Si quelque chose bloque, ne passez pas des heures dessus : notez ce qui s'affiche à l'écran (une capture suffit) et nous réglerons ça ensemble en fin de séance 1. Le plan B tout en bas vous permet de suivre quoi qu'il arrive.

## Ce qu'il vous faut

- Un ordinateur portable sous macOS ou Windows 11, que vous apporterez à chaque séance. Sous Linux, l'installation est similaire, demandez-nous si besoin.
- Le mot de passe de votre session (macOS le demande pour autoriser une application, Windows peut le demander à l'installation).
- Environ 500 Mo d'espace disque libre.

Nous utilisons trois outils, tous gratuits : un navigateur (Chrome), un éditeur de code (VS Code) et deux extensions de VS Code.

## Étape 1 - Le navigateur : Chrome

Les outils de développement montrés en cours sont ceux de Google Chrome. Brave et Microsoft Edge sont construits sur le même moteur et conviennent aussi. Safari et Firefox restent utiles pour tester vos pages, mais ne les utilisez pas comme navigateur principal pour le cours.

1. Rendez-vous sur https://www.google.com/chrome/ et installez Chrome si ce n'est pas déjà fait.
2. Ouvrez n'importe quel site, puis appuyez sur **F12** (Windows) ou **Cmd + Option + I** (Mac). Un panneau s'ouvre sur le côté ou en bas : ce sont les DevTools. Refermez-les avec la même touche. C'est tout ce que nous vérifions pour l'instant.

Sur Mac, si vous voulez aussi utiliser les outils de Safari : Safari > Réglages > Avancé, puis cochez "Afficher les fonctionnalités pour les développeurs web". Le menu Développement apparaît dans la barre de menus.

## Étape 2 - L'éditeur : VS Code

Visual Studio Code est l'éditeur de code le plus utilisé au monde. Il est gratuit et fonctionne de la même façon sur Mac et Windows.

### Sur macOS

1. Allez sur https://code.visualstudio.com/ et cliquez sur **Download for Mac**. Le site détecte votre type de Mac ; si on vous demande de choisir, prenez la version **Universal**.
2. Vous récupérez un fichier `.zip` dans Téléchargements. Double-cliquez dessus : une application **Visual Studio Code** apparaît à côté.
3. **Glissez cette application dans le dossier Applications** du Finder. Cette étape compte : si vous lancez VS Code depuis Téléchargements, il fonctionnera mal et vous le perdrez au premier rangement.
4. Ouvrez VS Code depuis Applications (ou depuis Spotlight : Cmd + Espace, tapez "code"). Au premier lancement, macOS demande si vous voulez vraiment ouvrir une application téléchargée d'Internet : cliquez sur **Ouvrir**.

### Sur Windows 11

1. Allez sur https://code.visualstudio.com/ et cliquez sur **Download for Windows**. Vous récupérez un fichier `VSCodeUserSetup-x64-....exe` dans Téléchargements.
2. Lancez-le. Si un écran bleu "Windows a protégé votre ordinateur" apparaît, cliquez sur **Informations complémentaires** puis **Exécuter quand même** : il s'agit d'une vérification de réputation, pas d'une alerte de sécurité réelle sur ce fichier.
3. Acceptez la licence, gardez le dossier d'installation proposé, puis sur l'écran des tâches supplémentaires **cochez** :
   - "Ajouter l'action Ouvrir avec Code au menu contextuel des fichiers"
   - "Ajouter l'action Ouvrir avec Code au menu contextuel des dossiers"
   - "Ajouter au PATH" (déjà coché normalement)
4. Terminez l'installation et lancez VS Code.

Cette version "User Setup" s'installe dans votre profil et ne demande pas de droits administrateur. Si votre poste est géré par l'école et refuse quand même l'installation, voyez le plan B.

### Régler la langue (facultatif)

VS Code est en anglais par défaut. Ce guide et le support de cours donnent les libellés en français quand ils existent, mais l'anglais fonctionne tout aussi bien. Pour passer en français : ouvrez la palette de commandes (**Ctrl + Shift + P** sur Windows, **Cmd + Shift + P** sur Mac), tapez `display language`, choisissez "Configure Display Language" puis "Français" : VS Code propose d'installer le pack de langue et redémarre.

## Étape 3 - Les extensions

Les extensions ajoutent des fonctions à VS Code. Nous en utilisons deux, la troisième est un confort.

1. Dans VS Code, cliquez sur l'icône **Extensions** dans la barre de gauche (quatre carrés dont un détaché), ou appuyez sur **Ctrl + Shift + X** (Windows) / **Cmd + Shift + X** (Mac).
2. Dans le champ de recherche en haut, tapez le nom de l'extension, vérifiez l'auteur, puis cliquez sur **Install**.

| Extension | Auteur à vérifier | À quoi ça sert |
|---|---|---|
| **Live Server** | Ritwick Dey | Affiche votre page dans le navigateur et la recharge à chaque sauvegarde. Indispensable. |
| **Prettier - Code formatter** | Prettier | Range votre code automatiquement : indentation propre, lisible, sans effort. |
| Auto Rename Tag | Jun Han | Quand vous renommez une balise ouvrante, la fermante suit. Confort. |

Il existe plusieurs extensions nommées "Live Server" : prenez celle de **Ritwick Dey**, c'est celle du cours.

Pour que Prettier travaille tout seul : palette de commandes (Ctrl/Cmd + Shift + P), tapez `settings json`, choisissez "Preferences: Open User Settings (JSON)" et ajoutez ces deux lignes entre les accolades (s'il y a déjà du contenu, ajoutez une virgule après la dernière ligne existante) :

```json
"editor.formatOnSave": true,
"editor.defaultFormatter": "esbenp.prettier-vscode"
```

Si cette manipulation vous inquiète, sautez-la : nous la ferons ensemble en séance.

## Étape 4 - Le test qui prouve que tout fonctionne

C'est l'étape la plus importante. Elle reproduit exactement ce que vous ferez à chaque séance.

1. Sur votre Bureau, créez un dossier nommé `test-devweb` (tout en minuscules, sans espace ni accent : c'est une habitude à prendre dès maintenant).
2. Dans VS Code : menu **File > Open Folder** (Fichier > Ouvrir le dossier) et choisissez ce dossier. Ouvrez toujours un **dossier**, jamais un fichier isolé : Live Server en a besoin. Si VS Code demande si vous faites confiance aux auteurs du dossier, répondez oui, c'est le vôtre.
3. Dans le panneau de gauche, passez la souris sur le nom du dossier et cliquez sur l'icône **Nouveau fichier**. Nommez-le exactement `index.html`.
4. Dans ce fichier vide, tapez un point d'exclamation `!` puis appuyez sur la touche **Tab**. VS Code génère tout le squelette d'une page HTML.
5. Entre `<body>` et `</body>`, écrivez : `<h1>Mon poste est prêt</h1>`
6. Sauvegardez : **Ctrl + S** (Windows) ou **Cmd + S** (Mac).
7. Faites un **clic droit** dans le fichier et choisissez **Open with Live Server**. Votre navigateur s'ouvre sur une adresse qui commence par `http://127.0.0.1:5500` ou `http://localhost:5500` et affiche votre phrase en gros.
8. Revenez dans VS Code, changez le texte de la phrase, sauvegardez : le navigateur se met à jour tout seul.

Si le point 8 fonctionne, tout est en place.

### Votre checklist

Cochez mentalement, ou notez ce qui manque pour la séance 1 :

- [ ] Chrome (ou Brave, Edge) ouvre les DevTools avec F12 ou Cmd + Option + I
- [ ] VS Code se lance depuis Applications (Mac) ou depuis le menu Démarrer (Windows)
- [ ] L'extension Live Server de Ritwick Dey est installée
- [ ] `!` puis Tab génère un squelette HTML dans un fichier `.html`
- [ ] Open with Live Server ouvre la page dans le navigateur, et la page se met à jour à la sauvegarde

## Si ça coince

**Mac : "Visual Studio Code ne peut pas être ouvert car il provient d'un développeur non identifié", ou l'application est "endommagée".** Faites un clic droit sur l'application puis **Ouvrir**, et confirmez. Si le message persiste : Réglages système > Confidentialité et sécurité, descendez jusqu'à la mention de VS Code et cliquez sur **Ouvrir quand même**.

**Mac : VS Code est installé mais je ne le retrouve plus.** Il est probablement resté dans Téléchargements. Déplacez-le dans Applications, puis relancez-le depuis là.

**Windows : l'installation demande un mot de passe administrateur que je n'ai pas.** Vous avez téléchargé la version "System Installer". Retournez sur le site, cliquez sur la petite flèche à côté du bouton de téléchargement et choisissez **User Installer**.

**Windows : "Open with Live Server" n'apparaît pas dans le clic droit.** Deux causes possibles : l'extension n'est pas installée (vérifiez dans l'onglet Extensions), ou vous avez ouvert le fichier seul au lieu du dossier (File > Open Folder).

**Windows : le pare-feu demande une autorisation pour "Code" ou "Node".** Autorisez sur les réseaux privés. Live Server crée un petit serveur local sur votre machine, c'est normal.

**Le navigateur affiche une page vide ou "impossible d'accéder au site".** Regardez en bas à droite de VS Code : s'il y a écrit "Port : 5500", le serveur tourne. Tapez alors `http://localhost:5500` à la main dans la barre d'adresse. S'il y a écrit "Go Live", cliquez dessus pour démarrer le serveur.

**Mon fichier s'appelle `index.html.txt`.** Windows masque les extensions par défaut. Dans l'Explorateur de fichiers : menu Affichage > Afficher > **Extensions de noms de fichiers**. Renommez ensuite le fichier en `index.html`. Faites cette manipulation dès maintenant, elle vous évitera une famille entière de bugs mystérieux.

**Les accents s'affichent bizarrement dans le navigateur.** Vérifiez que la ligne `<meta charset="UTF-8">` est bien présente dans le `<head>`. Le squelette généré par `!` l'inclut.

**Rien ne marche et je n'ai plus de temps.** Passez au plan B et venez en séance 1 avec votre ordinateur : nous réglerons le reste ensemble.

## Plan B - travailler sans rien installer

Si votre poste refuse toute installation (ordinateur d'entreprise ou de l'école verrouillé, panne, etc.), vous pouvez suivre le cours et rendre votre projet avec un simple navigateur :

1. Dans **Chrome ou Edge** (pas Safari ni Firefox pour cette fonction), ouvrez https://vscode.dev : c'est VS Code qui tourne dans un onglet.
2. Cliquez sur **Open Folder** et choisissez un dossier de votre ordinateur. Le navigateur demande l'autorisation d'y accéder : acceptez. Vous créez et modifiez vos fichiers exactement comme dans VS Code.
3. Pour voir votre page : dans l'Explorateur de fichiers ou le Finder, double-cliquez sur votre `index.html`. Il s'ouvre dans le navigateur. Après chaque sauvegarde, appuyez sur **F5** pour recharger : c'est la seule différence avec Live Server, où c'est automatique.

Ce plan B suffit pour l'ensemble du projet fil rouge, dont les fichiers sont tous dans un même dossier. Il est en revanche moins confortable au quotidien : dès que vous pouvez installer VS Code, faites-le.

## Pour aller plus loin

Le chapitre 4 du support de cours détaille la configuration de VS Code (raccourcis, autres extensions utiles) et l'usage des DevTools. Nous le parcourons en séance 1.

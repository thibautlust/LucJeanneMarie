# Qui veut gagner des noces d'or ? (édition mariage)

Deux fichiers : `index.html` (le jeu, sur l'écran) et `vote.html` (la page de vote des invités, ouverte par QR code), plus un dossier `photos`.

## 1. Créer la base Firebase (5 min, pour le vote du public)

1. Va sur https://console.firebase.google.com, clique sur « Ajouter un projet » (Analytics inutile).
2. Dans « Créer » (ou « Build »), choisis « Realtime Database », puis « Créer une base de données », région en Europe, mode verrouillé.
3. Onglet « Règles » : remplace tout par le contenu de `regles-firebase.json`, puis « Publier ».
4. Onglet « Données » : copie l'adresse en haut, du type `https://xxxx-default-rtdb.europe-west1.firebasedatabase.app`.

## 2. Publier sur GitHub Pages

1. Dépôt **public** : envoie `index.html`, `vote.html` et le dossier `photos`.
2. « Settings > Pages » : « Deploy from a branch », branche `main`, dossier `/ (root)`, Save.
3. Le jeu est ensuite disponible à `https://TON-PSEUDO.github.io/NOM-DU-DEPOT/`.

## 3. Régler le jeu

Tout se règle en haut du script de `index.html`, entre « À PERSONNALISER » et « FIN DE LA PERSONNALISATION » :

- `NOMS` : les prénoms des mariés.
- `FIREBASE_URL` : l'adresse de ta base Firebase (vide = le joker « Public » donne des pourcentages simulés).
- `PHOTO_FINALE` : la photo de l'écran final (fichier du dossier `photos` ou adresse https).
- Les questions, une par ligne : `Question | A | B | C | D | bonne lettre | photo`. La photo est facultative (nom de fichier du dossier `photos`, ex. `q1.jpg`, ou adresse https). 15 questions maximum ; avec moins de 15, certains paliers de l'échelle sont sautés pour finir aux noces d'or.

Pour modifier le fichier : sur GitHub, ouvre `index.html`, clique sur le crayon, modifie, puis « Commit changes ». La page est republiée en une à deux minutes (recharge avec Ctrl+Maj+R).

## 4. Répéter avant la fête

- Lance le jeu sur l'ordinateur, clique sur « Public » : un QR code apparaît.
- Scanne-le avec un téléphone en 4G (wifi coupé), vote, et vérifie que les barres bougent.
- Teste avec 2 ou 3 amis en même temps, y compris le 50/50 (les réponses cachées sont grisées sur les téléphones).

## Photos

Dossier `photos` à la racine du dépôt, noms de fichiers identiques à ceux écrits dans les questions (majuscules comprises). Réduis les images (moins de 300 Ko). Sans photo ou si le fichier est introuvable, la question s'affiche sans image.

## Échelle des noces

La liste est dans `var P=[...]` du script (par exemple `{n:1,name:"coton"}`) : modifie les noms si tu préfères d'autres appellations.

## Bon à savoir

- Les trois aides (50/50, Public, Appel à un ami) sont utilisables sans limite. Chaque appel au public lance un nouveau vote, et chaque téléphone ne peut voter qu'une fois par vote.
- Le dépôt étant public, les questions, les réponses, les photos et l'adresse Firebase sont lisibles par quiconque ouvre le code de la page. Les règles Firebase limitent ce qu'on peut faire avec la base (envoyer un vote A, B, C ou D), mais un invité curieux pourrait lire les réponses dans le code.
- Le vote demande une connexion internet sur les téléphones et sur l'ordinateur du jeu.

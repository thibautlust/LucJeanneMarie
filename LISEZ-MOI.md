# Qui veut gagner des millions ? Édition mariage

Deux fichiers : `index.html` (le jeu, sur l'écran) et `vote.html` (la page de vote des invités, ouverte par QR code).

## 1. Créer la base Firebase (5 min)

1. Va sur https://console.firebase.google.com, clique sur « Ajouter un projet » (Analytics inutile).
2. Dans le menu « Créer » (ou « Build »), choisis « Realtime Database », puis « Créer une base de données ». Choisis une région en Europe et le mode verrouillé.
3. Onglet « Règles » : remplace tout le contenu par celui de `regles-firebase.json`, puis « Publier ».
4. Onglet « Données » : copie l'adresse en haut, du type `https://xxxx-default-rtdb.europe-west1.firebasedatabase.app`.

## 2. Publier sur GitHub Pages

1. Crée un dépôt **public** sur GitHub, puis « Add file > Upload files » et envoie `index.html` et `vote.html`.
2. « Settings > Pages » : source « Deploy from a branch », branche `main`, dossier `/ (root)`, puis Save.
3. Après une minute ou deux, le jeu est disponible à `https://TON-PSEUDO.github.io/NOM-DU-DEPOT/`.

## 3. Régler le jeu

1. Ouvre l'adresse du jeu, déroule « Personnaliser ».
2. Saisis les prénoms, tes vraies questions et colle l'adresse Firebase, puis « Enregistrer et relancer le jeu ».
3. Les questions et l'adresse restent dans **ce navigateur** : le jour J, utilise le même ordinateur et le même navigateur. Ne les mets pas dans le dépôt public.

## 4. Répéter avant la fête

- Lance le jeu sur l'ordinateur, clique sur « Public » : un QR code apparaît.
- Scanne-le avec un téléphone en 4G (wifi coupé), vote, et vérifie que les barres bougent.
- Teste avec 2 ou 3 amis en même temps, y compris le joker 50/50 (les réponses cachées sont grisées sur les téléphones).

## Bon à savoir

- Chaque téléphone ne peut voter qu'une fois par question. Un nouveau vote est possible à chaque nouvelle question.
- Sans adresse Firebase, le joker « Public » retombe sur des pourcentages simulés.
- La base n'est pas protégée par mot de passe : un invité très motivé pourrait tricher en lisant le code. Pour un mariage, le risque est faible.
- Le vote fonctionne sans compte pour les invités, mais il faut une connexion internet sur les téléphones et sur l'ordinateur du jeu.

## Photos des questions

1. Crée un dossier `photos` à côté de `index.html` sur GitHub et mets-y tes images (`q1.jpg`, `q2.jpg`…). Pense à les réduire (moins de 300 Ko chacune) pour qu'elles s'affichent vite.
2. Dans « Personnaliser », ajoute le nom du fichier en dernier champ de chaque question : `Question | A | B | C | D | B | q2.jpg`. Une adresse https complète fonctionne aussi.
3. Sans photo (champ vide ou fichier introuvable), la question s'affiche simplement sans image.
4. Le dépôt étant public, les photos qui s'y trouvent sont visibles par toute personne qui connaît l'adresse.

## Échelle des noces

Les noms des noces sont dans la liste `var P=[...]` au début du script de `index.html` (par exemple `{n:1,name:"coton"}`). Les appellations varient selon les régions : modifie-les si tu préfères une autre liste.

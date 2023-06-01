# Hashing & Objects

Dans cette section, on parle du dossier ``.git`` qui se trouve dans n'importe quel repo git. On y retrouve plusieurs informations importantes:
* 3 Fichiers
    * config
    * HEAD
    * Index
* 2 Dossiers
    * Objects
    * Refs

## Config file

Fichier de configuration. Permet de setter certaines informatoins (le compte utilisé ou l'éditeur utilisé lors d'un rebase). C'est un fichier local.

La commande ``git config`` permet de setter des valeurs dans le fichier de config.

Le fichier de config global devrait être situé :
* En Windows : C:/Users\\.gitconfig
* En Linux : ~/.gitconfig

On peut configurer la moindre chose jusque la couler dans un terminal.

## Le fichier des refs
Dans ce dossier il y a plusieurs sous-dossiers. C'est ici que git enregistre les références à des branches ou des commits.

### Le dossiers heads
Dans ce dosser, git fait un fichier pour chaque branche du répertoire avec comme nom, le nom de la branche.

Ces fichiers ne font que contenir un hash de commit. Ce commit correspond au HEAD de la branche. Le HEAD de la master n'est pas le même que le HEAD d'une branche avec des commits en plus donc le contenu ne sera pas le même. Par contre, une branche qui vient d'être créée contiendra le même hash de commit que le fichier de master/main.

### Le dossier tags
Il fonction de la même manière, chaque tags contient le hash du commit qui comporte ce tag.

### Le dossier remote
Fonctionne de la même manière que le dossier HEAD mais cette fois ci, pour les remotes.

## Le fichier HEAD
Il contient la référence du fichier sur laquelle la HEAD est actuellement dans le repo. C'est une référence à une référence.

Ex : cat HEAD ==> refs/head/main si on est sur la main.

Si on est en état **detached HEAD**,alors on a le hash du commit sur lequel on est.

## Le dossier objects

Contient tout le contenu de git. Il y a les backup, les commits et l'historique de git. C'est uen grosse partie de la session.

Ce dossier semble uniquement contenir des fichiers binaires ou compressés.

Il contient une liste de hash qui représente les différentes informations. La commande ``git hash-object`` permet de hasher un fichier ou une donnée. La commande ``git cat-file`` permet de lire un hash.

Git est un stckage de donnée clé-valeur. Les clés sont les valeurs de SHA-1 et les valeurs sont des fichiers ou des commits.

## Blobs
Les blobs (binary large objects) sont des objets utilisé par git qui enregistre uniquement le contenu de fichier. Les fichiers binaires contenu dans le dossier **objects** dont les noms sont des hash sont tous des blobs.

## Trees
Les trees enregistre la structure d'une dossier. Chaque arbre contient des pointeurs vers des blobs ou d'autres arbres. Ce sont aussi des objets cotenu dans le dossiers **objects**.

## Commits
Les commits sont des objets qui combine des trees avec des informations sur le contexte qui a abouti à l'arbre courant. Les commits ont une référence au commit parent, l'auteur, le commiter et le message de commit.
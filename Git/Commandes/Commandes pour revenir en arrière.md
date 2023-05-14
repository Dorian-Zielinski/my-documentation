# Commande pour revenir en arrière
## Git Checkout
```
git checkout <commit-hash>
```
Déplace le HEAD à un autre commit. On se retrouve dans un état de **detached HEAD**. Cet état nous autorise à faire des modifications et éventuellement de créer une nouvelle branche avec ces changements.

Il faut utiliser ``git switch <branch>`` ou ``git switch -`` pour revenir sur la branche.


```
git checkout HEAD <filename>
```
Permet d'annuler les modifications sur le ou les fichiers choisis. S'applique uniquement sur les fichiers qui sont **unstaged**.

Version plus courte : ``git checkout -- <filename>``

## Git Restore
```
git restore <filename>
```
Permet d'annuler les changements fait sur un ou plusieurs fichiers.

```
git restore --source HEAD~1 <filename>
```
Permet de restaurer le contenu d'un fichier à l'état qu'il à dans un autre commit.

```
git restore --staged <filename>
```
Permet de passer des fichiers staged à l'état de unstaged.

## Git Reset
```
git reset <commit-hash>
```
Permet de réinitialiser le répertoire à l'état d'un commit précédent.

Par défaut, la commande garde les modifications qui ont été faites mais supprime les commits.

Ajouter l'option ``--hard`` permet de supprimer les commits et les modifications.

## Git revert
```
git revert
```
Fait la même chose que le ``reset`` mais créé un **nouveau commit** qui va inverser/undo les changements au lieu de tout simplement les supprimer dans le reset.
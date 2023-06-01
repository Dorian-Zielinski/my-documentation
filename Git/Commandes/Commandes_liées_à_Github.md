# Commandes liées à Github
## Remote
```
git remote add <name> <url>
```
Permet de connecter un répertoire local à un repertoire github.

Le nom usuel est ``origin``

## Push

```
git push <remote> <branch>
```
Permet d'envoyer les modifications/commits d'une branche locale sur une branche remote de github.

Dans la plupart des cas, la branche remote a le même nom que la branche locale. Mais il est possible d'avoir une branche locale et une branche remote qui n'ont pas le même nom:
```
git push <remote> <branch>:<remote-branch>
```
Exemple : ``git push origin pancake:waffle``

L'option **-u** (upstream ou --set-upstream) permet de connecter une branche locale avec une branche remote. Ce qui permet d'utiliser la commande ``git push`` sans mentionner la remote et le nom de la branche.

**Important :** Lorsque l'on veut push les commits d'une branche, on n'est pas obligé d'être sur cette branche pour le faire. Il est possible de le faire depuis une autre branche.

## Pull

```
git checkout origin/master
```
Permet de savoir ce qu'il y avait dans le origin/master

```
git fetch
```
Récupère les changements du repo Github pour les mettre dans le local repository mais ces changements ne seront pas intégré dans le Workspace. Donc permet de récupérer les infos sans les appliquer.

```
git pull
```
Cette commande met à jour le HEAD de notre branche. Fait donc comme le ``git fetch`` mais qui applique aussi les changements dans le Workspace.
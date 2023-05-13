# Commandes Git
## git switch
Permet de changer de branche.

L'option ``-c`` permet de créer une branche depuis là où l'on est et d'avoir le HEAD directement sur celle-ci.
## git branch
Affiche la liste des branches en local.

Option :
* ``-v`` permet de donner plus d'information sur chaque branche (ex : information sur le dernier commit de la branche)
* ``-m`` pour renommer une branche
```
git branch -m <new_name>
```
* ``-u`` permet de setter le upstream de la branche
```
git branch <name> -u origin/<name>
```

## git clone
Permet de copier une répertoire git en local à l'aide d'une url
```
git clone <url>
```
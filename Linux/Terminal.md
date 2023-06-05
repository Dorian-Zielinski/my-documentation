# Terminal

## Modification sur le terminal

Il est possible d'apporter des modifications au terminal en modifiant le fichier ``~/.bashrc``.

Pour rappel, le ``~\`` signifie que l'on est à la racine du dossier utilisateur, juste en dessous du dossier ``home``. Aussi, le fichier commence par un **``.``** ce qui signifie que le fichier est caché et que l'on doit utiliser la commande ``ls -a`` pour le voir.

### Changer la langue de Git
Il est possible de changer la langue de git en modifiant le fichier ``~/.bashrc``.
Il suffit d'ajouter la ligne suivante :

```
alias git='LANG=en_GB git'
```

### Modification de prompt
Le prompt est la ligne qui précède l'endroit où l'on peut écrire nos commandes dans un terminal. Il est possible de la modifier en passant par le fichier ``~/.bashrc``.

Dans l'exemple qui va suivre, j'ai changer le prompt afin d'afficher le  nom de la branche de HEAD.

En premier, il faut une méthode qui va permettre de récuperer le nom de la branche de HEAD.
```
# Get the HEAD branch name of the current repo
parse_git_branch()
{
  local BRANCH=$(git symbolic-ref HEAD --short 2> /dev/null)
  if [[ ! -z "$BRANCH" ]]
  then
    echo "($BRANCH)"
  fi
}
```

La commande ```git symbolic-ref HEAD --short``` affiche le nom de la branche sur laquelle on se trouve, et on utilise ```2> /dev/null``` pour masquer les erreurs potentielles.

Maintenant que la fonction est créé, il suffit de modifier la variable ```$PS1```. C'est une variable d'environnement qui contient la valeur du "prompt".

Voici un exemple :
```
# Regenerate the prompt
CYAN='\e[0;36m'       # Cyan
GREEN_BOLD='\e[1;32m'   # Green - Bold
BLUE_BOLD='\e[1;34m'    # Blue - Bold
WHITE_BOLD='\e[1;37m'   # White - Bold
RESET='\e[0m'         # Text Reset
export PS1="${GREEN_BOLD}\u:${BLUE_BOLD}\w ${CYAN}\$(parse_git_branch)${WHITE_BOLD} $"
```
Lien du [tuto](https://blog.pabuisson.com/2014/04/branche-git-courante-dans-le-prompt/)
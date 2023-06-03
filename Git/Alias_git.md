# Les Alias Git
## Le fichier de config global de Git

Par défaut, le fichier de config global se situe dans le ``home directory`` et le nom du dossier est ``.gitconfig``.

Le commande suivante permet d'afficher la config global

```
cat  ~/.gitconfig
```

Il semble que le fichier de config global se situe ici : ``~/.config/igt/config``

Pour afficher une valeur de la configuration globale

```
git config --global <option>
```

Exemple : ``git config --global user.email``

Pour réécrire une variable du fichier de configuration

```
git config --global <option> "newValue"
```

## Les alias

Les alias git sont des raccourcis. Voici à quoi peut ressembler la partie alias dans le fichier de configuration globale.

```
[alias]
    s = status
    l = log
```

Les alias sont configurables via le fichier ou via le terminal.

En ce qui concerne les arguments, il n'y a pas de problème. On peut utiliser un alias puis ajouter les arguments dans le terminal.

Il est aussi possible de rajouter des arguments dans l'alias par exemple :

```
ol = log --oneline -10
```
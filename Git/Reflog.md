# Reflog

Le reflog (reference log) est un ensemble de logs/records de ce que fait git. C'est une liste de chaque log pointé par des références.

Les logs sont pris à chaque changement du HEAD. Donc lors d'un nouveau commit ou d'un changement de branche, un nouveau log est créé.

Ces logs sont dans **.git/logs/HEAD**

**Limitations** : les logs sont uniquement locaux (normal) et ils ne sont pas permanent. Par défaut, ils expirent au bout de 90 jours.

La commande **git reflog** permet de voir les logs.

Voici les sous commandes disponibles :
* show
* expire
* delete
* exists

La commande la plus utilisée est **show**. Le sautres ne sont quasiment pas utiliséses.

Ex : ```git reflog show HEAD``` pour voir le fichier dans logs/HEAD

Le hash en début de ligne correspond au commit du HEAD après la modification via une commande git. Ceci permet de récupérer des commits qui ont pu être supprimé.

Il est possible de voir les logs d'une branche en particulier :
```
git reflog show <branch_name>
```

## Structure d'une référence
```
name@{qualifier}
```

``HEAD@{2}`` ==> where HEAD was 2 moves ago

Il est possible d'utiliser ces refs avec la commande ``checkout`` ou ``diff``
```
git checkout HEAD@{2}
```

```
git diff HEAD@{0} HEAD@{5}
```

## Timed references

Chaque entré à un time stamp. On peut utiliser pour remonter dans le temps au lieu d'utiliser les refs.

Ex :
* master@{one.week.ago}
* bugfix@{2.days.ago}
* main@{yesterday}

## Reflog rescue

Pour récupérer un commit disparu :
* D'abord, on regarde le commit qui a disparu : ``git reflog show HEAD``
* Ensuite, on fait un ``git reset --hard <hash_perdu>`` en mentionnant le commit qui a disparu et que l'on a récupéré via le show

Les reflogs sont aussi très efficace poru résoudre des prolèmes suite à un rebase. Même si l'historique a été réécris, il est toujorus possible de revenir en arrière.
# Les Tags Git
Dans la majorité des cas, les tags sont utilisés pour marquer des numéros de versions.

On peut tagguer des commits en particuliers.

Il y a 2 types de tags :
* Le lightweight tag : juste un label sur un commit
* Le annotated tag : il enregistre des méta-données en plus (comme un message de commit)

## Semantic versioning

C'est une liste de règle pour nommer les tags. Ex : 2.4.1
* 2 => Major release : Significant changes. Features may be deleted or changed substantially
* 4 => Minor release : New Feature, just some new stuff
* 1 => Patch release

1.0.0 => The first release

La commade ``git tag`` permet de voir l'ensemble des tag d'un repo.

L'option ``-l`` pour lister tous les tags (c'est implicite dans git tag)

On peut rajouter un filtre de ce type ``*beta*`` pour avoir uniquement les tags avec beta dedans.

Ex : ``git tag -l "*3.8*"``


Il est possible de faire un checkout sur les tag :
```
git checkout <tag>
```

Il est aussi possible de faire un diff sur les tags :
```
git diff <tag1> <tag2>
```

## Créer un tag
Créer un **lightweight tag** sur le commit actuel (le HEAD).
```
git tag <tagName>
```

Créer un **annotated tag** pour ouvrir un éditeur afin d'afficher des informations supplémentaires.
```
git tag -a <tagName>
```

Pour visionner les méta-données d'un tag.
```
git show <tagName>
```

Pour spprimer un tag.
```
git tag -d <tagName>
```

## Pusher les tags
Par défaut, les tags ne sont pas pushé. Il faut le préciser si on veut pusher des tags.
```
git push --tags
```
# Le rebase interactif
Pour lancer un rebase interactif : 
```
git rebase -i HEAD~X
```

Le **X** correspond au nombre de commit que l'on veut remonter.

Renoomer : **reword** ou **r**

**squash** ou **s** : permet de regrouper les changements de plusieurs commits dans un seul.

**fixup** ou **f** : permet de squash mais ne garde pas le message de commit du commit qui doit disparaître. A utiliser lorsque l'on veut squash de nombreux commit mais sans conserver les nom de commit.
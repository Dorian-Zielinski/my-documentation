# Tips
## Ajouter des fichiers au dernier commit
Ajouter un ou plusieurs fichuers au dernier commit existant :
```
git add <files>
git commit --amend --no-edit
```
L'option ``--no-edit`` permet de ne pas changer le nom du commit

## Configuration par défaut
Lien vers la configuration à avoir par défaut sur git : https://spin.atomicobject.com/2020/05/05/git-configurations-default/

```
git config -l
```
Permet d'afficher la configuration de git.
# Git Diff

```
git diff
```
Liste tous les changements depuis el dernier commit. S'applique uniquement sur les fichiers "unstaged", il ne va pas comparer les fichiers qui ont déjà été ajoutés.

Les options ``--staged`` ou ``--cached`` permet de comparer seulement les fichiers staged.

```
git diff HEAD
```
Liste tous le changements depuis le dernier commit, que les fichiers soit staged ou non.

L'option ``HEAD~x`` liste tous les changements entre HEAD et le xième commit derrière le HEAD.

```
git diff [filename]
```
Compare un ou plusieurs fichiers au lieu de tous ceux du commit.

```
git diff branch1..branch2
```
Permet de comparer le HEAD de deux branches différentes. **branch1** est le fichier **a** et **branch2** est le fichier **b**.

```
git diff commit1..commit2
```
Permet de comparer deux commits de la même branche.
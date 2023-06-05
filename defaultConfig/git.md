# Ma configuration par défaut de git

```
[core]
	editor = code --wait
[alias]
	s = status
	ol = log --oneline -10
	b = branch
	sw = switch
	cm = commit -m
	cam = commit -am
	amend = commit --amend
	amend-ne = commit --amend --no-edit
	a = add
	aa = add .
    r = rebase
	ri= rebase -i
```

Liste de commande :
```
git config --global alias.s "status"
git config --global alias.ol "log --oneline -10"
git config --global alias.b "branch"
git config --global alias.sw "switch"
git config --global alias.cm "commit -m"
git config --global alias.cam "commit -am"
git config --global alias.amend "commit --amend"
git config --global alias.amend-ne "commit --amend --no-edit"
git config --global alias.a "add"
git config --global alias.aa "add ."
git config --global alias.r "rebase"
git config --global alias.ri "rebase -i"

```
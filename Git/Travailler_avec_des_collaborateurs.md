# Travailler avec des collaborateurs
## Centralized Workflow
Mauvaise idée, beaucoup tropde conflit si plusieurs personnes travaillent dessus

## Feature Branch Workflow
Permet de passer d'un sujet à un autre sans avoir de problème de conflit.

## Pull request
Les pull requests ne sont pas natives à Git, elles sont propres à Github. C'est identique aux merge request de Gitlab.

## Règle de protection

Dans Git : Settings -> branches- Add rule
Permet d'empêcher :
* les push directement sur certaines branches
* de forcer des reviews avant des push
* et d'autres possibilités 

## Forking & cloning
Permet à chaque développer d'avoir son propre répertoire. Avec ces commandes, il est possible de copier un répertoire et de faire les modifications que l'on souhaite.

Il semble possible de faire des pull requests de fork sur une repo main. Ceci permet à des personnes qui ne sont pas collaborateurs à la base d'ajouter leur idée sur un projet.

Il est possible d'avoir une méthode de travail ou plusieurs personnes ont leur propre fork et les changement sont ajoutés au répertoire principal.

Dans une fork, même s'il n'est pas possible de push sur le répertoire d'origine, il est possible de pull pour être à jour et avoir toutes les modifications qui ont été faites.
Habituellement, le nom de la remote d'origine est **upstream** ou **original**
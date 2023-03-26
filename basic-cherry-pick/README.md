# Git Kata: Les bases du cherry picking

Dans ce kata, on veut a deux branches, `master` et `feature`. On a travaillé et progressé sur ces branches indépendamment. Cependant, il y a quelques changements dans la branche `feature` qu'on voudrait appliquer sur `master` dès maintenant, sans fusionner l'ensemble de la branche `feature`.

Git possède une fonctionnalité permettant de ne prendre que tel ou tel changement, nommé `cherry-pick`. On dit à git quels commits on souhaite sélectionner et git va ajouter les changements de ce commit sur la branche courante.

Git peut faire un cherry pick sur un seul commit ou une plage de commits.

## Mise en place

1. Lancez le script `source setup.sh` sous Linux ou `.\setup.ps1` dans PowerShell sous Windows

## Étapes

Actuellement nous avons cet historique dans le dépôt : 

    A - B - C - D         master
          \
            E - F - G - H feature

Comme vous le voyez, la branche `feature` et la branche `master` ont progressé avec des commits différents. On veut sélectionner F et G et les appliquer sur la branche `master` de manière à obtenir un historique ressemblant à 

    A - B - C - D - F - G master
          \
            E - F - G - H feature

1. Utilisez `git log --oneline --graph --all` pour afficher l’historique
1. Utilisez `cat` pour voir le contenu de `names.txt`. Ce fichier a été changé dans le commit F
1. Utilisez `cat` pour voir le contenu de `sentence.txt`. Ce fichier a été changé dans le commit G
1. Utilisez `git cherry-pick <commit_hash_F>` pour faire un cherry pick du commit F sur votre branche
1. Utilisez `git log --oneline` pour voir les changements dans l'historique et notamment que F est maintenant le nouveau commit de la branche `master`
1. Utilisez `cat` pour voir le contenu de `names.txt`, constatez qu'il a changé
1. Utilisez `git reset --hard HEAD^` pour effacer le cherry picking de l'historique de manière à tester un cherry-picking avec une plage de commits
1. Utilisez `git log --oneline --graph` pour vérifier que le commit n'est plus dans la branche
1. Nous sommes maintenant dans l'état de départ, utilisez maintenant `git cherry-pick <commit_hash_F>^..<commit_hash_G>` pour faire un cherry pick de la plage de commits de F à G (les 2 commits). Faites particulièrement attention et n'oubliez pas le symbole chapeau `^` après le hash du premier commit (Consultez la section *Note* ci-dessous pour comprendre pourquoi il est requis.)
1. Utilisez `git log --oneline --graph` pour consulter l'historique
1. Utilisez `cat` pour voir le contenu de `names.txt` et de `sentence.txt` et constatez les changements !
1. Combien de commits on été ajoutés suite au cherry pick?

## Note

Quand on utilise une plage de commits, le premier (et donc plus ancien) hash de commit spécifié n'est **pas** inclus dans la plage. Tous les autres suivants, jusqu'au deuxième hash de commit (le plus récent donc), inclus, sont inclus dans la plage.

Pour éviter ce problème, utilisez le symbole chapeau `^` après le premier hash de commit pour dire à git que vous voulez sélectionner comme borne, le commit précédent, ce qui a pour conséquence d'inclure le commit dans la plage.

Par exemple

    git cherry-pick ABCD..EFGH

n'inclus pas le ABCD. Vous devez à la place ajouter un chapeau après ABCD pour dire à git de l'inclure, comme ceci :

    git cherry-pick ABCD^..EFGH

Référence: https://www.tollmanz.com/git-cherry-pick-range/
Référence: https://git-scm.com/docs/git-cherry-pick

## Commandes utiles

- `git cherry-pick <ref>`
- `git reset --hard <ref>`
- `git log --oneline --graph --all`

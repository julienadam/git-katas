# Git Kata: Les bases de `revert`

## Mise en place

1. Lancez `source setup.sh` (ou `.\setup.ps1` sous PowerShell)

## Étapes

Dans cet exercice, quelques modifications se sont glissées dans l'historique que nous voudrions éliminer. Les commits sont publics, on ne peut donc pas les retirer simplement. A la place, nous devons retirer les changements non désirés d'une manière sécurisée.

1. Utilisez `git log --oneline` pour regarder l'historique
1. Utilisez `cat` pour voir le contenu `greeting.txt`
1. Utilisez `git revert` sur le commit le plus récent pour retirer les changements de ce commit.
1. Utilisez `git log --oneline` pour regarder l'historique
1. Est-ce que la commande revert a ajouté ou retiré un commit ?
1. Utilisez `cat` pour voir le contenu de `greeting.txt`
1. Utilisez `ls` pour inspecter le contenu du répertoire de travail
1. Utilisez `git log --oneline` pour trouver le has du commit qui a ajouté les identifiants au répertoire
1. Utilisez `git revert` pour annuler le commit qui a ajouté les identifiants.
1. Utilisez `git log --oneline` pour regarder l'historique
1. Utilisez `ls` pour inspecter le contenu du répertoire de travail
1. Combien de commits ont été ajoutés ou changés par le dernier revert ?
1. Utilisez `git show` avec le hash du commit sur lequel vous avez fait un revert.
1. On a fait un revert sur le fichier contenant les identifiants, il est donc retiré du repertoire de travail. Pour autant, est-il retiré de git ?

## Commandes utiles
- `git revert <ref>`
- `git log --oneline`
- `git show <ref>`

# Rebase Exec

## Mise en place

1. Lancez le script `source setup.sh` sous Linux ou `.\setup.ps1` dans PowerShell sous Windows

## Étapes

En local, nous avons créé une série de commits. On souhaite les envoyer en master mais également les tester un à un.

Notre suite test est contenue dans le fichier `test.sh`. On va utiliser `git rebase --exec` pour exécuter la suite de test sur chaque commit au fur et à mesure du déroulement de l'opération de rebase. un tag `initial-commit` a été posé sur le premier commit dans l'historique.

1. Lancez le script de test `./test.sh` pour vérifier que le commit le plus récent passe bien les tests.
1. Utilisez `git rebase -i --exec ./test.sh initial-commit` pour lancer le rebase en mode interactif avec lancement du script de test sur tous les commits. Il n'y a rien à changer dans la proposition qui est faite par git.
1. Les tests vont se lancer et échouer sur un commit particulier. Ils échouent parce que le script est modifié dans ce commit. Il faudra le réparer.
1. Modifiez dans `test.sh`
    - `One test failed` en `all tests pass`
    - `exit 1` en `exit 0`
1. Mettez `test.sh` en staging puis modifiez le commit avec `git commit --amend` pour réparer le script de test.
1. Exécutez `git rebase --continue` pour continuer la validation
1. Vous pouvez lancer `verify.sh` (ou `verify.ps1` sous PowerShell) pour valider votre solution.

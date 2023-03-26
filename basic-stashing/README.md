# Git Kata: Les bases de l'utilisation des stashes

## Mise en place

1. Lancez le script `source setup.sh` sous Linux ou `.\setup.ps1` dans PowerShell sous Windows

## Étapes

Vous travaillez sur votre projet. Vous avez du travail en cours dans le staging et des changements dans le répertoire de travail, pas encore dans le staging.

Soudainement, vous prenez connaissance d'un bug en production. Vous allez mettre votre travail dans un stash, corriger le bug, et retourner à votre travail originel.


1. Explorez le dépôt
   1. Qu'y a-t-il en cours dans le répertoire de travail ?
   2. Et dans le staging ?
   3. A quoi ressemble l'historique de commits ?
   >*Remarquez que le fichier file.txt a des changements en staging et des changements hors staging (seulement dans le répertoire de travail)*
2. Utilisez `git stash` pour créer un stash avec votre travail
   1. Maintenant, qu'y a-t-il en cours dans le répertoire de travail ?
   2. Et dans le staging ?
   3. A quoi ressemble l'historique de commits ?
   4. Listez les stashes
3. Corriger l'erreur de frappe dans bug.txt sur la branche _master_ et faites un commit.
4. Retournez à votre travail initial, appliquez le stash précédent sur _master_ avec `git stash apply`
   1. Qu'y a-t-il en cours dans le répertoire de travail ?
   2. Et dans le staging ?
   >*Oups. Tous vos changements sont hors du staging maintenant. Ceci peut être problématique et inattendu.*
5. Nous allons défaire nos modifications avec `git reset --hard HEAD`. C'est une commande dangereuse car elle va retirer les fichiers du staging et du répertoire de travail définitivement. Mais pas d'inquiétude, nos modifications sont en sécurité dans un stash. Allez jeter un oeil au kata [reset](reset/README.md) si vous n'êtes pas sûr.e.s de comprendre ce qui se passe.
6. Appliquez le stash sur _master_ avec l'option `--index`.
   1. Maintenant, qu'y a-t-il en cours dans le répertoire de travail ?
   2. Et dans le staging ?
   >*Cette fois on est bien dans la situation initiale!*
7. Nous n'avons plus besoin du stash, effacez le.
   1. A qui ressemble la liste de stashes ?
   2. A quoi ressemble l'historique ?

## Commandes utiles

- `git status`
- `git status -s`
- `git diff`
- `git diff master`
- `git stash`
- `git stash list`
- `git stash apply`
- `git stash apply --index`
- `git stash drop`
- `git log --oneline --all --graph`
- `git commit`
- `git add`

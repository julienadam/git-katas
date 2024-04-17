# Git Kata: Commit sur la mauvaise branche

## Mise en place

1. Lancez `source setup.sh` (ou `.\setup.ps1` sous PowerShell)

Ce kata a été honteusement repris de [Git Katas](http://blog.schauderhaft.de/gitkata/).

Vous travaillez vraiment dur sur la branche master. Une partie de votre travail est déjà validée. C'est alors que votre chef arrive avec une demande urgente.

Étant donné que votre HEAD actuel n'est pas prêt pour la production, vous sauvegardez un commit, et commencez une nouvelle branche nommée 'quickfix'. Vous faites ce que votre patron vous demande et validez les changements sur cette nouvelle branche avec un commit.

C'est là que vous réalisez que vous avez créé un petit sac de noeuds avec vos branches.

Actuellement, vos commits ressemblent à cela

```text
         master
           |
           v
   A <---- B
   ^ \
   |  \--- C
remote     ^
           |
        quickfix
```

Mais vous voudriez qu'ils ressemblent plutôt à ça :

```text
         remote
           |
           v
   A <---- C <---- B
                   ^
                   |
                  HEAD
```

## Objectifs

1. Utilisez `git log --oneline --graph --all` pour visualiser les branches et les commits
2. Copiez `C` sur `master` avant `B` en faisant un rebase de `quickfix` sur `master`.
3. Créez une nouvelle branche (`changes-including-B`) depuis `master` afin de continuer à travailler sur `B`.
4. Faites pointer `master` sur `C` avec un reset.
5. Effacez la branche `quickfix`.
6. Poussez `master` (ceci n'est pas possible dans l'exercice mais serait l'opération à réaliser dans un contexte habituel avec un remote).

## Commandes utiles

- `git log --oneline --graph --all`
- `git switch <branch-name>`
- `git rebase <branch-name>`
- `git branch <branch-name>`
- `git reset --soft HEAD~`
- `git branch -d <branch-name>`
- `git merge <branch-name>`

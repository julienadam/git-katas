# Git Kata: Fusion en mode _fast-forward_

## Mise en place

1. Lancez le script `source setup.sh` sous Linux ou `.\setup.ps1` dans PowerShell sous Windows

## Étapes

A nouveau, vous êtes dans une branche dédiée, cette fois nous allons jongler entre plusieurs branches pour démontrer à quel point les branches sont légères avec Git.

1. Créez une feature branch nommée `feature/uppercase` (oui, `feature/uppercase` est un nom de branche valide et même une convention assez courante).
1. Placez-vous dans cette branche
1. Qu'affiche `git status` ?
1. Éditez le fichier greeting.txt pour qu'il contienne une salutation en majuscules.
1. Ajoutez `greeting.txt`au staging et faites un commit
1. Qu'affiche `git branch`?
1. Qu'affiche `git log --oneline --graph --all` ?
   *Souvenez-vous: vous voulez mettre à jour la branche master de manière à ce qu'elle contienne aussi les changements actuellement sur la feature branch. La commande `git merge [nom de branche]` prend un nom de branche en paramètre d'où les changements seront pris. La branche sur laquelle HEAD pointe actuellement (celle sur laquelle on se trouve) sera mise à jour avec les modifications présentes dans la branche passée en paramètre*
1. Passez sur la branche `master`
1. Utilisez `cat` pour regarder le contenu de `greeting.txt`
1. Faites un diff entre les branches
1. Fusionnez les branches
1. Utilisez `cat` pour regarder le contenu de `greeting.txt`
1. Qu'affiche `git log --oneline --graph --all` ?
1. Effacez la feature branch

## Commandes utiles

- `git branch`
- `git branch <branch-name>`
- `git branch -d <branch-name>`
- `git switch`
- `git branch -v`
- `git add`
- `git commit`
- `git commit -m`
- `git merge <branch>`
- `git diff <branchA> <branchB>`
- `git log --oneline --graph --all`

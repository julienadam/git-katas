# Git Kata: Utiliser rebase

## Mise en place

1. Lancez le script `source setup.sh` sous Linux ou `.\setup.ps1` dans PowerShell sous Windows

## Étapes

A nouveau, vous êtes dans une branche dédiée, cette fois nous allons jongler entre plusieurs branches pour démontrer à quel point les branches sont légères avec Git.

1. Quelles sont les branches disponibles ?
1. Affichez l'historique de la branche master
1. Placez vous sur la branche `uppercase`
1. Comparez l'historique avec celui de la branche `master` ?
1. Faites un rebase de la branche `master` sur `uppercase` (`git rebase master`)
1. Que s'est-il passé ? Dessinez le !
1. Placez vous maintenant sur la branche `master`
1. Fusionnez la branche `uppercase` dans `master`
1. A quoi ressemble l'historique maintenant ?

## Commandes utiles

- `git switch <branch-name>`
- `git rebase <branch-name>`
- `git log --oneline --graph --all`
- `git merge <branch-name>`

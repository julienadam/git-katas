# Git Kata: Fusion avec conflit

## Mise en place

1. Lancez le script `source setup.sh` sous Linux ou `.\setup.ps1` dans PowerShell sous Windows

## Étapes

Dans ce kata, git n'arrive pas à trouver un moyen de fusionner le contenu ajouté dans `merge-conflict-branch1` avec le contenu de `master`.

A la fin, on veut que les 2 modifications soient présentes dans `master`.

1. Utilisez `git merge` pour fusionner les changements de `merge-conflict-branch1` sur `master`.
1. Que sort `git status` ?
1. Résolvez le conflit avec votre éditeur favori, ou avec `git mergetool`
1. Suivez les instructions dans `git status` pour terminer la fusion
1. Que montre `git log --oneline --graph` ?

## Commandes utiles

- `git merge`
- `git status`
- `git add`
- `git commit`
- `git log --oneline --graph`

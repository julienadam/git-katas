# Git Kata: Merge de MergeSort

Dans ce kata on va gérer notre vrai véritable conflit de fusion.

Il y a 2 branches distinctes :

* Mergesort-Impl
* master

Votre tâche est de fusionner `Mergesort-Impl` sur `master` et résoudre le conflit en analysant le code et en éditant les fichiers en conséquence.

## Mise en place

1. Lancez le script `source setup.sh` sous Linux ou `.\setup.ps1` dans PowerShell sous Windows

## Étapes

1. Lancez `git branch` pour afficher les branches présentes
1. Fusionnez `Mergesort-Impl` sur `master`
1. Résolvez le conflit avec au choix :
   1. Votre éditeur favori **OU**
   2. Utilisez `git mergetool --tool=emerge` (pour les fans d'emacs) or `git mergetool --tool=vimdiff` (pour les fans de vim), ou votre outil configuré si vous en avez un avec `git mergetool`
1. Terminez la fusion (`git status` vous guidera)

## Commandes utiles

- `git branch`
- `git merge`
- `git status`
- `git mergetool`
- `git mergetool --tool=emerge`
- `git mergetool --tool=vimdiff`
- `git add`
- `git commit`


# Git Kata: Les bases de .gitignore

Nous allons travailler avec le fichier `.gitignore` dans ce kata.

Dans ce fichiers vous pouvez spécifier des fichiers, des extensions de fichier, des répertoires que vous ne voulez pas gérer avec git.

Vous pouvez tout de même manuellement ajouter des fichiers avec git add, même s'ils ont été ignorés dans le fichier .gitignore

Nous travaillerons aussi avec `git rm`, qui est la commande de suppression de git. `git rm` est équivalent à effacer un fichier du répertoire de travail puis à mettre dans le staging la suppression en lançant la commande `git add nom_fichier`.

Parfois vous ajoutez par erreur un fichier qui n'aurait pas dû être dans git (ex. des binaires, des fichiers .class etc.)

Si vous voulez signaler à Git qu'un fichier doit être retiré de git, mais que vous voulez qu'il reste présent dans votre répertoire de travail, utilisez la commande `git rm --cached` pour demander la suppression du fichier dans le staging mais pas dans le répertoire de travail.

## Mise en place

1. Lancez `source setup.sh` (ou `.\setup.ps1` sous PowerShell)

## Étapes

1. Créez un fichier nommé `foo.s`
1. Qu'affiche `git status`?
1. Créez un fichier `.gitignore` dans votre répertoire de travail contenant `*.s`
1. Qu'affiche `git status`?
1. Faites un commit du fichier `.gitignore`
1. Faites un commit du fichier `file1.txt`
1. Ajoutez les fichiers `txt` au `.gitignore` en ajoutant la ligne suivante `*.txt`
1. Qu'affiche `git status`?
1. Modifiez `file1.txt`
1. Qu'affiche `git status`? Pourquoi le fichier est-il présent dans le suivi alors qu'on a ajouté les fichiers `txt` au fichier ignore ?
1. Créez un autre fichier .txt dans le repository, qu'affiche `git status` maintenant ? Pourquoi n'est-t-il pas suivi ?
1. Ajoutez au staging la suppression du fichier `file1.txt` avec `git rm --cached`
1. Qu'affiche `git status`?
1. Créez un nouveau fichier nommé `file2.txt` et ajoutez la ligne `!file2.txt` au fichier `.gitignore`.
1. Qu'affiche `git status`? Pouvez-vous imaginer un cas d'utilisation pour suivre un fichier alors que l'extension est ignorée ?

## Commandes utiles
- `git rm`
- `git add`
- `git commit`
- `git commit -m`
- `git rm --cached`

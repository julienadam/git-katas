# Git Kata: Les bases du *commit*

Ce kata est une introduction aux commandes `git add` et `git commit`.

C'est un kata pour débuter, si vous avez déjà utilisé `git status`, `git log --oneline --graph`, `git add` et `git commit` régulièrement vous pouvez probablement passer à la suite.

Si vous n'avez pas encore fait la configuration de base de git, regardez en bas de cette page.

## Mise en place

1. Lancez le script `source setup.sh` sous Linux ou `.\setup.ps1` dans PowerShell sous Windows

## Étapes

1. Utilisez `git status` pour voir sur quelle branche vous vous trouvez
1. A quoi ressemble `git log` ?
1. Créez un fichier
1. A quoi ressemble la sortie de `git status` maintenant ?
1. Ajoutez le fichier à la zone de staging avec `git add`
1. A quoi ressemble la sortie de `git status` maintenant ?
1. Faites un `commit` du fichier dans le dépôt
1. A quoi ressemble la sortie de `git status` maintenant ?
1. Modifiez le contenu du fichier que vous avez créé tout à l'heure
1. A quoi ressemble la sortie de `git status` maintenant ?
1. Ajoutez la modification fichier à la zone de staging avec `git add`
1. A quoi ressemble la sortie de `git status` maintenant ?
1. Modifiez le fichier à nouveau
1. Faites un `commit` (sans ajouter la dernière modification au staging)
1. A quoi ressemble la sortie de `git status` maintenant ? Et celle de `git log` ?
1. Ajoutez et faites un commit du changement le plus récent

## Commandes utiles
- `git add`
- `git commit`
- `git commit -m "Mon message de commuit"`
- `git log`
- `git log -n 5`
- `git log --oneline`
- `git log --oneline --graph`
- `touch filename` pour créer un fichier (ou `sc filename ''` sous PowerShell)
- `echo content > file` pour écraser un fichier avec le contenu (ou `sc filename 'content'` sous PowerShell)
- `echo content >> file` pour ajouter du contenu au fichier (ou `ac filename 'content'` sous PowerShell)

## Configuration initiale de Git
1. `git config --global user.name "John Doe"`
1. `git config --global user.email "johndoe@example.com`

Si vim vous fait peur :
- `git config --global core.editor nano`

Pour les utilisateurs Windows :
- `git config --global core.editor notepad`

D'autres options :
- `git config --global core.editor "atom --wait"`
- `git config --global core.editor "code --wait"`
- `git config --global core.editor "'C:/Program Files/Notepad++/notepad++.exe' -multiInst"`
